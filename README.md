# DOS-DDOS-project
BIA-Spinnaker Analytics on-job Project
This script provides a full-featured tool to detect and mitigate DoS attacks with IP whitelisting, email alerts, and logging.

Packet Sniffing: The script monitors the specified network interface using scapy to detect incoming IP packets.
Traffic Analysis: It keeps track of the number of packets from each source IP. If the count exceeds a predefined threshold (THRESHOLD) within a specified time window (TIME_WINDOW), the source IP is identified as potentially performing a DoS/DDoS attack.
Blocking IP: When an IP exceeds the packet threshold, the script blocks the IP using the Windows Firewall via the netsh command.
Status Reporting: Every 20 seconds (or configurable via REPORT_INTERVAL), the script reports whether an attack is ongoing or not by checking the flag attack_detected.
Email Alerts: The script sends an email notification to an administrator when an attack is detected, ensuring emails are not sent more frequently than the specified EMAIL_INTERVAL.
Logging: Attack events and status updates are logged to a file (attack_logs.txt).
Whitelisting: IPs specified in the WHITELISTED_IPS list are never blocked.
