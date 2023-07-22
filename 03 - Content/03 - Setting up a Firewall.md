---
creation date: June 22nd 2023
last modified date: June 22nd 2023
aliases: []
tags: #📖
---

Primary Categories: [[]] 
Secondary Categories: [[]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Setting up a Firewall]]  
---

**The following is an optional activity that is not related to the BTL1 exam content.**

For this activity, we’ll be creating a brand new virtual machine that will act as a firewall. Firstly, head over to the [pfSense website](https://www.pfsense.org/download/) and download the ISO install file shown in the below screenshot. If you’re unsure what version to download for your host system, read the information at the bottom of this page.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/f7631db0355b94d37b038946d06417430880ae5abe24e5419d259d63b2cb48e17a5d470f5c945114182f70c4d117.png)

Now that we have the .iso.gz file we need to unzip it, so we can access the .iso file. If you don’t already have 7Zip installed, you’ll need to [download it](https://www.7-zip.org/download.html), install it, and use it to extract the files. You should now have the .iso file!

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/91536e9b5ce48f1d36181649c4bbc8ad629cd67d39c1a4d05fe50afee5fa13133807c3f56c8112722afc44c051c0.png)

Next, open VirtualBox and click on New in the top middle of the VirtualBox Manager windows. Name the virtual machine anything, we’ve gone with “BTL1 Firewall Exercise”, set the type as BSD, and the version as FreeBSD. If your host system is 64-bit, then download FreeBSD (64-bit).

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/7be602f754850a6399af5a9940f1a111ba6abb16fc8338e9e36694f7825a195f71457c4efa022cf1ba54c89de134.png)

The RAM minimum is 512 MB, but as we are just experimenting with pfSense it doesn’t need to have high resources to deal with traffic and operations. We suggest you set the memory size to 1024 MB. When creating a new virtual hard drive, select the VirtualBox Disk Image (VDI) file type.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/a7055d278c64a6312a8ce4994ba335421e02a459da18b5fb478f926f6ae76712c585e022127eefd4c830090c8ed8.png)

Next we need to ensure that the virtual machine is in Bridged networking mode, so that the system has it’s own IP address instead of sharing the IP of our host system. Select your new virtual machine by left-clicking on it once in the VirtualBox Manager, then click the Settings cog at the top of the window. Go to the Network tab and change from NAT to Bridged Adapter.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/453a3fae0cef1d72f3b179bbfb715c73786df891c7f259fa418f1b0d5f9fa97387c9cc117a445620a59d437bd6ad.png)

Go back to the VirtualBox Manager window, and double-click your firewall virtual machine to run it. You will be prompted with the below window, asking you to import an optical disk – this is our .iso file for pfSense! Select it, and click Choose.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/0a5fe84c025882c7d511b0bb0c6e34b92cb6f72814da1c50811b427020715923c00d127ef4331d248f945dc48d6f.png)

Follow the pfSense installer to get pfSense initialized correctly.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/8688196250f5a51186344b5c69a79ee3fa1a9caa048e52fb7d32b45b558fd7c0c92f5bef1e7e208f77b3761c766a.png)

Once the installation is complete, manually shut down the virtual machine. If you don’t it will attempt to run the installer again. To stop this, we need to open the virtual machine settings from the VirtualBox Manager and remove the .iso file we used for installation.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/6854a7516519f21ee6bde7f5fa1036a5095b9b17ab3f1ad231faeec32705ab680321f9d3e1d766e3e126aee639be.png)

Now that you can boot into your pfSense virtual machine properly, select option 1 and when asked “Should VLANs be set up now?” type “n”.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/c7e594876ca7b5c618e3eb9643c187e86cd29a9fa6c1dd39fb988ca985a4219da6b809f1972ec0a6c0fd72b8ddef.png)

When asked to enter a WAN interface name, enter “em0”, and when asked to enter the LAN interface name, don’t enter anything and press Enter. When asked to remove the LAN IP address, type “y”.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/3980e05b74bd1e4a4b18b69b50fa0e68a35d82dd45e2627a1728553217333a69f683351a19c03e4f0263ba177e8e.png)

