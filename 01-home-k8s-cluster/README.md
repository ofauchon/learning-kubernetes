You'll find here all the details for building a kubernetes personnal home cluster.

Prior to this, let me tell me more about the objectives of this project.

 * Goals

Couple of weeks ago, I decided to learn more about Kubernetes.
Now I want to practice on real hardware, and prepare CKA administrator.

So, the this k8s cluster setup is mainy for educational purpose, and must be as cheap as possible. 4 nodes will be enough (2 control nodes, and 2 workers). 

Lot of people uses raw RPI3/4 boards, and some other uses more complex setup with CM4 compute modules (ex: turing PI boards). I like thes approaches, as they offer evolutivity, low enery consumption, little room requirements.  

But at the moment, RPI3/4 and CM4 boards are still realy expensive. 

This is why I started looking towards alternative hardware like Thin Clients. Let's see the details now.


 * Hardware

After searching the lowest priced hardware,  I ended up buying 4 HP t610 thin client.

See details here:
https://support.hp.com/fr-fr/document/c05350817

It costed me only about 250 Euros for 4 units with power supply, stand mount, and shipping,  It's a fair price for all that. 

Each device is loaded with 8Gb Ram, 128Gb SSD, and 4 cores. 
This is great for playing around with kubernetes.

The units where shipped with Ubuntu pre-loaded, which makes me confident this hardware have a good Linux compatibility. 

But I don't trust pre-installed images, so next step is to install a fresh Linux OS (and time to switch to Debian)

 * Linux OS installation

I chosed Debian 12 because I needed stability and good community support. 
 
Installation can be done with netinst image:

https://www.debian.org/CD/netinst/#netinst-stable

I won't detail here the installation steps, as it's well documented elsewhere and it's out of scope of this tutorial

After installation, you should have four linux servers on the same network. 

|hostname| ip |
|-|-|
| 192.168.0.11 | k8s-control-1|
| 192.168.0.12 | k8s-control-2|
| 192.168.0.13 | k8s-node-1|
| 192.168.0.14 | k8s-node-2|



