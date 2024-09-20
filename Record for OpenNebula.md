### Initial status 
Server is opening and login as admin is successful. User creation and login gives error.


#### How to open opennebula poral?
`ip.address:9869` _replace ip.address with the system ip address_


#### Error: Status of host is "ERROR"

Change the ip of the opennebula. Host(System) must have the ip of the current network

1. use "nano /etc/hosts"
2. change the ip of opennebula to current network ip - (198.168.122.1 on 16/08/2024)

This changes the "INIT" or "ERROR" status of the host to "ON".


============================

use "ping opennebula" to see wheather the network is connected

============================

use "ssh opennebula" 
--> check the ssh working

============================

### 20.08.2024

**Current IP for the system :** 192.168.119.198
#### Error : Fireedge_key is not available

![[Pasted image 20240820153112.png]]
**Solution:**

```bash
cd /var/lib/one/.one/
echo "random_key" >> fireedge_key
```

**Status:** No repeated error. 
**New error:** server

**Problem detected :** opennebula-fireedge server not started 
**Solution:**
```bash
systemctl start opennebula-fireedge #to start the server
systemctl enable opennebula-fireedge #enabling auto-start on system boot
```

Now fireedge_key has generated successfully

***Current status :***  VNC is opening 


#### ERROR: User login cred not available
Solution : Resetting the password

1. Use ctrl+alt+del  //use CtrlAltDel button available in opennebula
2. Click shift while booting to enter into choice screen
3. Choose recovery mode
4. Choose soft reboot
5. Click enter and type the following command to change the password
```bash
cd /
passwd root #root is the default user
```
6. Type the new password and continue.
7. Reboot normally and enter the password we set previously. 

### 22.08.2024

**Current IP for the system :** 192.168.126.198

**Status :**  
Started working in client machine. 
User Login successful 
Trying to run VM using client machine

#### ERROR : *TUNNEL_ERROR*  in VNC (client machine)
##### SUB-ERROR : *FireEdge public endpoint is not working, please contact your cloud administrator.*
![[./2024-08-22_11-23.png]]

Tried changing `/etc/one/sunstone-server.config`

```bash
#change :public_fireedge_endpoint
#old = http://localhost:2616
#new 
http://one.example.com:2616
```

**Solution :**
Changing `/etc/one/sunstone-server.config`
```bash
#change :public_fireedge_endpoint
#old = http://localhost:2616
#new 
http://192.168.126.196:2616

```

Restart opennebula sunstone server
```bash
systemctl restart opennebula-sunstone
```

**Current status :** 
VNC working in client system. 
Accessing VM using client system is done. 

**Requirement :** Client systems have to be in same network as host system.
