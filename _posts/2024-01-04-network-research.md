---
layout: post
title: "Home Network (Project)"
date: 2024-01-04 23:11 +0000
categories: learning networking
description: "Complete network overhaul replacing a mesh powerline system with UniFi equipment, including research on access points, switches, gateways, VLANs, and security camera integration."
---


<a name="readme-top"></a>

<br><br>


<p><i>A table of contents  will be inserted here</i></p>


<br>




<!-- INTRODUCTION -->

<br><hr><br>

<h2 id="#Introduction" align="center">INTRODUCTION</h2>

<br><hr><br>







<br>

<!-- OVERVIEW -->

<h2 id="#overview">Overview</h2>

<p><b>Why rework the current network? </b></p>
<p>
    We have multiple networks setup within the 
    house as we have a router which has direct connections to 
    3 rooms in the house and then to a seperate mesh network. 
    The mesh network is then scattered around the house and 
    creates it's own seperate network. This means we have 2x 
    SSID's and there is conflict in the house between the 
    networks.
</p>
<p>
    The Wi-Fi in our house is currently bad when not close to 
    the router. In the furthest parts of the house the internet 
    signal is poor. When trying to setup an AP in one side of the 
    house the signal kept dropping, this is likely to the AP being 
    faulty.
</p>

<br>

<p><b>What are the plans with the new network? </b></p>
<p>
    The idea of this research is to allow for a new network to be 
    setup using only Ubiquti kit where possible or at least Ubiquti 
    AP's as they're supposed to be good and easy to manage with the 
    Unifi-controller software as it shows the network in a user 
    friendly way (showing the topology of the network, nice UI etc) 
    as well as allowing for VLAN creation for Main, Guest and IoT 
    networks.
</p>

<br><br>

<h2>Current setup</h2>

<p><b>TalkTalk ISP Router</b></p>
<ul>
    <li>Mesh network</li>
    <li>Dans room</li>
    <li>Jamies room</li>
    <li>Living room</li>
</ul>

<br>

<p><b>Mesh Network</b></p>
<ul>
    <li>Dad's office</li>
    <li>Behind TV (Front room)</li>
    <li>Extension</li>
</ul>

<br>

<p><b>Main issues:</b></p>
<ul>
    <li>2x Networks / SSID - this causes crosstalk</li>
    <li>Mesh network is powerline therefore speeds suffer</li>
</ul>




<br>

<p align="right">(<a href="#readme-top">back to top</a>)</p>









<!-- UNIFI NETWORK RESEARCH-->

<br><hr><br>

<h2 id="#unifi-network-research" align="center">UNIFI NETWORK RESEARCH</h2>

<br><hr><br>










<h2 id="typical-setups">Typical Setups</h2>

<a href="https://www.youtube.com/watch?v=kGBFkIzf6x0">YouTube: 2022 
    Complete Unifi Setup Guide</a>

<br><br>

<p>The first part of this video is useful to familiarize yourself with 
    what kit would be needed for a typical network. The second half can be used to 
    configure your network once you have all hardware setup.</p>

<p><b>Hardware used:</b></p>
<ul>
    <li><b>Unifi Cloud Gateway:</b></li>
    <ul>
        <li>UDM SE (UDM-SE)</li>
    </ul>
    <li><b>Switch:</b></li>
    <ul>
        <li>Unifi Flex Mini 5-Port (USW-Flex-Mini)</li>
    </ul>
    <li><b>Access Points:</b></li>
    <ul>
        <li>U6 Lite (U6-Lite)</li>
        <li>U6 Pro (U6-Pro)</li>
    </ul>
    <li><b>Cameras:</b></li>
    <ul>
        <li>G3 Flex (UVC-G3-FLEX)</li>
        <li>G3 Instant (UVC-G3-INS)</li>
    </ul>
</ul>

<br><br><br>

<p><b>UDM SE</b></p>

<p><b>Roles:</b></p>
<ul>
    <li>Unifi Console</li>
    <li>Unifi Controller</li>
    <li>Router</li>
    <li>Inbuilt switch</li>
</ul>

<br>

<p><b>UDM SE vs UDM Pro:</b></p>
<ul>
    <li>Integrated 8-port PoE/PoE+ switch vs no PoE
    <ul>
        <li>(6) PoE</li>
        <li>(2) PoE+</li>
    </ul>
    </li>
    <li>128 GB SSD for Unifi Protect recordings vs no SSD</li>
    <li>2.5 GbE RJ45 WAN ports vs 1Gbps on Pro</li>
</ul>

<br><br>




<br>

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<br>










<!-- UNIFI KIT-->

<br><hr><br>

<h2 id="#unifi-kit" align="center">UNIFI <br> GATEWAY | CONTROLLER | AP | SWITCH | CLOUD CONSOLE</h2>

<br><hr><br>





<br>

<!-- ACCESS POINTS -->

<h2 id="#unifi-access-points">Unifi Access Points</h2>

<a href="https://www.youtube.com/watch?v=y5I_WhnviYY">YouTube: Which is the Best AP for You? - UniFi Access Points Explained 2022</a>

<br>

<p>
    In summary this video says the U6 Lite should be used for general usage, anything else would be overkill.
</p>

<br>




<h3>WiFi Bands (2.4Ghz vs 5Ghz)</h3>

<p><b>5Ghz</b></p>
<ul>
    <li>Used for personal devices</li>
    <li>Has less range</li>
    <li>Can support higher throughput</li>
    <li>Create a personal VLAN</li>
</ul>

<br>

<p><b>2.4Ghz</b></p>
<ul>
    <li>Is used for less secure devices (IoT) / cameras</li>
    <li>Has more range</li>
    <li>Supports lower throughput</li>
    <li>Create a IoT VLAN</li>
</ul>

<br><br>

