---
title: 'Finding the optimal TCPIP receive window size'
date: '2002-05-10T13:10:45+02:00'
status: publish
permalink: /article/tcpip-rwin-size.html
author: Snakefoot
excerpt: 'Using PING to test the network connection and calculating the best TCP/IP receive window.'
type: post
id: 188
category:
    - Network
    - Network
    - Network
    - Network
    - Network
    - Network
    - Network
tag:
    - lan
    - max-transfer-unit
    - network-performance
    - ping
    - rwin
    - tcpip
    - wan
post_format: []
tags:
    - 'rwin,max-transfer-unit,lan,wan,tcpip,ping,network-performance'
---
##### What problem does the receive window solve?

 TCPIP is a reliable network protocol where each packet sent is acknowledged by receiver, and if the sender doesn't get the acknowledge packet back within a certain timeout, then it retransmits the original packet. But it is inefficient to wait for the acknowledge packet from the receiver before sending the next packet. The Receive WINdow(RWIN) solves the problem of the sender constantly waiting for the receiver acknowledge.  
  
##### How does receive window work?

 The RWIN size specifies how much data, which can be sent to the receiver without getting an acknowledge from the receiver. This allows the sender to send several packets without waiting for acknowledge. It also allows the receiver to acknowledge several packets in one stroke.  
  
##### Why is the size of the receive window important?

 If the RWIN is too large, then the sender will spend a lot of time resending the entire RWIN every time packet loss is detected by the receiver. This is especially important if on a high collision network like a 100 Mbit Ethernet HUB. If Selective Acknowledgment (SACK) is enabled then it should lessen the downside of a too large RWIN.  
 If the RWIN is too small, then the sender will be blocked constantly because it fills out the RWIN with packets before receiver is able to acknowledge that it has received the packets.  
  
##### What is the proper size of the receive window?

 The optimal RWIN is mainly dependent on two things:
 - **Latency**: The time it takes for a network packet to reach destination and get a reply back (Also known as ping time). If the latency is high and the RWIN too small, then it can allow the sender of data to fill out the RWIN before any acknowledge packet is returned.  
    
   The latency for a connection is dependent on how quick the sender and receiver(and routers in between) are able to handle packets. If reaching the bandwidth limit of the physical line, then the latency becomes high.
- **Bandwidth**: The amount of data that can be sent within a given time. If the bandwidth is high and the RWIN is too small, then sender can fill out the RWIN too fast, before the receiver can acknowledge the received data.  
    
   The max bandwidth for a connection is dependent on the lowest available bandwidth at sender and receiver(and routers in between). The max limit can also depend on the ISP capping, or by the receiving/sending application throttling the connection.

##### How to find the optimal receive window size with PING?

 To use the PING (Packet InterNet Groper) tool to find the optimal RWIN Size, ping your ISP with the [Max Transfer Unit(MTU) size](/article/tcpip-mtu-size.html) (The -28 is because of the IP- and ICMP-Header which the PING tool adds.) > PING www.tiscali.dk -f -l &lt;MTU-28&gt; -n 10

 Then insert the values of your connection in this calculation :  
> Bandwidth(kbps) / 8 \* Average Latency(MiliSec) = RWIN Size(Bytes)

 Then round up the RWIN Size to a multiple of the Maximum Segment Size (MSS) which is equal the MTU Size subtracted the size of IP Header (20 Bytes) and TCP Header (20 bytes + ? bytes depending of options like timestamp being enabled). So if your MTU Size is 1500 then your MSS is usually 1460 (1448 if timestamp is enabled).  
  
<form action="" id="calculateform"><table border="0" cellspacing="4"><tr><td>Bandwidth</td><td>Latency</td><td>MSS</td><td></td><td>Receive Window</td></tr><tr valign="top"><td><input maxlength="8" name="bandwidth" size="9" type="text" value=""></input></td> <td><input maxlength="4" name="latency" size="5" type="text"></input></td> <td><input maxlength="4" name="mss" size="5" type="text"></input></td> <td><input name="calcbutton" onclick="javascript:CalculateRWIN()" type="button" value=" Need JScript "></input></td> <td><input maxlength="7" name="rwin" readonly="readonly" size="8" type="text"></input></td> </tr><tr valign="top"><td> <input checked="checked" name="bwtype" type="radio" value="kbps"></input>kbps  
<input name="bwtype" type="radio" value="KByte"></input>KByte/Sec</td> <td>milisec</td><td>bytes</td><td></td><td>bytes</td></tr></table>

</form> <script type="text/javascript"><!--
document.forms.calculateform.calcbutton.value = "Calculate RWIN";
function CalculateRWIN()
{
document.forms.calculateform.rwin.value = "NaN";
if (document.forms.calculateform.bwtype[1].checked)
	raw_rwin = eval(document.forms.calculateform.bandwidth.value) * eval(document.forms.calculateform.latency.value);
else
	raw_rwin = eval(document.forms.calculateform.bandwidth.value) / 8 * eval(document.forms.calculateform.latency.value);
if (document.forms.calculateform.mss.value=="")
{
	if (raw_rwin<8192)
	{
		raw_rwin = 8192;
	}
}
else
{
	if (raw_rwin<6*eval(document.forms.calculateform.mss.value))
	{
		raw_rwin = 6*eval(document.forms.calculateform.mss.value);
	}
	else
	{
		rwin_remainder = raw_rwin % eval(document.forms.calculateform.mss.value);
		raw_rwin = raw_rwin-rwin_remainder+eval(document.forms.calculateform.mss.value);
	}
}
document.forms.calculateform.rwin.value = raw_rwin;
}
//--></script>  
##### How is the default receive window size calculated in Microsoft Windows?

 Microsoft Windows tries to find the most optimal RWIN during the connection handshake. For most network types the following method will calculate a reasonable RWIN, so one doesn't have to configure it manually:
1. The initial connection request is created with a RWIN of 16384 bytes 
  - Win9x/WinNT4 uses a RWIN of 8192 bytes
  - Win2k3 uses a RWIN dependent on media speed (Ignores latency): 
      - Below 1 Mbps: 8192 bytes
      - 1 Mbps - 100 Mbps: 16384 bytes
      - Greater than 100 Mbps: 65536 bytes
  - Windows Vista/2008 uses [receive window scaling](/article/vista-tcpip-auto-rwin.html) by default, and uses a default RWIN of 64K.
2. When the reply to the initial connection is received the RWIN is adjusted: 
  1. RWIN is rounded up to a even multiple of Maximum Segment Size (MSS).
  2. RWIN is adjusted to the larger of 4 times MSS, but not higher than 65536 bytes (unless Windows Scaling is enabled). 
      - If the GlobalMaxTcpWindowSize is set then it will be highest limit
 
 Note when creating a socket it is possible to overrule the default RWIN size using **setsockopt** with the socket option SO\_RCVBUF. If the GlobalMaxTcpWindowSize is set, then it will limit the max size of the RWIN.  
  
 More Info [MS KB93444](http://support.microsoft.com/kb/93444 "Tuning TCP/IP for Performance [Q93444]")  
 More Info [MS KB172983](http://support.microsoft.com/kb/172983 "Explanation of the Three-Way Handshake via TCP/IP [Q172983]")  
  
 Related [Recommended settings for the TCP/IP stack](/article/windows-tcpip-settings.html)  
  
 Credits [DSLReports.com](http://www.dslreports.com/)