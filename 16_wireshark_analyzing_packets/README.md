Lab 16: Analyze Your First Packet with Wireshark

Platform: Qwiklabs
Skill Area: Network Analysis, Cybersecurity, Packet Inspection
Date Completed: 05-11-2025
Difficulty: Advanced

📝 Overview

In this lab, I learned how to use Wireshark to capture, inspect, and analyze network traffic. I explored the three-pane interface of Wireshark, applied display filters, and examined packet details across different protocol layers including Ethernet, IPv4, TCP, UDP, ICMP, and DNS.

Through hands-on exercises, I learned how to:

Identify source and destination IP addresses in a web browsing session.

Analyze ICMP Echo (ping) requests and determine protocol types.

Apply filters such as ip.addr, ip.src, ip.dst, and eth.addr to isolate traffic.

Explore DNS queries and responses using udp.port == 53 and identify resolved IPs.

Examine TCP traffic on port 80 to analyze HTTP packets and packet structure (Frame length, Header length, TTL).

Search for specific payload data (e.g., tcp contains "curl") to locate packets with targeted content.

🔍 Key Findings
Finding	Result
Protocol of first Echo (ping) request	ICMP
TCP destination port	80
Protocol in MAC filter packet	TCP
DNS query IP for opensource.google.com	142.250.1.139
Time to Live (TTL)	64
Frame Length	54 bytes
IPv4 Header Length	20 bytes
Destination Address	169.254.169.254
🧠 Skills Practiced

Network traffic inspection

Protocol and port analysis

Filtering and isolating network data

Packet structure dissection (Frame, Ethernet, IP, TCP/UDP layers)

DNS resolution analysis

Practical use of Wireshark in incident response contexts

📸 Evidence

Below are the screenshots captured during the lab to demonstrate key steps and findings:

-Wireshark was launched and the sample .pcap file was opened. This provided an overview of captured packets, showing columns for source, destination, protocol, and additional packet info.
![Screenshot 1](images/01_opening_wireshark.png)

-A display filter ip.addr == 142.250.1.139 was applied to isolate traffic between the local system and the target IP address. The packet list reduced to only relevant entries for easier inspection.
![Screenshot 2](images/02_applying_ip_addr_search.png)

-A TCP packet was selected for detailed inspection, displaying the Transmission Control Protocol layer. The TCP destination port was identified as 80, confirming HTTP communication.
![Screenshot 3](images/03_tcp_search.png)

-The Frame subtree was expanded to view physical-level details such as arrival time, frame length, and total captured bytes. The frame length for this packet was confirmed as 54 bytes.
![Screenshot 4](images/04_frame_search.png)

-The Ethernet II layer was explored to identify the source and destination MAC addresses. This information reveals which devices on the network were involved in the communication.
![Screenshot 5](images/05_ethernet_search.png)

-The Internet Protocol Version 4 (IPv4) layer was expanded to display the source and destination IP addresses, protocol type, and header length—which was found to be 20 bytes.
![Screenshot 6](images/06_ipv4_seaerch.png)

-The TCP destination port field was reviewed, showing port 80, which is the default port for HTTP web traffic. This confirmed that the packets represented standard web browsing activity.
![Screenshot 7](images/07_destination_port_search.png)

-The filter ip.src == 142.250.1.139 was applied to display only packets originating from the specified IP address. This allowed analysis of outgoing traffic from the remote web server.
![Screenshot 8](images/08_ip_source_search.png)

-The filter ip.dst == 142.250.1.139 was used to isolate packets sent to the target IP. This step focused on inbound traffic from the local system to the web host.
![Screenshot 9](images/09_ip_destination_search.png)

-The filter eth.addr == 42:01:ac:15:e0:02 was used to isolate packets containing a specific Ethernet MAC address. This narrowed down communication between devices at the data link layer.
![Screenshot 10](images/10_mac_address_search.png)

-Within the Ethernet II subtree, the source and destination MAC addresses were verified. The corresponding IPv4 subtree revealed that the internal protocol carried in these packets was TCP.
![Screenshot 11](images/11_mac_address_source_and_destination_ports.png)

-The Time to Live (TTL) field within the IPv4 header was examined. The TTL value of 64 indicated the packet’s lifespan across network hops before expiration.
![Screenshot 12](images/12_time_to_live.png)

-A UDP filter udp.port == 53 was applied to capture DNS-related traffic. This step isolated packets containing DNS queries and responses between the client and DNS server.
![Screenshot 13](images/13_udp_port_search.png)

-Inside the DNS query packet, the Queries section was expanded, revealing that the requested domain was opensource.google.com. This confirmed the user’s attempt to resolve the domain name.
![Screenshot 14](images/14_udp_domain_queries.png)

-In the DNS response packet, the Answers section showed the IP resolution for opensource.google.com, returning the address 142.250.1.139 from the DNS server.
![Screenshot 15](images/15_udp_domain_answers.png)

-A TCP filter tcp.port == 80 was used to isolate HTTP packets. The packet details confirmed standard web communication with a destination address of 169.254.169.254 and frame length of 54 bytes.
![Screenshot 16](images/16_tcp_port_search.png)

-Finally, the filter tcp contains "curl" located packets containing the text “curl” in their payload. This confirmed the presence of a web request made using the curl command-line tool within the capture.
![Screenshot 17](images/17_contains_curl_search.png)

✅ Conclusion

This lab provided practical experience in packet-level network analysis using Wireshark. I now understand how to dissect packets, identify communication protocols, and apply advanced filtering to focus on relevant network traffic—critical skills for any cybersecurity analyst or network defender.