<h3>Comparison between (U6 Lite vs U6+ vs U6 Pro)</h3>
<p><b>U6 Lite</b></p>
<ul>
    <li>Wifi 6</li>
    <li>2x2 MIMO on 2.4Ghz with throughput of 300Mbps</li>
    <li>2x2 MIMO on 5Ghz with throughput of 1.2Gbps</li>
</ul>

<br>

<p><b>U6+</b></p>
<ul>
    <li>Wifi 6</li>
    <li>2x2 MIMO on 2.4Ghz with throughput of 573.5Mps</li>
    <li>2x2 MIMO on 5Ghz with throughput of 2.4 Gbps</li>
</ul>

<br>

<p><b>U6 Pro</b></p>
<ul>
    <li>Wifi 6</li>
    <li>2x2 MIMO on 2.4Ghz with throughput of 573.5Mps</li>
    <li>4x4 MIMO on 5Ghz with throughput of 4.8 Gbps</li>
    <li>Qualcomm chipset</li>
</ul>

<br>

<h3>Conclusion</h3>
<p>
    The U6 Pro seems like the best option due to the fact it has 4x4 MIMO on the 5Ghz band. Also it has a better chipset. The U6 Lite seems the be the 2nd most recommended.
</p>





<br>





<br><hr><br>



<br>

<!-- UNIFI GATEWAYS -->

<h3 id="unifi-gateways">Unifi Gateways</h3>

<h4>Do I need a Unifi gateway?</h4>

<a href="https://www.reddit.com/r/UNIFI/comments/15rgxt3/do_i_need_a_unifi_gateway/">Reddit: Do I need a Unifi gateway?</a>

<br><br>

<h4>What is a unifi gateway</h4>

<p>The USG Ubiquiti UniFi Security Gateway, is an enterprise Gateway router with Gigabit Ethernet that combines advanced security features with high performance routing technology.</p>


<p><b>Function:</b></p>
<ul>
    <li>Routing</li>
    <li>Security</li>
</ul>


<p><b>Typical usage:</b></p>
<p>ISP Modem -> USG -> Switch</p>

<br>

<a href="https://uk.store.ui.com/uk/en">UniFi Cloud Gateways</a>

<br><br>

<p>Any of the above will do the same thing as the USG I believe.</p>

<p><b>What is a Unifi Console?</b></p>
<p>From what I've read, the console is the device which sits between the modem and the switch. This is a physical piece of hardware which hosts the Unifi-Controller as well as providing other function.</p>


<br><br>







<p align="right">(<a href="#readme-top">back to top</a>)</p>

<br>

<!-- UNIFI CONTROLLERS -->

<h3 id="unifi-controllers">Unifi Controllers</h3>

<h4>What is a Unifi-Controller</h4>

