# PowerShell_Reverse_Shell_AMSI_Bypass
This script is a reverse shell written in PowerShell capable of bypassing the Windows AMSI.

1. Connection Setup:
 - It connects to a remote host (10.10.10.10) on port 4455 using a TCP client.
 - A network stream is established for data transmission.

2. Data Handling:
 - It continuously listens for incoming data from the remote host.
 - Incoming data (commands) is read as UTF-8 encoded text, interpreted, and executed on the local system using Invoke-Expression.

3. Response Transmission:
 - The output or errors resulting from the executed commands are sent back to the remote host over the same TCP connection.

4. Loop Behavior:
 - The script runs in a loop as long as the TCP connection is active, ensuring a continuous back-and-forth communication.

5. Cleanup:
 - Once the connection is closed, all resources (the TCP client, stream, and readers/writers) are properly disposed of.


![NVIDIA_Overlay_BDU4VW9QHK](https://github.com/user-attachments/assets/d3bf5bf8-f6eb-4169-abea-ee78e04e5834)
