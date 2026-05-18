# Below are the wazuh rules added to detect rootkit kernel behaviour 

open the ossec.conf file with the code below
```bash
sudo nano /var/ossec/etc/osssec.conf
```
_paste the code in the image below under the <rootcheck> section_

```xml
<disabled>no</disabled>
<check_files>yes</check_files>
<check_trojans>yes</check_trojans>
<check_dev>yes</check_dev>
<check_sys>yes</check_sys>
<check_pids>yes</check_pids>
<check_ports>yes</check_ports>
<check_if>yes</check_if>

<!-- rootcheck execution frequency - every 12 hours by default-->

<frequency>120</frequency>

<rootkit_files>etc/shared/rootkit_files.txt</rootkit_files>

<rootkit_trojans>etc/shared/rootkit_trojans.txt</rootkit_trojans>

<skip_nfs>yes</skip_nfs>
```
---

# Detection & Monitoring

# Wazuh Rootcheck

Configured Wazuh to perform frequent rootkit scans every 2 minutes.

---

# Observed Alerts

Detected:
- Hidden processes
- Rootkit activity
- System inconsistencies
- Suspicious rsyslogd, sshd, cron modifications

---

# Custom Rule

File:
```bash
/var/ossec/etc/rules/test_process.sh
```
