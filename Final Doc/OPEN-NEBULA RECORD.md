# Admin portal

## Logging in

Connect to internet and type `192.168.81.220:9896` in the URL bar to enter into the website 

![[Screenshot from 2024-10-07 16-01-35.png]]

#### User credentials :
- Username : admin
- Password : cit123

## Dashboard

Dashboard gives the details of :

- Virtual Machines 
	- Total VMs
	- Pending VMs 
	- Failed VMs
- Images
	- Available images
	- Memory consumed by the image
- Systems
	- Total users created
	- Total groups present
- Virtual Networks
	- Virtual Networks available (created by the admin)
	- Number of IPs used 

![[Screenshot from 2024-10-07 16-01-52.png]]

## Instances 

![[Screenshot from 2024-10-07 16-02-27.png]]

Under instances we can create,
1. VMs
2. Services
3. Virtual Routers

#### Creating a new VM

1. Click the `+` icon to create a new VM
2. Select the Template for the VM (here template means OS)
	- Templates can be installed based on our preferce

![[Screenshot from 2024-10-07 16-02-38.png]]

3. Enter the amount of space to be allocated for the VM i.e. Memory, Disk space, Physical CPU,etc 
 ![[Screenshot from 2024-10-07 16-03-14.png]]

4. Select Network from the available network templates
![[Screenshot from 2024-10-07 16-03-52.png]]

5. Now a new VM has been created.
6. To start the newly created VM select the VM.
7. Select the `Monitor` icon in the top and choose VNC

![[VNC.png]]

8. The VM will be opened in a new tab
![[2024-10-08_16-27.png]]


## Network

### Creating a Virtual network

1. Go to `Virtual Networks` under the `Network` page
![[Screenshot from 2024-10-07 16-04-29.png]]

2. Select the `+` icon to create a new Virtual network 

3. Name the network as you wish and select the `0: default` for cluster then go to `Conf`
![[Screenshot from 2024-10-07 16-05-07.png]]

4. Under `Conf` fill the options as follows 
	- Bridge : bridge0
	- Network mode : Bridged

![[Screenshot from 2024-10-07 16-05-33.png]]

5. Under `Addresses` fill the options as below
	- First IPv4 address : 192.168.1.1     (this is the starting address of the network)
	- First MAC address : 02:00:00:00:00:01
	- Size : 20     (number of network group's ip available)

![[Screenshot from 2024-10-07 16-07-44.png]]

6. Under `Security` choose the security group (default group will be selected automatically if no group is created). 

![[Screenshot from 2024-10-07 16-07-53.png]]

7. Now click the `create` button in the top which created the new virtual network.

8. Available networks can be viewed `Network` page

![[Screenshot from 2024-10-07 16-09-31.png]]


## System
### Creating a new User

1. Under `System` page select the `Users` option

![[2024-10-08_16-32.png]]

2. Click the `+` icon to create a new user.
3. Fill the Username and Password for the user.
4. Select the group under which the user has to be added.

![[2024-10-08_16-34.png]]



# Student portal

Enter the server/host machine's IP with along with port `9869` in the URL bar of the web-browser.
For e.g. `192.168.81.220:9869`

1. Enter the credentials (username and password) that is created by the admin

![[2024-10-08_16-37.png]]

### Dashboard

- Dashboard show the basic informations like Virtual Machined and Quotas.
![[2024-10-08_16-36.png]]

#### Using VMs 

1. Choose VM in the menu bar to list all the available VMs

![[2024-10-08_16-43.png]]

2. Choose the VM that you need form the list
3. Click the `Start/Play` icon to start the VM

![[2024-10-08_16-45.png]]

4. Refresh and wait until the VM starts running 
5. To open the VM click the `Monitor` icon and choose `VNC`

![[2024-10-08_16-46.png]]

6. Login to the VM and start working

![[2024-10-08_16-47.png]]