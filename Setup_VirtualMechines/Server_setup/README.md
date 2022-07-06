# Server Setup

1. run SConfig
2. rename server to DC1
3. configure Network to use a Static IP ADDRESS (In my case I used 10.10.24.28)
4. set primary DNS server to the ip address you configured in the previous step
5. exit SConfig into powershell

-----------------------------------------------------------------------------------------------------
Shell commands

# The only thing you have to run directly on the server will allow you to run commands for the Server directly from the Management workstation.

Enable-PSRemoting

exit
exit

-----------------------------------------------------------------------------------------------------
# The rest of the configuration and commands are found in the Management file in the workstation folder of this project