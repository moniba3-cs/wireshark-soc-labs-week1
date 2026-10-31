
# Wireshark SOC Labs - Week 1

Four hands-on Wireshark labs from the Networkwalks internship, analysing packet captures as a SOC analyst.

| Lab | Topic | What I did |
|---|---|---|
| 1 | Identify the Attacker's IP | Filtered SYN packets, found a port scan (40 ports) from one IP |
| 2 | HTTP Plain Text Credentials | Read username/password from an unencrypted HTTP POST |
| 3 | Brute Force Catch | Found repeated FTP logins (530 errors) and the successful login (230) |
| 4 | VoIP Call Replay | Analysed SIP/RTP, played the call with RTP Player |

## Key filters used
- tcp.flags.syn == 1 && tcp.flags.ack == 0
- http.request.method == "POST"
- ftp.response.code == 530
- sip.Method == "INVITE"
- rtp

## Takeaways
Use HTTPS/SFTP instead of HTTP/FTP, encrypt VoIP (SRTP), and monitor for port scans and repeated failed logins.
