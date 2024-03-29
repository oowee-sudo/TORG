#**Linux files**
- **`/etc/passwd`**: find interpreter
- **`/var/run`**: ps data
- **`/var/spool`**: temp data
- **`/sys/kernel/debug`**: activate trace in kernel
- **`/proc`** **`/sys`** : virtual directories
- **`SetUID`** **`SetGID`** **`Sticky Bit`** : special permissions
#**Linux commands**
- **`dmesg`** : kernel messages
- **`nice`** : change x priority
- **`journalctl`** : logs
- **`crontab -e`** : Scheduling jobs
- **`df`** : disk free usage
- **`dd`** : copy
- **`tldr`** : too long didnt read
- **`pwd`** : print working directory 
- **`cut`** **`uniq`** : edit string output (ocurrence)
- **`paste`** : merge file lines
- **`IO Redirect`** : `2>` `>>` `2>>`  redirect error / append , `<` redirect input to file
- **`read`** : read user input
- **`env`** : check all environment variables ( `set` `unset`)
- **`echo "<n>Debug info " | sudo tee -a /dev/kmsg > /dev/null`** : write in a privileged file
#**Network files**
- **Hostname**:  **`/proc/sys/kernel/hostname`**  **`hostnamectl`** **`/etc/hostname`**
- **ip config** : **`iproute2`** package for **`ip`**
- **Network config** : **`/etc/network`**
- **DNS** : **`/etc/hosts`** **`/etc/resolv.conf`**
- **SSH** : **`ssh-copy-id`** **`ssh-keygen`** **`scp`**
- **open ports** : **`ss`**  **`lsof`**
- **interface realtime**: **`bmon`** **`iptraf`**
- **packets analysis**: **`tcpdump`** **`wireshark`** 
