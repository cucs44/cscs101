# Before you start
This repo help you setup the environment
# Using SSH to connect linux server
In this session, we are connect to cse linux server via vscode. It would take up around 400MB on your allocated space on linux server. If you want to save the space, use terminal instead. Also you may want to enable   `[remote.ssh: remote server listen on socket]` for your remote:ssh plugin before connect.
1. Connect to CUHK CSE network  
   Follow [this guide](https://www.cse.cuhk.edu.hk/misc/cse-account-password-vpn/) from CSE department to use VPN
2. Install remote-ssh plugin  
   search `ms-vscode-remote.remote-ssh`, press `install`  
   ![image](./image/remotessh.jpg)
3. Create an alias for ssh login configuration  
   - Click the ssh icon at bottom-left corner  
   ![image](image/sshicon.jpg)  
   - Then select `Open SSH Configuration File`
   ![image](image/sshmenu.jpg)  
   - Select a ssh config file(recommend select the one including your username in path)
   - Edit the config    
    ```
    Host CSE
        HostName linux7.cse.cuhk.edu.hk
        User YOUR-UNIXID
    ```
    Note: HostName can be from linux1 to linux16. Also, if you don't want to connect to CSE network, you can set the HostName as `gw.cse.cuhk.edu.hk`
4. Connect to remote  
   - Click the ssh icon at bottom-left again and select `Connect to Host...`   
   ![image](./image/sshselect.jpg)  
   - Select the alias you just config
   ![image](./image/sshconnect.jpg)  
   - Enter your unix password  
    Note: You may need to choose yes for first time connecting to the server.
   ```
   #> The authenticity of host 'SOME-IP-OR-DOMAIN' can't be established.
    #> ECDSA key fingerprint is SHA256:.....
    #> Are you sure you want to continue connecting (yes/no/[fingerprint])? 
    ```