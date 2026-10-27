# Task Five — Wireshark ICMP Capture

## Objective
Capture and analyse ICMP echo requests and replies for Google, the network gateway, and localhost using Wireshark.

## Network Details
- Network interface: eth0
- Kali source IP: 10.0.2.15
- Gateway IP: 10.0.2.1

## Capture Files
- google.pcapng — ICMP traffic to google.com
- gateway.pcapng — ICMP traffic to the gateway (10.0.2.1)
- localhost.pcapng — ICMP traffic to localhost (127.0.0.1)

## Method
1. Started packet capture in Wireshark on the relevant interface.
2. Sent four ICMP echo requests to each target using ping.
3. Applied the ICMP display filter in Wireshark.
4. Checked the echo requests and replies.
5. Saved each capture as a separate PCAPNG file.

## Ping Results

| Target | Sent | Received | Loss | Min RTT (ms) | Average RTT (ms) | Max RTT (ms) |
|---|---:|---:|---:|---:|---:|---:|
| Google (google.com) | 4 | 4 | 0% | 19.403 | 22.611 | 30.721 |
| Gateway (10.0.2.1) | 4 | 4 | 0% | 0.468 | 0.860 | 1.662 |
| Localhost (127.0.0.1) | 4 | 4 | 0% | 0.038 | 0.379 | 1.300 |

## Observations
- Fastest target: Localhost (average RTT: 0.379 ms).
- Slowest target: Google (average RTT: 22.611 ms).
- Gateway average RTT: 0.860 ms.
- All targets received four replies with 0% packet loss.

## Conclusion
ICMP traffic was captured for all three targets. Localhost had the lowest average round-trip time, followed by the gateway, while Google had the highest.
