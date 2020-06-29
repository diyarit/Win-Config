## Recommended Windows settings

Este script configura Windows según nuestras buenas prácticas:

-   Disable SMB v1
-   Disable NetBIOS
-   Disable unnecessary network services (file sharing, device search, etc.)
-   Turn on automatic Windows updates
-   Deactivate Remote Access Firewall (WinRM) rules
-   Activate RDP and change port to 20389 (requires restart)
-   Activate NTP and synchronize server time

## Installation (from PowerShell)

    Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Force
	$Url = "https://raw.githubusercontent.com/diyarit/Win-Config/master/configure_windows.ps1"
	$Output = "C:\configure_windows.ps1"
	$WebClient = New-Object System.Net.WebClient
	$WebClient.DownloadFile( $url , $Output)
	Invoke-Expression $Output

When finished restart server to apply RDP changes
