# Shodan.io

 Shodan is a search engine that lets users search for various types of servers (webcams, routers, servers, etc.) connected to the internet using a variety of filters.

Some have also described it as a search engine of service banners, which is metadata that the server sends back to the client.

This can be information about the server software, what options the service supports, a welcome message or anything else that the client can find out before interacting with the server.

<img width="1886" height="918" alt="image" src="https://github.com/user-attachments/assets/ba08faf8-556d-44b5-a80c-adf22376e577" />


### Short on time? Here’s what you need to know about Shodan and how to secure your networks in 2026:

Shodan is a database of billions of publicly available IP addresses, and it’s used by security experts to analyze network security. If you’re terrified to discover that your internet-connected devices could be exposed to absolutely anyone, here are some tips to keep your network as secure as possible:

> `Limit your devices to local-only connections.` Many internet of things (IoT) devices don’t need to go online and can be set to only share information with other devices on your home or business network.

> `Change your login details`. Many IoT devices, routers, and other web-facing tools ship with generic passwords that can be easily cracked. Get a good password manager like Dashlane or 1Password and generate complex, unique passwords for all of the devices on your network.

> `Minimize service banner information`. Many devices share a dangerous amount of information in their web-facing service banners. You can easily remove unnecessary information from your banners and limit the amount of information available to IP-trawlers like Shodan.

> `Use a network firewall`. A properly configured firewall can block unauthorized users from accessing any of the devices in your network. If you don’t currently have a firewall, I’d recommend the one that comes with Norton 360.

> `Use Shodan`. Shodan’s free membership can give you some information, but the affordable paid membership is more helpful — it grants access to on-demand scanning, which can tell you exactly what information Shodan gets from a specific IP address.

Shodan is a search engine, like Google, but instead of searching for websites, it searches for internet-connected devices — from routers and servers, to Internet of Things (IoT) devices, such as thermostats and baby monitors, to complex systems that govern a wide range of industries, including energy, power, and transportation.

Shodan can find anything that connects directly to the internet — and if your internet-facing devices aren’t protected, Shodan can tell hackers everything they need to know to break into your network.

But Shodan wasn’t designed by hackers, and hackers aren’t usually the ones using it. Hackers use similar port-crawling tools to invade internet-connected devices (if you’re trying to keep your home or office safe from network intrusion, I highly recommend using an advanced antivirus with endpoint protections like Bitdefender or McAfee).

Because of its public nature and relatively simple user interface, Shodan is a crucial resource used by cybersecurity experts to help protect individuals, enterprises, and even public utilities from cyber attacks.

Anyone can search for any internet-connected devices using Shodan, and Shodan will let you see if something is or isn’t publicly available. But keep in mind that searching with Shodan is a little more complicated than a basic Google search. 

## What Is Shodan?

Shodan is a search engine similar to Google.

But while Google searches for websites, Shodan searches for devices that are connected to the internet. Users can perform a search using the Shodan search engine based on an IP address, device name, city, and/or a variety of technical categories. Users can sign up for free accounts, but they are very limited — Shodan limits its free service to only 50 search results.

Shodan started in 2003 as a pet project for a young computer programmer, John Matherly. Matherly figured out a way to map each device connected to the internet by constantly crawling the web for randomly generated IP addresses, and he eventually developed a search engine to search through his growing database of internet-connected devices. Matherly released Shodan to the public in 2009.

Matherly’s intention was never to create an easy way for hackers to discover devices and infiltrate them, but as soon as Shodan was up and running, it began discovering industrial supervisory control and data acquisition (SCADA) systems, security cameras, traffic lights, and other sensitive devices that shouldn’t have been publicly accessible.

Once Matherly discovered how many devices were exposed online, he began marketing Shodan to IT workers to help them analyze and troubleshoot network vulnerabilities.

> * Note: Home networks aren’t especially susceptible to this kind of port crawling, but if you want to keep your devices as secure as possible, you should use an advanced antivirus like Norton that can map out every device on your network and warn you of suspicious connections.

## How Does Shodan Work?

Shodan works by requesting connections to every imaginable internet protocol (IP) address on the internet and indexing the information that it gets back from those connection requests.

Shodan crawls the web for devices using a global network of computers and servers that are running 24/7.

An IP address is your device’s digital signature — it’s what allows Google to tailor searches to your location, and it’s what allows all internet-connected devices to communicate with each other (VPNs like ExpressVPN hide your IP address so that you can’t be tracked by your ISP or other browser-tracking tools online).

Internet-connected devices have specific “ports” that are designed to transmit certain kinds of data. Once you’ve established a device’s IP address, you can establish connections to each of its ports. There are ports for email, ports for browser activity, ports for printers and routers — 65,535 ports in all.

When a port is set to “open”, it’s available for access — this is what allows your printer to establish a connection with your computer, for example. The computer “knocks” at the open port, and the printer sends a packet of information called a “banner” that contains the information your computer needs to interact with the printer.