In the below screenshot we can see that the em0 interface is enabled, and in our case we see the IP address 192.168.1.249. If you enter this IP into your browser on your host system, you will see the pfSense login portal.
![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/50a093190d7210159795638d94e76128330d9708025be8c27cb33122df847abccde03beff038111c3ccfb6e2c704.png)![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/3d56d93ef1dc6f838e9dd33a2a0c1f37c556081e6c190bea873eca3ca7084248a51c53b2cd814f0db0f82062a7be.png)
Use the username:admin and the password:pfsense to log into the management console. On the first page we are presented with the configuration wizard, which we will be following to get everything set up correctly. Click Next to begin.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/f4ce9591c9e0bf126e60cdb77c28f71fdce51fb3492d572efda11cf041dcf7160a77210764a255751871d9e8df7c.png)

Configure the setting as shown below.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/899f55b763901aa88e97b8841cdb1f5a93b35b7fa46ce88de3d49586dcb70ee4564b29056ed5f5d7d10752d2986e.png)

Leave the following settings as they are by default.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/07500274494b09b5340c6c0ace4026239cd4a32d0cd53de20c083aafade39bfac0f8e36f62c020696f901c849a62.png)

Below, we have changed the SelectedType from DHCP to Static. Under the Static IP Configuration section we have set the IP address to match the IP we’re currently using to access this web console (look at your address bar!). Make sure to change the subnet mask to 24, and the gateway as 192.168.1.1.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/d7bf3b34aec484d0a120401546d3e30e32a7f92d80ed0fc4f0f40d64c426526bd8773a1fc6d86dd8dd29b828a3b0.png)

Next, you’ll be asked to enter an admin password. We have chosen “password” for now. Then you’ll be asked to Reload pfSense with the new changes. Once this is done, we’re ready to get onto the fun stuff! ? Click on the pfSense logo in the top left-hand corner to view the Dashboard. This provides valuable information about our firewall, such as; interfaces, system, uptime, and resource usage as shown in the below GIF.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/d94d00c835c110ea82601956cd7c733cf6b98758aa66f5f952bf355099ca7b9f2ebc5f1d4566b3c2ff141ee99c14.gif)

---

# Creating Firewall Rules

From your pfSense web console, hover over Firewall on the top menu and click on Rules.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/7613ff6ce160eb304bd2778feed12bb31260c1285def2ecbecd7d9c1fcc8e5901fefc604ae951f7a5c898a07d18f.png)

As we don’t currently have any firewall rules in place, all incoming connections are blocked by default as a safety measure. We’re going to quickly cover how to write some basic firewall rules. To get started click on the left Add button at the bottom of the page. Before we actually create our own rules, we’re going to explain the properties that we can set when creating a rule.

## **Action**

There are three actions we can take with our firewall rules:

- **Pass:** Allow the traffic to pass through the firewall.
- **Block:** Prevents the traffic from passing through the firewall by dropping the connection, and not notifying the source IP (known as silent dropping).
- **Reject:** Prevents the traffic from passing through the firewall by dropping the connection, and informing the source IP.

## **Disabled**

Ticking this box will disable the rule, meaning that it is not actively used by the firewall, but the rule is not deleted so it can be enabled in the future.

## **Interface**

Choose the interface from which packets must come to match this rule. For this walkthrough, we only have a WAN interface configured.

## **Address Family**

Choose whether the rule applies to IPv4 traffic, IPv6 traffic, or both.

## **Protocol**

Which protocol this rule applies to. For example, we could block TCP traffic but allow UDP traffic. We can also choose to use Any protocol, instead of a specific one.

## **Source**

The source of the network connection the rule will apply to. For example, if we wanted to block connections to Facebook from this network, the source value would be 192.168.1.0/24, with a destination value of Facebook’s IP range.

## **Destination**

The destination of the network connection the rule will apply to. See the example under the Source heading to understand what this means.

## **Log**

We can optionally log traffic that matches this rule. If we were blocking connection to Facebook, we could log when this rule is enforced, allowing us to identify which hosts are attempting to connect to Facebook. In an enterprise, we would push these logs to a SIEM platform for centralized management and alerting.

