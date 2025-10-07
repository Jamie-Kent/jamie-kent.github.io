---
layout: post
title: Smart Home
date: 2024-03-11 20:40
categories: learning smart-home
description: "Guide to setting up a self-hosted smart home system using HomeBridge on an Orange Pi, including configuration for Tapo smart devices and integration with Apple HomeKit."
---

<a name="readme-top"></a>

<h2>Table of Contents</h2> 

<ul>
    <li><a href="#overview">Overview</a></li>
    <li><a href="#research">Research</a>
    <ul>
        <li><a href="#homebridge-setup">Homebridge Setup</a>
        <ul>
            <li><a href="#audio-capture">text</a></li>
        </ul>
        <li><a href="#tutorial-gathering">text</a></li>
    </li>
    </ul>
    <li><a href="#research">Research</a>
        <ul>
            <li><a href="#">text</a></li>
        </ul>
    </li>
</ul>

<br>

<h2 id="overview">Overview</h2>


<p>This is going to be about everything smart home related
</p>


<p align="right">(<a href="#readme-top">back to top</a>)</p>


<h2 id="homebridge-setup">Homebridge setup</h2>
<p><a href="https://www.youtube.com/watch?v=oH86kP6mLeE">Setting up Orange Pi</a></p>
<p><a href="https://www.reddit.com/r/homebridge/comments/11pxy06/homebridge_on_a_orange_pi_zero/">Setting up HomeBridge on the Orange Pi</a></p>

<br>

<p><b>Steps to install:</b></p>
<ol>
    <li>Downloaded Ubuntu for Orange Pi from the Orange Pi website</li>
    <ul>
        <li>This went to a google drive link - installed bionic and xenial</li>
    </ul>
    <li>Installed Balenca Etcher as it's needed to flash the Micro SD</li>
    <li>Flashed it onto the Micro SD however it wasn't appearing to work</li>
    <li>Reformatted the MSD</li>
    <li>Flashed Armbian Bookworm onto it - <a href="https://www.armbian.com/orange-pi-zero/">Armbian Bookworm CLI 6.6.20</a></li>
    <li>Power cycled the Orange Pi after about 5 - nothing was happening</li>
    <li>Tried to setup PuTTY</li>
    <ul>
        <li><a href="https://www.puttygen.com/download-putty#Download_PuTTY_for_Mac_and_Installation_Guide">PuTTY Website</a></li>
        <li><a href="https://rajivverma.me/blog/tech/how-to-install-putty-on-macbook-air-m1/">Setup Guide</a></li>
        <li><a href="https://developer.apple.com/download/all/">Apple Developer link</a></li>
        <li><a href="https://download.developer.apple.com/Developer_Tools/Xcode_15.3/Xcode_15.3.xip">Xcode 15.3</a></li>
        <li><a href="https://download.developer.apple.com/Developer_Tools/Command_Line_Tools_for_Xcode_15.3/Command_Line_Tools_for_Xcode_15.3.dmg">Command Line Tools for Xcode 15.3</a></li>
        <li><a href="https://www.macports.org/install.php">MacPorts</a></li>
        <li><a href="https://www.xquartz.org/">xquartz</a></li>
    </ul>
</ol>

<br><br>

<p>Installing PuTTY</p>

<ul>
    <li>Move Xcode from Downloads to Applications</li>
    <li>sudo xcodebuild –license</li>
    <li>sudo port -d selfupdate</li>
    <li>sudo port install putty, press y to install dependencies</li>
    <li>cp /opt/local/bin/putty ~/Desktop/putty (creates desktop shortcut)</li>
    <li>Install xquartz</li>
    <li>Ran PuTTY and connected to the orange pi by finding it's IP from router</li>
</ul>

<br><br>
    
<p><a href="https://github.com/homebridge/homebridge/wiki/Install-Homebridge-on-Debian-or-Ubuntu-Linux#prerequisites">HomeBridge Install Guide</a></p>

<ul>
    <li>curl -sSfL https://repo.homebridge.io/KEY.gpg | sudo gpg --dearmor | sudo tee /usr/share/keyrings/homebridge.gpg  > /dev/null</li>
    <li>echo "deb [signed-by=/usr/share/keyrings/homebridge.gpg] https://repo.homebridge.io stable main" | sudo tee /etc/apt/sources.list.d/homebridge.list > /dev/null</li>
    <li>sudo apt-get update</li>
    <li>sudo apt-get install homebridge</li>
    <li>hostname -I (to find IP)</li>
    <li>Create an account @ "IP:8581"</li>
</ul>

<p><a href="https://www.atpeaz.com/tp-link-tapo-smart-plug-work-on-apple-home/">Setting up Tapo on HomeBridge</a></p>

<ul>
    <li>Go to Plugins then install "TPLink Tapo" (verified)</li>
    <li>Go to the settings section then press configure</li>
    <li>For the name I entered "Tapo Smart Platform"</li>
    <li>Fill in email account for Tapo</li>
    <li>Add all IP addresses for your smart products</li>
    <li>Power cycle HomeBridge then it'll pull through all devices</li>
</ul>

<br>

<p>This needs to be reviewed tomorrow</p>

<p>Installed Unifi-Protect</p>



<br><br><br><br><br><br><br><br>

<details>
    
<summary> <b>Time tracking</b> </summary>
<br>
<h4><b>Research 1</b></h4>
<p>11/03/24 | start 20:40 | end 23:13 | 2 hours 33 minutes</p>
<ul>
    <li>created the initial page</li>
    <ul>
        <li>installed OS onto Orange Pi</li>
        <li>Research Homebridge</li>
        <li>Flashed the OS onto MSD with BalencaEtcher</li>
        <li>Started setting up PuTy pre-reqs</li>
    </ul>
</ul>

<br>

<h4><b>Research 2</b></h4>
<p>14/03/24 | start 22:00 | end 01:02 | 3 hours 2 minutes</p>
<ul>
    <li>created the initial page</li>
    <ul>
        <li>Install PuTTY</li>
        <li>SSH'd to the device then installed HomeBridge</li>
        <li>Installed Tapo from the plugins</li>
        <li>Configured the Home app</li>
    </ul>
</ul>

<br>

</details>