Shodan works by “knocking” at every imaginable port of every possible IP address, all day, every day. Some of these ports return nothing, but many of them respond with banners that contain important metadata about the devices Shodan is requesting a connection with.

Banners can provide all sorts of identifying information, but here are some of the more common fields you will see in a banner:

+ Device name:  What your device calls itself online. For example, Samsung Galaxy S21.
+ IP address:  A unique code assigned to each device that allows the device to be identified by servers.
+ Port #:      Which protocol your device uses to connect to the web.
+ Organization: Which business owns your “IP space”. For example, your internet service provider or the business you work for.
+ Location: Your country, city, county, or a variety of other geographic identifiers.

Some devices even include their default login and password, make and model, and software version, which can all be exploited by hackers.

> ### What Can You Find on Shodan?

Any device connected to the internet can potentially show up in a Shodan search.

Since Shodan went public in 2009, a pretty large community of hackers and researchers have been cataloging the devices they’ve been able to find and connect with on Shodan — things like:

* Baby monitors
* Internet routers.
* Security cameras.
* Maritime satellites.
* Water treatment facilities.
* Traffic light systems.
* Prison pay phones.
* Nuclear power plants.

Before you freak out and go hide in a bunker, remember that Shodan merely indexes publicly available information. Yes, it can show users a nuclear power plant’s server banner, but that doesn’t mean that anyone with an internet connection can cause a nuclear meltdown. In the case of industrial computers and old SCADA systems, many of them are protected by passwords, two-factor authentication, firewalls, and strict security protocols.

However, Shodan does reveal just how much of our information is publicly available. If your webcam is internet-facing and you haven’t changed its default logins, hackers can access it without your knowledge, gaining an easy window into your home. In fact, webcams are one of the most commonly searched terms on Shodan’s “Explore” page. This is another reason why it’s so important to use an antivirus program like Norton which can flag network vulnerabilities and give you a warning if other apps or users are accessing your webcam or microphone.

Editor's Note: ExpressVPN and this site are in the same ownership group.

> ### How to Use Shodan Search Engine

Performing a search on Shodan isn’t as simple as performing a Google search. Google has refined its technology to be as user-friendly as possible, while Shodan is designed with IT professionals in mind.

To test Shodan, I wanted to find all Cisco devices in New York City. I started off with a simple search for: [Cisco]. But I didn’t really feel like sorting through the millions of results myself.

<img width="768" height="397" alt="image" src="https://github.com/user-attachments/assets/0ddc5c70-54cf-4ffc-87ad-7b6960063408" />

So I went a step further and used a simple search for [“Cisco” and “New York City”].

<img width="768" height="234" alt="image" src="https://github.com/user-attachments/assets/e7fcdb66-2a75-4269-a716-a0890bbcc905" />

As you can see, I didn’t find what I was looking for since I know that there are Cisco servers in New York City. The reason for this is that Shodan didn’t translate my query to mean, “Cisco servers in New York City”, like Google would have done. To search for specific keywords in specific locations, you need to use Shodan’s search filters.

With Shodan, users have to type their search filters out in the search bar in order to customize their queries.

Here are some basic search filters you can use:

> +  city: find devices in a particular city.
> +  country: find devices in a particular country.
> +  geo: search for specific GPS coordinates.
> +  hostname: find values that match the hostname.
> +  product: search the name of the software or product identified in the banner.
> +  os: search based on operating system.
> +  port: find particular ports that are open.
> +  before/after: find results within a timeframe.


So when I finally searched: [Cisco city:“New York”], Shodan returned the following results:

<img width="768" height="426" alt="image" src="https://github.com/user-attachments/assets/1a75623e-d94a-4105-ba2d-f61b97a0a601" />


Using search filters is the best way to search on Shodan quickly and efficiently, but you have to register for an account with Shodan to get access to them. There are 4 Shodan plans, with different number of query credits (you need those to use search filters and request result pages beyond the first one) and scan credits (1 scan credit lets you scan 1 IP):

+  Free account. Two pages of search results, limited filters.
+  Membership. One-time fee for lifetime use gives you 100 query credits and 100 scan credits per month.
+  Freelancer. This subscription gives you 10,000 query credits, scanning and network monitoring for up to 5,120 IP addresses (that is to say, 5,120 scan credits) per month.
+  Small Business. This subscription comes with 200,000 query credits and 65,536 scanning credits per month, plus a vulnerability scanning tool.
+  Corporate. This highest-tier Shodan plan gives you unlimited results, scanning and network monitoring for up to 327,680 IP addresses, access to all search filters, and premium customer support.

## What Is Shodan Used For?

Shodan is most commonly used to help users identify potential security issues with their devices.

Businesses and consumers both use more and more internet-connected devices every day — this is especially true due to the rise in remote working in recent years. As we become more plugged in, our chances of falling victim to a malicious attack get higher.

By identifying all of the devices connected to the internet, displaying what information those devices are sharing with the public, and making it clear how easy that information is to access, Shodan can help users to reinforce their security in a variety of ways:

>  Home Security. Discover how many devices in your home are publicly accessible (chances are your printer and your baby monitor don’t need to connect with the entire internet!).