## **Description**

We can assign a description for this rule. This is a good idea when working in teams, so that other team members can understand what this rule does, and what it’s being used for.

Now that you understand the properties we can set within a rule, let’s create a rule to block a Security Blue Team-owned domain, Redhunt.net. Open a command prompt on your Windows system, or a terminal on a Kali Linux virtual machine, and type `**ping redhunt.net**`. You can instantly press CTRL+C to stop pinging. You now have the IP address of Redhunt.net!

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/57ef10ccff720266845643f3ca5dc039fa66908383c538eb5d96ec056fba1a12f36edf7f2d73eb530bdbf162791a.png)

Hover over Firewall on the top menu, and click Aliases. Aliases act as placeholders for real hosts, networks or ports. They can be used to minimize the number of changes that have to be made if a host, network or port changes. For example, if we create an Alias for a site we want to block, we can use that as the source or destination within firewall rules. If the IP of the site changes, we only need to change the Alias instead of every single rule. In the below screenshot we have set a name and the IP address of redhunt.net.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/da14e09682ed5ace3d79e6bf066e1591b80df3e6fff2a141d402168b2a1ce6adafb119551c62dd23bf2d32d4f477.png)

Now let’s create a firewall rule to block any host in our network connecting to the redhunt.net! Copy the below settings – we will explain them below

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/6808eaa10e53ebbbf9eaebd9151610eadf34eac2dcca2fe36210e7a88928cce36f07e1e72af07b01007f2ff62445.png)

- **Action:** Block – we want to block traffic to Redhunt.net
- **Protocol:** Any – we want to block all traffic (alternatively, we could choose to just block http (TCP 80) and https (TCP 443)).
- **Source:** Network, 192.168.1.0/24 – we want to enforce this rule for any system on our private home network.
- **Destination:** Single host or alias, RedHuntDOTNet (the alias we created earlier for the IP address of the website).

Before we change our host system’s default gateway, pushing all of our traffic through pfSense, we need to think about how the firewall is currently constructed. All traffic is blocked by default with pfSense, so technically, we have two rules at the moment:

- **Block ANY traffic to Redhunt.net (3.11.197.46)**
- **Block ANY traffic**

So if we change the default gateway on our host system, we will have absolutely no internet connection, because pfSense is blocking everything. We need to create something known as an ALLOW ALL rule. This might sound scary, but remember that your host is (or should be) running a local web application firewall, which will still work to block malicious traffic. This rule means that pfSense allows communications to come in and out from the internet, giving us a connection.

> _Firewalls follow a hierarchy when it comes to rules, working from the top down. This means pfSense will inspect the traffic and apply the rules in the following order:_
> 
> _**1.** **Firewall sees that Redhunt.net is blocked. If the packet is attempting to reach out to 3.11.197.46, drop the packet to prevent the connection.**_  
> _**2. Firewall sees that all traffic is allowed.**_

Let’s create our allow-all rule. Copy the settings we have used below.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/0569309e99acabd4fdb1114aa38bfe0042ef4ae7c6c34838d874b8f5ac3dbbcfbb5b8be9432bfb2a0a7b536493a6.png)

Once this rule has been created, make sure it is placed **below** the redhunt.net blocking rule, otherwise when we change our default gateway, you’re going to lose internet connection until you restore it.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/1c070f408de19f0d34f07d441cb6c2ebc936c70ad9e401502b9c4235eabc4574eee7733602cc7d6cecb49a0a5594.png)

> _**IMPORTANT NOTE:**_
> 
> _Due to human error, during this walkthrough we encountered an issue with our pfSense virtual machine, so we had to do a fresh install. Prior to this message, our pfSense IP address was 192.168.1.249. Our new instance has the IP address 192.168.1.251._

Make sure you’ve clicked on the Save Changes button that appears at the top of the page whenever a change is made, so pfSense can update itself. Now it’s time to see if everything has worked! First, we need to understand how our home network is set up, considering both our pfSense virtual machine and our host system. In my case, I am on a wired ethernet connection, with a network named “GardenNET”. We already know the following details:

