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
# VScode
VSCod(e/ium) has GUI and low learning curve, it can be used on Linux, Windows, and MacOS. If you have not chosen a tool for code, we suggest VSCode for beginners.  

In general, we suggest you to open one VSCode window per repository. After clone a repo from github, run `code REPO-NAME` to open a new VScode window.
## Feature
- Explorer: Show all the file in this repo, you can click to edit.  
Note: You can drag a file into explorer to upload that to your remote server. Right click a file and select download can do the reverse.  
![image](./image/explorer.jpg)
- Search: To search for keywords in the whole repo.  
![image](./image/search.jpg)
- Source Control: To track your staged/local change, also provide working tree for comparison.
![image](./image/sourcecontrol.jpg)
- Terminal: To run commands during development.
![image](./image/terminal.jpg)

## Configs
You may want to set these config  
`"terminal.integrated.scrollback": 100000`: increase your scrollback buffer large enough to see some error message, default of 1000 is grossly not enough.  

`"editor.formatOnSave": true`: formate your code on save, this feature will call the formatter of your own choice, you have to install some formatter for it work properly.  

`"diffEditor.ignoreTrimWhitespace": false`: some programming language(like Python) care about whitespace.

## Extension
### General

`ms-vscode-remote.remote-ssh`: Use VSCode on remote directory just like local  

`aaron-bond.better-comments`: Highlight comments by categories  

`eamodio.gitlens`: Integrate GUI git diff and history, among other features, into VSCode

### Language Specific

`ms-python.vscode-pylance`: python3 syntax highlighter and linter support

`esbenp.prettier-vscode`: javascript formatter

`graphql.vscode-graphql`: graphql syntax highlighter

## Hotkeys

### General
`ctrl + -`: Decrease text size

`ctrl + =`: Increase text size

### Editing

`ctrl+f`: find, you can also do highlight then ctrl+f (or other find / replace hotkey), VSCode generate the required Regex for you.

`ctrl+shift+F`: find globally

`ctrl+h`: replace

`ctrl+shift+H`: replace globally

`ctrl+g`: go to line (enter a line number)

`ctrl+shift+arrow`: multi-line text cursor

`ctrl+/`: comment / uncomment

`ctrl+w`: close file

`ctrl+shift+I`: format file

### Terminal

`` ctrl+` ``: open / close terminal, focus to terminal

`ctrl+shift+5`: split terminal into 2

``ctrl+shift+` ``: new terminal

`ctrl+d`: terminate current terminal