This is a network management software which can be either self-hosted or runs by default on Unifi Consoles. These are usually referred to as [UniFi Cloud Gateways](https://uk.store.ui.com/uk/en).

Running the device 24/7 will allow for:
- Setting up configuraitons
- Ability to check the status of devices

Self-hosting:
- [UnifiPi](https://unifipi.com/)

Further research needed here
<br><br>


<br><br>







<p align="right">(<a href="#readme-top">back to top</a>)</p>

<br>

<!-- UNIFI SWITCHES -->

<h2 id="unifi-switches">Unifi Switches</h2>

<h3>Are Unifi switches needed?</h3>

<a href="https://www.youtube.com/watch?v=PyDpLJIKg0M">Home Network Tour with UniFi Dream Router</a>

<p>The reason you would want to use Ubiquiti switches is so that you can put them on seperate VLAN's and manage the ports inidivually from the Unifi Controller page</p>

<br><br>

<h3>Setting up the Unifi-Controller</h3>

<a href="https://unifi.ui.com/">UI Site Manager</a>

<a href="https://www.youtube.com/watch?v=lkUhWnDPutg">Self Hosted UniFi Network Application Controller Install Tutorial</a>

<p>He shows how to self host the Unifi app on a Ubuntu image and provides the code</p>

<br>

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<br>











<!-- UNIFI CLOUD CONSOLES -->

<h2 id="unifi-cloud-consoles">Unifi Cloud Consoles</h2>

<h3>Udm pro vs udm se</h3>

<h4>Cloud console research</h4>

<a href="https://www.reddit.com/r/Ubiquiti/comments/13e84s1/best_ubiquiti_
router_for_a_setup_like_mine/">Best Ubiquiti router for a setup like mine</a>

<br><br>

<p>
    It's hard to work out what routers exist within the Unifi line and if one is even 
    needed to use the full functionality of the Unifi offering. Everyone says that the 
    UDM SE is the best option which makes sense but with minimal info on what cameras are 
    needed it doesn't make sense for me. Someone suggested the UDR which I had not yet 
    heard of really.   
</p>

<br>

<p>
    Found that most people recommend the UDM SE for a "single pane of glass" experience. 
    What people mean by this is for a single interface which everything can be controlled within
</p>

<a href="https://www.youtube.com/watch?v=YSFo-DfmucM">I'm getting rid of my Unifi Dream Router…</a>

<br><br>

<p><b>He says the only differences are:</b></p>
<ol>
    <li>The UDM has 6 less PoE ports</li>
    <li>The UDM doesn't support the really high speeds (multiple Gbs)</li>
    <li>The UDM only has 128 + SD storage for cameras</li>
</ol>

<br><br>

<p align="right">(<a href="#readme-top">back to top</a>)</p>







<br><hr><br>



















<br>

<p><b>Redditor suggesting UDR</b></p>

<blockquote>
        >Duke-Kaboom · 9 mo. ago
<br>    >Is price the driving factor ?
<br>    > 
<br>    >If not .....best setup UdmProSE. Has built in Poe and extra ports for expansion as well as the ability to add cameras for protect. 3 Ap's Done
<br>    >
<br>    >If yes. Then Edge router, with separate programming of the ap's. The edge router Interface is basic looking and technical.
<br>    >
<br>    >But
<br>    >
<br>    >If you "want the full.ubiquity setup" Sounds like you are looking for the more user friendly "single pane" 
experience others have described. Then you want the Unifi OS. I'd avoid cloudkey and usg all together as they are the old Platform..
<br>    >
<br>    >Another mid range option would be go with the UDR. It has 2 Poe ports to power two AP's and it has built in Wifi to act as the 3rd AP. This will still give you the single pane experience but slightly more cost effective.
</blockquote>



<br>





<br>



I then looked up whether it's worth getting a UDM Pro or the UDM SE and found 
[Dream Machine Pro vs SE?](https://www.reddit.com/r/Ubiquiti/comments/uj20p7/dream_machine_pro_vs_se/)


Checked some comparisons [U6+ v U6 lite](https://www.reddit.com/r/Ubiquiti/comments/16sh8zc/u6_v_u6_lite/) 
and [U6+ vs U6 lite](https://www.reddit.com/r/Ubiquiti/comments/14ipulk/u6_vs_u6_lite/). There is some mention of 
the U6 Pro which sounds to be the most reliable. 


U6+ vs U6 Lite:
- U6+ has better connection
- U6 Lite uses less RAM
- U6 Lite has more RAM
- U6+ has WiFi 6 on the 2.4Ghz band


[Upgrading my setup: Looking for input on the U6 Plus vs. U6 Lite (currently sold out)](https://www.reddit.com/r/Ubiquiti/comments/14mnvu3/upgrading_my_setup_looking_for_input_on_the_u6/)

I then saw this post where a Network technician says to get the U6 Pro. I'm feeling like the U6 Pro is the most solid option and will be the most reliable

>JacksonCampbell Cake day · 7 mo. ago <br>
Network Technician
Get the U6 Pro. The U6 Lite has the inferior chipset that can have horrible performance issues. The U6+ was made as an upgrade to it in some ways and is better but no Bluetooth. U6 Pro is better than both with WiFi 6 on both bands and MU-MIMO and OFDMA.




<br><br><br><br>


<br><br><br><br>

<h4>PoE switch options</h4>

The vast majority for people say that it's not worth using injectors. The reason for this is that they cause inconsistencies in the network and can create failures which are hard to troubleshooting and can break kit if they fail - overall not worth.

I then went back to research PoE switches and saw the return of the TP-Link switch. I looked up the difference between a TP-Link switch vs a Ubiquti one to see what I'd be missing if I swapped between kit.

You may lose the ability to turn off AP's remotely and also you may lose the ability to create VLAN's with non-Ubiuti kit. These are 2 things which I plan on doing therfore I think it makes sense to get a Ubiuti switch.

It doesn't currently make sense to get a Dream Machine due to having no cameras but does make sense to get an 8 port switch like this [Lite 8 PoE](https://uk.store.ui.com/uk/en/pro/category/all-switching/products/.usw-lite-8-poe) as an in the middle step.

I found this guide which spoke about whether it's worth getting a  [Unifi switch or not?](https://www.reddit.com/r/Ubiquiti/comments/171btbv/unifi_switch_or_not/)

>Amiga07800 . 3 mo. ago <br>
>The 16 ports has a VERY low PoE budget than won’t be enough for you. You have some other options:
>1. Swap UDM Pro for the SE - 95W PoE on 8 ports - and eventually add a non PoE UniFi switch
>2. Use TWO USW-Lite-8-PoE, 104W PoE budget,” 
>
>Beside, I REALLY suggest to swap the U6+ for the U6-Pro, they are vastly superior (and have a Qualcomm chipset)

This guy suggested the U6 Pro's which I think are the better option now and also suggested either the 8 port switch or a UDM SE.

<br><br><br><br>

<h4>Conclusion from research</h4>

<p>
    I don't much more research is required here. I Will do some final checks tomorrow but I think this should all now be ok to order. I will setup search alerts on eBay over the coming weeks to try to get some money off of the AP's as they sell for £135 instead of £154. Also I might be able to pickup the 8 port switch from a 3rd party site without paying the £10 delivery fee which Ubiquti charge.

    In regards to setting up a Unifi Controller I will run this on my laptop and will think about a solution for this long term. I have a couple of cheap Raspberry Pi's so maybe able to use one of these to turn the docker image as self-hosted controller to keep it up 24/7.

    The plan is to setup 3x networks. 5Ghz networks for phones, this will be our primary network for laptops/tablets/mobiles. Another 2.4Ghz network which will be used for IoT devices. An additional guest network. I think Ubiquti has an easy setup option for this but I'll likely refer back to the video at the top of this article and then also fine some other information on ideal network setups.

    I will add more sections to this as I configure the network and also after buying kit to put the price I paid for everything.
</p>


<br>



<a href="https://www.youtube.com/watch?v=wi_geRfabAs">YouTube: Unifi Home Network Upgrade - Why I finally switched</a>

<br>

<p>

</p>

He spoke about the fact that you could use [linuxserver/unifi-controller](https://hub.docker.com/r/linuxserver/unifi-controller) and run a docker image which you use to run the Unifi-controller.

Checked reddit about this and found [Docker Vs. Raspberry Pi for Controller?](https://www.reddit.com/r/Ubiquiti/comments/xwhtka/docker_vs_raspberry_pi_for_controller/). In the initial statement the user said about hosting the docker image on a synology NAS. Someone in the comments posted a link to [Self-host the Unifi Controller on a Synology NAS](https://www.wundertech.net/self-host-the-unifi-controller-on-a-synology-nas/).

I'm thinking that I may not need a CloudKey and could save 200 if I do decide to get cameras. Either way I think I'll order the access points then go from there. Something important to note is that the **firmware should be updated** if kit is bought as this can prevent issues right away.

<br><br>

### Placing an order

**Thoughts when ordering** <br>
Order placed for 3x [U6+ Access Points](https://uk.store.ui.com/uk/en/products/u6-plus). From here we can then see if anything else is required and can also tune the equipment on arrival. I was going to order 2 however 3 should be fine as if 2 is enough for the house, one can go in the garage.

**Order cancellation** <br>
I found out how to [cancel my order](https://www.reddit.com/r/Ubiquiti/comments/m5s0bx/cancelling_order/) as I forgot to add a switch. I done some more digging and found that people were reporting issues with the U6+ so decided against re-ordering.

<br>

[U6+ vs U6-Lite oddities](https://www.reddit.com/r/Ubiquiti/comments/16d0yi4/u6_vs_u6lite_oddities/)

**RAM differences** <br>
Read this article which says about RAM differences between the U6+ U6 Lite and there is mention of the Pro too. Sounds like it goes U6+ then U6 Lite and then the U6 Pro in terms of how much RAM each has.

**Band usage** <br>
Someone also said in another article about there being issues with 2.4Ghz and saying that the AP's perform way better on 5Ghz. I'm struggling to find any more info about this and cannot find the post I read it on.

<br>

[Recommended hardware to meet Unifi POE requirements?](https://www.reddit.com/r/Ubiquiti/comments/13srj0d/recommended_hardware_to_meet_unifi_poe/)

**Struggling to understand PoE** <br>
Trying to understand how PoE works at the moment so that whatever AP's I get I don't have to run cables to. This would neaten things up a little.
<br><br>

### Power Requirements

The [Flex Mini](https://uk.store.ui.com/uk/en/pro/category/all-switching/products/usw-flex-mini) requires **2.5W** per unit and I'm planning on getting **2** units which would be a total of **5W**

The [U6+](https://uk.store.ui.com/uk/en/products/u6-plus) requires **9W** per unit and I'm planning on getting **3** units which would be a total of **27W**

Overall Total: **32W**

<br><br><br><br>

<h4>PoE Switch vs PoE Injector</h4>

[Cheap POE Gigabit Switch 8 Ports?](https://www.reddit.com/r/HomeNetworking/comments/s3oyea/cheap_poe_gigabit_switch_8_ports/)

I found what I thought I was looking for. When searching for cheap PoE switches someone suggested what I was looking for, an 8 port PoE switch. 4 of the ports are PoE and the other 4 are not. It has an overall max power of 64W which would be fine for my usage as I only need 32W as calculated earlier. This would allow for an additional 32W with the remaining 1 port so maybe this could be used to beam Wi-Fi to the garage.

I later realised that this was not fit for purpose as all kit needs to be Ubiquti. 

Having a Ubiquti switch allows:
- Manual power cylcing of PoE devices
- VLAN assignment to port number
- 

<br><br><br><br>

<blockquote>
    >flywithabuzz · 2 yr. ago <br>
    Technically you don't need a PoE switch if you're only planning to use 2 PoE devices. You can get PoE injectors for $10-$15 each....but now you also need to provide power to each of those injector bricks. It's in your best interest to get an 8 port switch with 4 PoE if you're serious about potentially needing 2 more PoE ports.
    >
    >Also, if you're running cameras, I would highly recommend getting a managed 8-port switch so you can setup VLAN tagging to have better control of who those cameras are sending data.
    >
    >[Managed 8 Port Switch: $69.99](https://www.amazon.com/TP-Link-TL-SG108PE-Shielded-Lifetime-Protection/dp/B01BW0AD1W/)
    >
    >Unless you're buying used, the breakdown for getting PoE is:
    >
    >8 Port Switch : $16.99
    >
    >8 Port Switch w/4 PoE :$64
    >
    >1 PoE Injector: $15
    >
    >8 Port Switch + 4 PoE Injectors: $ 16.99+$45 = $61.99
</blockquote>


<br>

<a href="https://www.reddit.com/r/HomeNetworking/comments/s3oyea/cheap_poe_gigabit_switch_8_ports/">Cheap POE Gigabit Switch 8 Ports?</a>

<br>


In the above post there was some information regarding security cameras / NVR's

>vrtigo1 · 2 yr. ago <br>
Good advice about putting cameras in their own VLAN. If you're using a PC-based DVR like BlueIris, another simpler option for someone that doesn't know anything about VLANs, managed switches, trunk ports and/or firewall ACLs would be to just segregate the entire physical camera network to its own switch, then put two NICs in the DVR PC. Connect 1 NIC to the main network and the other to the camera network. This isn't as secure as putting all the cameras in their own VLAN but it should still prevent them from connecting to the Internet or other devices on the LAN.


<br><br><br>

<h4>Summary of [chat with GPT](https://chat.openai.com/share/c2721371-04a1-4077-9682-901431bbcbe9):</h4>
<ul>
    <li>The Flex Mini is powered via PoE but doesn't provide PoE power</li>
    <li>Flex mini can powered via USB-C or PoE</li>
    <li>PoE sources include, PoE Switch, Router with PoE or an Injector</li>
    <li>EdgeRouter is not part of the Unifi line, this is for ISP's</li>
    <li>Went through power requirements, Ubiquiti has all power requirments on their product pages</li>
    <li>Negatives of using a TP-Link for the PoE switch</li>
</ul>

<br>





<br>

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<br>












<br><br><br><br><br><br><br>

<h3>Unifi Protect research</h3>

<a href="https://www.youtube.com/watch?v=BbmrdY2lA5k">YouTube: Unifi Protect G5 bullet review</a>

<br>

<p>
    The g4 bullet is better than G5 as it's higher res / looks better at night. There is a comparison on the video
</p>


<br><br>


<h4>Chat with GPT (storage requirements)</h4>

<p>
    I then wondered how much storage will be needed to store 1 months worth of footage for 2x G4 cameras which are recording in 2k for a month straight. I asked GPT this and the following is a 
    link to the chat. <a href="https://chat.openai.com/share/b955b46b-bae4-4b3d-984e-a2b84a373c51">link to ChatGPT</a>
</p>


<h4>Summary of chat</h4>

<p>
    1GB of storage per day so ~30GB per month. This is not very much if you're planning on deleting the footage when not needed. Using a dream machine would be overkill for this if you're not requiring other features it offers.
</p>

<br>

<p>
    Watched a tutorial on how to setup Unifi Protect so that the footage is streamed to the Synology camera system <a href="https://www.youtube.com/watch?v=AJYEy093Cdo">Adding Cameras to Synology from Unifi</a>
</p>




<br><br><br><br>

<h4>Buying G3 camera</h4>

<p>
    I just went and bought a G3 Flex camera for £35 which I found on facebook marketplace. I've just plugged into the PoE switch but just remered you cannot self 
    host Unifi Protect therfore need to wait until the UDR arrives before I'm able to adopt it.
</p>

<br>

<p>
    The next thing to buy will be either a UDM SE to replace the UDR or to get a CloudKey Gen 2 if we choose to have more cameras / the UDR does not have enough storage or RAM.
</p>


<br><br>





<a href="https://www.youtube.com/watch?v=nQSbUTwbCdE&">DONT buy/upgrade to the Unifi G4 doorbell pro just yet..!</a>



<h4>Pro differences:</h4>
<ol>
    <li>Cost over 100+ more</li>
    <li>Has 8MP package sensor</li>
    <li>Can be powered with PoE</li>
    <li>Better microphone quality</li>
</ol>

<br>

<a href="https://www.reddit.com/r/Ubiquiti/comments/15ynub5/ubiquiti_vs_ring/">Ubiquiti vs Ring?</a>



<p>
    People say not to look at Ring as it's owned by Amazon. Also you have to pay a monthly subscription cost of £3.49 to store footage.
</p>


<br>

<h4>Price from Retailer & Ebay</h4>

<table>
    <td>
        <tr>**Model** | **Retail** | **New** | **Used**</tr>
        <tr>Ubiquiti G4 | £189.18 | £150 | £120</tr>
        <tr>Ring Gen 2 | £99.99 | £45 | -</tr>
    </td>
</table>










<br><br>







[Help me decide between Unifi G3 cameras or something like Blink / Arlo etc](https://www.reddit.com/r/homeautomation/comments/7gp6vk/help_me_decide_between_unifi_g3_cameras_or/)

Ubiquiti vs Blink or Arlo

- Wireless (Blink & Arlo) require battery replacements
- Wireless (Blink & Arlo) will degrade Wi-Fi quality when you have multiple
- Cameras should be at least 9ft away from the ground (installed via ladder)
- Storing footage of the interior of your home is a privacy concern
- Ubiquiti has an inferior NVR to someone like Blue Iris
- Locally stored footage can be stolen by a thief



<p align="right">(<a href="#readme-top">back to top</a>)</p>



<br>














**Purchases** <br>

**Date** | **Model** | **Price** | **Platform**
10/01/24 | Ubiquiti UniFi 6 Pro Access Point (U6-Pro) | £117 | ebay
13/01/24 | Ubiquiti UniFi 6 Pro Access Point (U6-Pro) | £129.99 | ebay
16/01/24 | Ubiquiti Unifi Flex Mini Switch (USW-Flex-Mini) | £29.29 | ebay
20/01/24 | Ubiquiti UniFi Dream Router (UDR) | £228.60 | 4gon

**Total Price** <br>
£



<br>










Download the Unifi-controller from [Self-Hosting a UniFi Network Server](https://help.ui.com/hc/en-us/articles/360012282453-Self-Hosting-a-UniFi-Network-Server#:~:text=Start%20the%20newly%20installed%20UniFi,Adopt%20your%20first%20UniFi%20device.)

19:36 - managed to finally adopt the device after mutliple resets of the device. Had to plug it directly into the router rather than into the wall port in the kitchen.












Managed to connect to the AP

You have to create a new network from within the Unifi Controller

Wifiman is not working when viewing the signal strength of floor plan pages on my phone within the app

downloaded wifiman on my macbook, it still is not doing signal strength and floor plan













unboxed the 8 port poe switch

If I'm unable to use the PoE from the switch I can always use the PoE injector which came with one of the AP's that I bought

Found this video [Unifi Gigabit Managed Switch Lite 8 PoE](https://www.youtube.com/watch?v=lWM0KnAQ8gA) where he says that if you plug your laptop/desktop into the switch you can adopt it that way

The switch then updated itself after I tried to Adopt it

Adoption failed

Found a guide which says about using SSH to connect to the switch

[Why does my UniFi hardware tell me "Adoption failed"? (3 Solutions!!)](https://www.youtube.com/watch?v=WHdyKfuouDI)

Guice on how to setup SSH keys

[UniFi - Adding SSH Keys to UniFi Devices](https://help.ui.com/hc/en-us/articles/235247068-UniFi-Adding-SSH-Keys-to-UniFi-Devices)

Found this guide regarding connecting to the switch via SSH

[Unifi Switch CLI Commands](https://www.youtube.com/watch?v=H68f4HZMGH8)

The above was a little technical and also vague in regards to resolving failed adoption issues

[Different ways to adopt unifi devices](https://www.youtube.com/watch?v=4p96fPY-8RY)

This guys is really good and broke things down. Installed LAN Scan from the appstore to view devices on my network

When scanning I could not find the device even though it was plugged into my laptop via a port replicator

Tried to plug it into the router again, it then said getting ready and adopted












### Fixing WiFiman

I need to read this when researching "Ubiquiti WiFiman"

[I’ve turned on WiFiMan support and I’m connected to a UniFi Network, any ideas why Signal Mapper is grayed out/how to fix this?](https://www.reddit.com/r/Ubiquiti/comments/v3p33c/ive_turned_on_wifiman_support_and_im_connected_to/)







### Test results from Dan's room

Tested the WiFi in Dan's room with the AP under the router

SSID: Test
Download: 56.02 Mbps
Upload: 17.38 Mbps

SSID: private
Download: 7.26 Mbps
Upload: 6.03 Mbps

SSID: TALKTALK
latency error






### UDM vs UDR

[UniFi Dream Machine vs UniFi Dream Router \| which is the right router for you?](https://www.youtube.com/watch?v=nML_kqFpRSQ)

You can only use Unifi networking stuff and cannot run protect as well when using the UDM therefore it is not fit for purpose

[UDR Fail or Success?](https://www.youtube.com/watch?v=E6K2nITRdeA)

He had issues which were resolved with a software update














Last night setup

Router -> 8 port PoE switch -> AP (Router)
                            -> AP (Kitchen)

Connected some devices up too, all work. The speeds are no better in the lounge for some reason (they were pretty much maxed anyway)

When looking at the client list there are some random devices which were only showing their MAC addresses with no additioanl information

I tried to kick these off then network but they rejoined. I've checked my apple watch and it was connected therefore it must have been shared by my phone / macbook

changed the SSID then the switch was stuck offline








**Auto-connecting MAC addresses** <br>
noted down mac addresses for connected devices and gave them friendly name

going to later set it up so that they auto connect to the network











<br>

**Unblocking a device** <br>
I found out how to unblock a device. The device will appear in the offline section when going to the "Client Devices" option from the left hand sidebar then choosing offline from the top navigation bar.

The blocked devices will appear with a red dot next to them.

![unblocking-device-new-GUI-1](/img/network-research/unblocking%20a%20device%201.png)

![unblock-device-new-GUI-2](/img/network-research/unblock%20a%20device%202.png)


**Setup pt19** <br>
23/01/24 | start 18:14 | end 

On review - check guest settings (it said about hotspot settings)

<br>

Modem -> router -> camera + 8-port-poe-lite

<br>

**Setting up the UDR** <br>
- Setup the UDR via the Unifi Network app
- Created a new SSID when setting up the UDR
- Reset all devices for re-adoption
- Re-adopted all devices
- Updated UDR via Unifi Protect mobile app
- Wiped adoption for G3-Flex
- Managed to adopt 8-port-poe-lite via Unifi Network app
- Adpopted devices: UDR, 8 port switch, 4 port switch, G3 Flex
- Stopped running the local server, from site selector it went grey
- Adopted U6 pro in Dan's room

<br>

**Wiring** <br>
- Wired everything into an extension lead

<br><br>

## Network Configuration
Explanation on all advanced settings within the Unifi-Controller <br>
[UniFi's Advanced Wi-Fi Settings Explained](https://www.reddit.com/r/Ubiquiti/comments/r0dh9p/unifis_advanced_wifi_settings_explained/)

**Reasons for creating a VLAN** <br>
1. **Security:** <br>
If a less secure device like a **Chrome casts**, **Printers** etc is hacked, it will not have access to the rest of the network which has devices like computers, phones, tablets etc are on.
2. **Congestion:** <br>
The more devices added to the network, the more congestion. 

<br><br>

### Creating IoT Network
1. Disable "Auto Scale Network"
2. Gateway/Subnet mask = 192.169.2.1 -> 192.168.107.1

**Advanced Configuration:** <br>
1. Auto -> Manual
2. VLAN ID = 2 -> 107
3. Multicast DNS = Enable
    - This will allow devices on the main network to discover devices on the IoT network. This allows the communication between the devices and facilates things like streaming to chrome cast from mobile phone.
4. "Add Network"

<br><br>

### Creating Guest Network
1. Disable "Auto Scale Network"
2. 192.168.2.1 -> 192.168.10.1

**Advanced Configuration:** <br>
1. VLAN ID = 2 -> 10
2. Network Type = Guest Network
    - This tells the devices that they're alone and that they cannot see any devices on the network. The only thing they can see is the internet. Two devices which are both on the guest network cannot communicate.
3. Disable Multicast DNS
    - Don't want these devices to be able to communciate with chrome cast etc
4. Add Network

<br><br>

### Creating Cameras Network
1. Disable "Auto Scale Network"
2. 192.168.2.1 -> 192.168.20.1

**Advanced Configuration:** <br>
1. VLAN ID = 2 -> 10
2. Disable Multicast DNS
3. Add Network

<br><br>


## WiFi Networks

### Main network
1. Settings>WiFi>Create New
2. Network = Default
3. Create WiFi Network

<br>

### IoT Network
1. Settings>WiFi>Create New
2. Add "_IoT" onto the end of the network name
3. Network = IoT
4. Turn 5Ghz WiFi band off
    - IoT devices generally connect better to 2.4Ghz networks. They struggle with combined SSID's (2.4Ghz + 5Ghz under the same network name)
5. Create WiFi Network

<br>

### Guest Network
1. Settings>WiFi>Create New
2. Add "_Guest" onto the end of the network name
3. Network = GuestNet
4. Create WiFi Network

<br>

## Firewall Rules

<br><br>

**WiFi Connectivity** <br>
- Mapped out the house on my phone 2x times
    - Kitchen AP not picked up
    - Dan's room AP not picked up



<br>

**MAC address privacy** <br>
[[Solved] UniFi Binding: Dealing with MAC Randomization](https://community.openhab.org/t/solved-unifi-binding-dealing-with-mac-randomization/128816)

I found out that Apple hide the MAC addresses for their devices by giving the router a fake MAC address.

<br><br><br><br>


<h3>Roadblocked</h3>

<p>
    Spoke to my Dad this evening to let him know that it's hard to proceed any 
    further given that depending on the camera requirements this will dictate what 
    networking equipment to go. If we're definitley going to get cameras then it 
    makes most sense to get a UDM SE to avoid buying switches seperate to the NVR 
    which will be needed to store the footage from the cameras. Also it will work 
    out cheaper than getting all individual parts and will also make for a cleaner 
    setup overall as it's basically an all in one setup.
</p>






<br><br><br><br><br><br><br><br><br><br><br>

Research <br>
27/01/24 | start | end 15:31

- recabled network station
- setup powerline adapter from sofa to tv
- moved IoT devies to the IoT network
- Removed the powerline network
- created new patching table

<br>

Research <br>
27/01/24 | start 19:35 | end 19:55 |

- sstp vs utp 

<br>

Research <br>
27/01/24 | start 21:58 | end  | -15 min

- setup firewall rules
- fixed unifi-controller toplogy by unplugging AP
- Could not find threat managment
- Could not work out how to change to legacy layout
- Tested the motion detection, had to adjust the activation sensitivity to high

<br>

Continuation of [2022 Complete Unifi Setup Guide](https://www.youtube.com/watch?v=kGBFkIzf6x0&t=711s)


### Unifi-Network Configuration

**Firewall Rules** <br>

**Path:** Security>Firewall rules>LAN>Create Entry


**Block IoT from LAN** <br>

![block iot from lan configuration](/img/network-research/firewall%20rules/Block%20IoT%20from%20LAN.png)

**Block LAN from IoT** <br>

![block lan from iot configuration](/img/network-research/firewall%20rules/Block%20LAN%20from%20IoT.png)

**Block cameras from LAN** <br>

![block cameras from lan configuration](/img/network-research/firewall%20rules/Block%20cameras%20from%20LAN.png)

**Block LAN from Cameras** <br>

![block lan from cameras configuration](/img/network-research/firewall%20rules/Block%20LAN%20from%20cameras.png)

**Block cameras from IoT** <br>

![block cameras from iot configuration](/img/network-research/firewall%20rules/Block%20cameras%20from%20IoT.png)

**Block IoT from Cameras** <br>

![block iot from cameras configuration](/img/network-research/firewall%20rules/Block%20IoT%20from%20cameras.png)

**Setting up exclusions** <br>
https://youtu.be/kGBFkIzf6x0?si=1dfBgWGH6QZrm8Xg&t=1436

You might want to do this if you want an apple tv which is on the IoT network to be able to see a Plex server which is on the main network

Follow above

**Threat Management** <br>
Turn this on

Trying to find where it's located on the UDR

**Mapping ports to VLAN's** <br>
This can be easily done

<h3>Unfi-Protect Configuration</h3>



<p><b>G3 Flex > Recording:</b></p>
<ul>
    <li>Recording mode = always</li>
    <li>Frame Rate = 25 (max)</li>
    <li>Image Quality = 100% (max)</li>
</ul>

<br>

<p><b>Motion detection settings:</b></p>
<ul>
    <li>1 second</li>
    <li>10 seconds</li>
    <li>10 seconds</li>
</ul>

<br>

<p><b>G3 Flex > Settings:</b></p>
<p><b>Camera:</b></p>
<ul>
    <li>Status light = disable </li>
</ul>

<br>

<p><b>Overlay Information:</b></p>
<ul>
    <li>Time = enable </li>
    <li>Name = enable </li>
    <li>Logo = disable</li>
</ul>


<p><b>Instant cameras: </b>The instant cameras can go on the main network as they're WiFi 
    cameras and will generally be left indoors</p>

<br>

<p><b>Night vision:</b></p>
<ul>
    <li>Activation Sensitivity = high</li>
</ul>

<br>

<p><b>Testing: </b>When testing the recording at night it didn't pick me up on low when creeping
</p>


<br><br><br><br><br><br><br>


<details>

<p><b>Initial Research pt1</b></p>
<p>04/01/24 | start 21:45 | finish 23:37 | 1 hour 53 minutes</p>
<ul>
    <li>Overview</li>
    <li>Not sure what else, I moved the content around</li>
</ul>

<br>

<p><b>Research pt2</b></p>
<p>05/01/24 | 19:46 | 23:35 | 1 hour 29 min</p>
<ul>
    <li>Found out about self hosting unifi-controller from Docker</li>
    <li>Self-hosting from Synology NAS</li>
    <li>Update firmware to avoid adoption issues</li>
    <li>Might be able to avoid buying a seperate NVR by self-hosting</li>
    <li>Placed order for U6+ then cancelled the order</li>
    <li>Researched U6+ vs U6 Lite</li>
    <li>Further PoE research</li>
    <li>Researched power requirements</li>
    <li>PoE switch vs Injector</li>
</ul>

<br>

<p><b>Research pt3</b></p>
<p>09/01/24 | 20:44 | 22:55 | 2 hours 11 minutes</p>
<ul>
    <li>Researched how to setup Unifi Protect</li>
    <li>Further research on UDMP vs UDM SE</li>
    <li>Researched U6+ vs U6 Lite and found out that U6 Pro is the most reliable</li>
    <li>Researched different bands (2.4Ghz and 5Ghz)</li>
    <li>Reasearched MIMO</li>
    <li>U6 Pro vs U7 Pro</li>
    <li>PoE vs Injectors</li>
    <li>Conclusion from research</li>
</ul>

<br>

<p><b>Research pt4</b></p>
<p>13/01/24 | start 15:54 | end 18:24 | 2 hours 30 minutes</p>
<ul>
    <li>Researched benefits of buying Ubiquiti switches
    <ul>
        <li>Seperate VLAN management per port</li>
        <li>Restart devices via PoE</li>
    </ul>
    
    <li>How to self-host the controller on Ubuntu</li>
    <li>Watched another summary video of a home setup</li>
    <li>Watched another vs video the UDMP vs the UDMSE</li>
</li>
</ul>

<br>

<h4><b>Research pt5</b></h4>
<p>13/01/24 | start 22:14 | end unsure</p>
<ul>
    <li>Researched the best Unifi router</li>
    <li>Found that the UDR could be an option</li>
    <li>Encountered roadblock which affects ordering kit</li>
</ul>

<br>

<h4><b>Research pt6</b></h4>
<p>14/01/24 | start 9:28 | end 11:52 | 2 hours 24 minutes</p>
<ul>
    <li>Researched cameras</li>
    <li>Researched how WISP's work</li>
    <li>Researched QNAP vs Synology</li>
    <li>Researching Unifi Protect on Synology NAS</li>
    <li>Researching self-hosting services</li>
</ul>

<br>

<h4><b>Research pt7</b></h4>
<p>14/01/24 | start 17:34 | end 18:15 | 41 minutes</p>
<ul>
    <li>Patched network port into the wall</li>
</ul>

<br>

<h4><b>Research pt8</b></h4>
<p>15/01/24 | start 7:55 | end 8:02 | 7 minutes</p>
<ul>
    <li>Researched camera install in a doctors office</li>
</ul>

<br>

<h4><b>Research pt9</b></h4>
<p>19/01/24 | start 18:56 | end 19:37 | 41 minutes</p>
<ul>
    <li>Downloaded the unifi-controller then self-hosted it from my macbook</li>
    <li>Fixed issues when setting up the Access Point by 
        wiring it directly into the router</li>
</ul>

<br>

<h4><b>Research pt10</b></h4>
<p>19/01/24 | start 20:53 | end 00:17 | 3 hours 24 minutes</p>
<ul>
    <li>Created new network within unifi-controller</li>
    <li>Encountered adoption issues</li>
    <li>Researched how to SSH to switch</li>
    <li>Installed LAN Scan to find the IP</li>
    <li>Tried to reset and power cylce the switch again which 
        resolved the issue</li>
    <li>Tried to fix WiFiman</li>
    <li>Tested the Wi-Fi from brothers room</li>
    <li>Researched the difference between UDM and UDR</li>
    <li>Researched how to configure the network</li>
</ul>

<br>

<h4><b>Research pt11</b></h4>
<p>20/01/24 | start 11:15 | end 12:30 | 1 hour 15 minutes</p>
<ul>
    <li>Setup PoE switch</li>
    <li>Tested speeds from the living room</li>
    <li>Assessed currently connected clients to setup Alias'</li>
    <li>Realised that the MAC addresses were changing</li>
</ul>


<br>

<h4><b>Research pt12</b></h4>
<p>20/01/24 | start 15:33 | end 15:45 | 12 minutes</p>
<ul>
    <li>Noted down MAC addresses so that I may be able to 
        setup auto-connecting or something similar like my 
        work has</li>
</ul>

<br>

<h4><b>Research pt13</b></h4>
<p>20/01/24 | start 19:16 | end 21:20 | 2 hours 4 minutes</p>
<ul>
    <li>Researching how to unblock devices</li>
</ul>


<br>

<h4><b>Research pt14</b></h4>
<p>20/01/24 | start 21:20 | end 21:41 | 21 minutes</p>
<ul>
    <li>Styling network-research page</li>
</ul>

<br>

<h4><b>Ring gen 2 vs Unifi G4 (non-pro) pt15</b></h4>
<p>20/01/24 | start 22:35 | end 23:07 | 32 mins</p>
<ul>
    <li>Researched G4 doorbell vs G4 Pro doorbell</li>
    <li>Researched Ubiquiti vs Ring doorbells & prices</li>
</ul>

<br>

<h4><b>Updating the Table of contents pt16</b></h4>
<p>21/01/24 | start 8:36 | end 10:26 | 1 hour 50 minutes</p>
<ul>
    <li>Researched how to make a table of contents</li>
</ul>


<br>

<h4><b>Fixing formatting pt17</b></h4>
<p>21/01/24 | start 11:29 | end 15:09 | 3 hours 40 minutes</p>
<ul>
    <li>Styling network-research page</li>
    <li>Researched Ubiquiti vs Blink / Arlo</li>
</ul>

<br>

<h4><b>Fixing formatting pt18*</b></h4>
<p>21/01/24 | start 21:53 | end 23:17 | 1 hour 24 minutes</p>
<ul>
    <li>Styling network-research page</li>
    <li>Moved all time tracking to the bottom of the page</li>
    <li>Continued to sort out the contents section</li>
    <li>Commited page at pt18</li>
</ul>

<br>

<h4><b>Formatting</b></h4>
<p>09/02/24 | start 18:35 | end 18:51 | 16 minutes</p>
<ul>
    <li>Planning headings</li>
</ul>

<br>

<h4><b>Creating firewall rules to allow speakers through IoT</b></h4>
<p>12/02/24 | start 21:38 | end 22:38 | 60 minutes</p>
<ul>
    <li>Figured out how to allow certain addresses through the firewall</li>
</ul>

<br>

<h4><b>Converting page from markdown to HTML</b></h4>
<p>12/02/24 | start 22:38 | end 23:20 | 58 minutes</p>
<ul>
    <li>Removed Table of contents</li>
    <li>Converted the whole time tracking section</li>
    <li>Reworded and reformatting the Overview section</li>
</ul>

<h4><b>Formatting document</b></h4>
<p>13/02/24 | start 22:00 | end 00:20 | 2 hours 20 minutes</p>
<ul>
    <li>Reformatted overview</li>
    <li>Added current setup with main issues</li>
    <li>Added headers between horizonal rules</li>
    <li>Reformatted typical setups</li>
    <li>Grouped most unifi research</li>
</ul>

<br>



</details>