- pfSense virtual machine IP (the IP you log into the pfSense web console with): **192.168.1.251**
- pfSense upstream gateway IP address (we set this when we first logged into pfSense web console): **192.168.1.1**
- pfSense DNS server IP (we set this when we first logged into pfSense web console): **8.8.8.8**

What we need to know next is our host system’s IP address, our host system’s DNS server IP, and our current default gateway. We can open a command prompt and use the command `**ipconfig /all**` to gather the information we need.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/c80c3efc05245d147e417fcc546ba13a7585663505cadd6bd3ed676f34cfc085c3ffea3ce747c374f44bfde5d044.png)

In our case (yours may be different), our **host IP is 192.168.1.220**, our **default gateway to the internet is 192.168.1.254**, and our **DNS server is 192.168.1.254** (same as the gateway). At the moment, our host is sending traffic from 192.168.1.220 to 192.168.1.254, then out to the internet. Below is a network diagram showing how we need to configure our host to push traffic through pfSense out to the internet. We’ll explain it more below.

  
 

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/aea6b8d68e8f770bbbe0fb43c5188e7ccef913f1949624d446c38a5602f7f36efd8d4ede2c3af0ca896bc15b6d43.png)

So at the moment, our host communicates with the router at 192.168.1.254 and that’s how we have internet connectivity. Our pfSense has the default gateway we assigned earlier, which is 192.168.1.1. Sometimes your router will sit at .1 in home networks, but in our case, it is at .254. What we need to do is:

- Tell our host system to use the pfSense virtual machine (192.168.1.251) as its default gateway. Traffic outbound for the internet will now go to pfSense.
- Tell our pfSense VM to use the router (192.168.1.254) as its default gateway, giving it internet connectivity.

The new network should look like the below diagram.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/40360107f9cbf5c196fa01ea0c9b054a49582d318f69604ecb64eb2e8458343e4cf1238a9a440a4c73e48e3cb72d.png)

First things first, let’s change the default gateway in pfSense from 192.168.1.1 to the correct value, 192.168.1.254, giving us access to the internet. You can see the change we have made in the below screenshot by clicking on “Add a new gateway” and entering our router’s IP.

  
![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/6ea97845f299b2177c918e1df6f2c7f58ce7442e65edf558024977837fbc80d84b813c4ee90bceb8cb9fafb0a08a.png)

Next it’s time to update the settings for our host. In the Windows search bar, type “run” and press enter. The following popup will display.

  
 

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/4814ab0cf5835bef3e6915ac4d176a575ed954c62ae6b884558923c28e99d9191b1225eee5ee1f2ed15c5fd9e1b2.png)

Enter in “ncpa.cpl” and press enter. You should see something similar to the below screenshot. Our ethernet network connection is shown in the top right, as GardenNET.

  
![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/b83d1e01358e55f0d824b363b36090e07955fdecc71f566c922d31aad6370baa0411ba1258cfcdbb66b8aca4f793.png)

Right-click on your primary connection, and select “Properties”. Find the line that reads “Internet Protocol Version 4”, and double left-click to open a new window, shown below. Here we can change from “obtain an IP address automatically” and “obtain DNS server address automatically” to set the values we need from our pfSense system. We have shown the before and after screenshots below. We will also explain what we’ve done underneath these images.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/b1a73b4533ca87262337633b5ecedd2d7362477100662f628b3a509676587499ebc4d5c818edf8a528991b188c38.png)

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/c87be0484a398bb60e04bddf6dacb41ec0d79a057facf294dbb27e425cc10c6958446a6d03e7bba1e1643c92885f.png)

So now, our traffic is going through pfSense to the router, then to the internet. Please note your connection speed may be slower, depending on the resources you assigned to the pfSense virtual machine, as it is having to scan all traffic coming through to match it against the two rules we have created. We can now see that we can browse any other internet site except Redhunt.net! Our blocking rule has worked!

  
 

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/d1c6f090227c02eca5ff700e77f59641fce4ddc00107be61ecedccc0d33ecd3c08fc8cb39ce5605556bf62889013.gif)


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: June 22nd 2023 (08:22 pm) 
Last Modified Date: June 22nd 2023 (08:22 pm)