>  Enterprise Security. Shodan can serve as an incredibly helpful tool for a company’s IT team by identifying every endpoint in the enterprise’s system and ensuring all of the banners are as secure as possible.

>  Infrastructure Management. By using Shodan, government and private sector professionals can ensure that all of their systems, from traffic systems to power grids, are secure and that all backdoors have been closed. Shodan can also be useful for finding legacy computer systems that are redundant or unnecessary.

>  Market Research. Businesses can track the distribution of their devices or software using Shodan, whether that’s Google tracking how many internet-connected devices are running Android or a thermostat company trying to figure out how many of its smart thermostats are still running.

>  Academic Research. Academics and cybersecurity professionals can use Shodan to analyze what kind of devices are connecting to the internet, what kind of software they’re using, and identify trends in security, device usage, and the overall makeup of the internet.

IT professionals frequently use Shodan to monitor networks for vulnerabilities — Shodan can be set up to alert users whenever a new device pops up in their network, giving security staff the opportunity to analyze and close vulnerabilities before hackers can access them.

Shodan is also extremely useful when it comes to patching vulnerabilities — when Microsoft’s Exchange servers were hacked by zero-day threats in March of 2021, experts were able to quickly put out a patch and close the server vulnerabilities. Using Shodan, security experts were able to determine how many Exchange servers had updated their software and patched the vulnerability, and they could also see how many servers were out-of-date and still vulnerable to the exploit.

However, home users looking to secure their network won’t find Shodan very useful. Most home network attacks rely on malware and exploits to gain access to a user’s devices — if you’re a home user wondering how to lock down your network, I recommend you check out our list of the top 10 antiviruses in 2026 and download a security solution like Norton or Bitdefender that can provide the kind of home network security you’re looking for.


> ### Can Shodan Expose Your Private Data?

Yes, absolutely. But it’s not likely. Shodan has made identifying IoT devices accessible to anyone with an internet connection and a web browser. And because a shocking number of devices connecting to the internet are unprotected, the potential for your webcam and other devices to be hacked without your knowledge is high.

Unfortunately, there are many individuals out there who will use Shodan with malicious intent. They will attempt to hack baby monitors, webcams, and security systems — and once they have access to a device in your network, they can violate your privacy, install malware on your system, and steal your identity. This is why it’s important to use a home internet security solution with real-time malware detection and identity theft protection like Norton or McAfee.

But the good news is that Shodan can only discover devices that have open ports — most home routers don’t need to have open ports, so your computer and router probably won’t appear on Shodan. It’s very important to check for your IoT devices, which are often set up to automatically provide communications with the greater internet.

Shodan has been repeatedly used by researchers to demonstrate vulnerabilities at the professional and home level. A quick search reveals Shodan users gaining access to webcams, automated greenhouse watering systems, baby monitors, smart fridges, and more. In my short time with Shodan, I was able to find webcam feeds of adults undergoing home medical care, baby monitoring cams, and even my local school district’s servers (fortunately, their banners didn’t reveal any important information!).

It’s important to note that the banner grabbing technology that Shodan uses is publicly available, and Shodan performs the most minimal data grabbing possible. Hackers use botnets to crawl networks for vulnerabilities in the exact same way that Shodan does. But hackers search exclusively for software vulnerabilities that will allow them to invade your networks, while Shodan’s vulnerability scan is hidden behind an expensive paywall.

Shodan is simply a publicly available tool that shows us what hackers have been able to find out about our devices for years.


> ### Best Ways to Remove Your IoT Devices from Shodan

You’d have to disconnect your devices from the internet to completely remove them from Shodan’s searches — but it’s pretty easy to limit the amount of information that Shodan can get from your devices.

Here are some techniques you can use to remove as much of your information from Shodan’s databases as possible:

>  Limit the number of devices connected to the internet. While it may seem that every device needs to have an internet connection today, many of them can actually be given local-only access to your network with no change in functionality. Printers, thermostats, baby monitors, and many other devices will work just fine connecting with your devices on your home network.

>  Change your login details. Many IoT products ship with generic passwords that are easily hacked. Make sure all of your internet-facing devices are protected with complex and unique passwords, and consider using a password manager like Dashlane to keep your data well protected and organized.

>  Limit the details in service banners. Service banners expose a lot of information about your hardware. Fortunately, many devices have built-in software to manage the data shared online. By trimming unnecessary data from your banner, you limit the intel that platforms like Shodan can collect.
Use a network firewall. Make sure that your network has a properly configured firewall. This will prevent unauthorized requests from being able to access any of the devices located behind the firewall. If you don’t currently have a firewall, I’d recommend the one that comes with Norton 360.

>  Use Shodan. Sign up for a free account and run a search against your household or company. You can find your IP address under your Wi-Fi network properties and then run the search: [net:IP Address]. However, if your router’s ports are closed (which they probably are), then Shodan won’t have any information. By paying for a membership, you can get access to on-demand scanning, where Shodan tells you exactly what information it gets from a specific IP address.
