# This is configuration of the Workstatiom Virtual Mechines

# 1) Management Virtual Mechine

1. First We must install all the tools we need to complete the lab.
    I. Open Windows Terminal or Powershell as Administrator 
    II. Install Chocolatey 
        I. cmd: Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1')) 
    III. Install git (for any & all project notes)
        I. choco install git
        II. A (When Prompted)
    IV. Install gh (for additional github functionasllity)
        I. choco install gh
        II. A (When prompted)
    V. Install vscode (to write scripts (in the scripts folder))
        I. choco install vscode
        II. A (when prompted)
# After installing all the tools restart powershell to use each one as needed

2. Now Configure Powershell to access the server from this Machine
    I. Start-Service WinRm
    # This next command tells the workstation that it can trust the server
    II. Set-Item WSMan:localhostClientTrustedHosts -Value (IP Address of DC1) 

# Now we can Finish Configuring DC1 to be an Active Directory Domain Controller

    1. Enter-PSSession -ComputerName (Ip Adress of DC1) -Credentials (Get-Credential) 
# When prompted enter the login credentals of the server NOT the workstation

    2. Install-WindowsFeature AD-Domain-Services -IncludeManagementools

    3. Import-Module ADDSDeployment

    4. Instalkl-ADDSForest

    5. (on next prompt) Enter your desired domain name

    6.  Server will restart 