# DAY - 04 WIRESHARK 

Wireshark is a popular open-source network protocol analyzer used for network troubleshooting, analysis, and security auditing. It captures and displays data packets traveling over a network in real-time, allowing users to inspect the contents of the packets for various protocols (like HTTP, DNS, TCP, UDP, etc.).

More about [wireshark](https://www.wireshark.org/)

# What is Wireshark 

Wireshark is like a super tool that helps you see what's happening on the internet in real time. Imagine you're sending messages through the air, and Wireshark can catch those messages and show you what they say, where they came from, and where they’re going. It helps people check if things are working right on the internet or if someone is trying to mess with the network.

Here are some key features of Wireshark:

- **Packet capture:** Captures live network traffic and provides detailed information about each packet.
- **Protocol analysis:** Decodes hundreds of network protocols and shows how the data is structured.
- **Real-time analysis:** Displays live data as it is captured from the network interface.
- **Filtering:** Users can apply filters to focus on specific types of traffic or conversations.
- **Exporting data:** Captured data can be saved and analyzed later, or exported for sharing.
- **Use in cybersecurity:** Wireshark is often used in penetration testing and vulnerability assessment to analyze network traffic for potential issues or attacks.

![Screenshot 2024-09-17 131216](https://github.com/user-attachments/assets/0994a3fd-0356-4442-8abc-c09dfae371b3)
> Wireshark can be found under the sniffing and spoofing section 

# Understanding the interface 

To open up wireshark simply go to the sniffing and spoofing section and select wireshark , or you can go to your terminal and write the command `wireshark`. On opening wireshark you're greeted with the network interface.

![Screenshot 2024-09-17 133840](https://github.com/user-attachments/assets/e728111f-62ed-471b-8762-aafcc0d8218d)

The network interface in Wireshark is where you choose which part of your computer's network connection you want to listen to for capturing data. Here's how it works:

### 1. What is a Network Interface?

A network interface is like a door through which data enters and exits your device. It could be your Wi-Fi, Ethernet (wired internet), or even virtual network interfaces like docker0 in Docker or lo for local traffic.

### 2. Choosing the Interface in Wireshark

When you open Wireshark, you’ll see a list of all available network interfaces. These could be:

- Wi-Fi (for wireless network traffic)
- Ethernet (for wired connections)
- Virtual Interfaces (like docker0, if you’re using Docker, or other VMs)
- Local Loopback (lo), used to capture traffic that stays within your own computer.

### 3. How to use the interface

- Select the interface you want to capture from by clicking on it.
- If you’re unsure, usually your Wi-Fi or Ethernet is the main one you’ll capture data from, depending on how you're connected to the internet.
- Wireshark shows spike on the interface that is being used for example eth0.
- Once you choose an interface and start capturing, Wireshark will show you live data packets traveling through that interface.


