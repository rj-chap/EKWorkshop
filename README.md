# Introduction

This repo serves as the primary source of content for my BSides Las Vegas 2015 Exploit Kit Analysis workshop, a.k.a. "Exploit Kit Shenanigans: They're Cheeky!"

The files contained within this repo can be considered dangerous, and thus should not be loaded on any machine (virtual or not) that is not dedicated to malware analysis.

# Requirements

## Hardware/Software
 *"P6 chip. Triple the speed of the Pentium."*

To participate in the workshop, you don't need Acid Burn's laptop. However, you will want to bring a laptop equipped with the following:

### Preferred Hardware

1. USB port
2. Ethernet port

Please try to have a USB and Ethernet port available.  I will have USB 3.0 drives with me the day of the workshop.  These drives will be FAT-formatted (nothing fancy) and contain the files required for the workshop.  I will also pop the files into this repo (on the day of the event), but being able to grab the most up-to-date files from me would be best.

I will also have a network switch setup with numerous Ethernet cables available.  I'll have a few share types running to share files.  So basically, if you can plug in a USB drive or pop onto a private Ethernet network, you'll be fine.  (I run a Macbook, so if you want to use Airdrop, we have that option also.)

### Software: Virtual Machines (VMs)

**REQUIRED:**

You'll need some VM software: **VMware or VirtualBox** are recommended.  Within your VM environment, you'll want two (2) different VMs:

**REMnux v6 VM** (remnux.org)

PLEASE have a VM of REMnux version 6 (**VERSION 6!**) installed, updated, and ready to rock!!  Lenny Zeltser has put quite a bit of time into REMnux, which is a Linux distro whose purpose is to facilitate and ease the process of malware analysis.  You can obtain REMnux here: https://remnux.org/.

Once you import the .OVA file into VMware or VirtualBox, you'll want to run `update-remnux full`

If you are not able to have a VM of this OS ready, I will have a few copies available on USB drives.  Please note that the file will be large and the transfer will take some time.  For that matter, 

REMnux includes the following tools that we'll be using (just a taste):
 1. bash
 2. Python
 3. WireShark
 4. Firefox
 5. Firebug
 6. rhino (js)
 7. swftools
 8. jd-gui

**OPTIONAL:**

**Windows XP, 7, or 8 VM** (Windows VM on which you can run malware!)

You do not *have* to have a Windows VM with you, but I highly recommend one.  If you bring a Windows VM, you'll be able to use a few tools that are not compatible with Linux, such as ILspy and a Win-specific debugger.  The shellcode we will analyze is compatible with WinXP through Win 8.1.  You will *not* want to bring Windows 10.  Leave that at home :).

### Software: Install These!

**Install on REMnux v6**:
 1. Bless hex editor				(sudo apt-get install bless)
 2. JPEXS Free Flash Decompiler		(https://www.free-decompiler.com/flash/download/)

Please note that JPEXS FF Decompiler for Linux (`ffdec_6.0.1.deb`) requires some dependencies, including Oracle's Java 8.  Rather than grab the .deb file, you'll most likely want to grab the `ZIP (Windows, Linux, Mac OS)` version (`ffdec_6.0.1.zip`) and run the `ffdec.sh` file to install on REMnux.

**Install on Windows**:
 1. ILSpy (http://ilspy.net/) -- Required for Silverlight exploit analysis
 1. JPEXS Free Flash Decompiler	-- Required for Flash exploit analysis (not req'd if installed in REMnux)

*If you want to walk through the shellcode for one of our examples*, you will need a Windows VM on which you can run malicious code.  Meaning: DO NOT use a Windows VM that you use for personal or work purposes outside of malware analysis.  We **will** be executing malicious code on the Windows VM, so you'll want something you can simply snapshot back to a working/clean state.

*Please have one of the following debuggers installed:*
 1. Immunity Debugger	(http://debugger.immunityinc.com/)
 2. OlyDbg 1.x			(http://www.ollydbg.de/download.htm)
 3. OlyDbg 2.x			(http://www.ollydbg.de/version2.html)

Any of the three above debuggers will do the job, but I'd prefer you use Immunity Debugger.  I will have copies of all three available, but I cannot provide a copy of Windows for obvious reasons.

**OPTIONAL Windows Software**:
 1. FlashDevelop w/Adobe Flex 4.6 SDK (flashdevelop.org) -- Optional for Flash exploit analysis 
  This isn't really required.  If you want to install FlashDevelop AND the ~330MB Flex SDK, you'll be able to compile actionscript3 code, which is awesome.  I will include the re-compiled SWF we'll want to analyze, so you don't *have* to have this sucker installed.

**VERY Optional** tools for JS deobfuscation
 These most likely won't be used the day of the workshop, but they are awesome tools... so grab 'em!
 1. Revelo						(http://www.kahusecurity.com/tools/)
 2. Malzilla					(http://malzilla.sourceforge.net/)
 3. PDF Stream Dumper			(http://sandsprite.com/blogs/index.php?uid=7&pid=57)

---

**If you have any issues getting any this software ahead of time, PLEASE ping me!** We want to make sure to use our time the best we can in the workshop, so let’s work together to prep prior to the event day.

## Personal Knowledge
 **Can I Kick It? (Yes, You Can!)**

If you are a programmer, great.  If not, don’t worry.  If you have worked to deobfuscated code, fantastic.  If not, mhe.  You see where I’m going with this.  Overall, this will be an intermediate to advanced workshop in terms of skills required.  Even so, I’ll work with anyone willing to push his or herself to learn some new skills.  To gain the most from the workshop, you will want to make sure that you are somewhat familiar with the following:

**JavaScript (JS)**

We are going to be going through a LOT of JS.  If you have never touched JS before, or you are not a programmer by nature, fear not.  Please contact me for some resources, or just hit YouTube/Google/whatever for some crash course action.

**Firebug**

We will be using Firebug within Firefox.  If you are not familiar, go hit YouTube and learn some basics!  Speaking of Firebug…
 
**Debugging**
 
You’ll want to be familiar with debugging concepts such as setting breakpoints, stepping through code, etc.  If you have never run a debugger, go hit your favorite search engine and blah blah.  You know the drill.
 
**Assembly Language (ASM)**
 
Don’t worry if you’ve never touched ASM.  I’ll be going over some basics of the debugger will be using, Immunity Debugger.  I will discuss the screen layout, things to watch, etc.  That will lead into a discussion about ASM and how we can analyze the code we’re going through.  Honestly, we'll only be using the debugger for one piece of shellcode, unless we end up with extra time.

# Questions?

Hit me up!  I have **no problem** responding to inquiries/questions/etc.

Twitter: **@rj_chap**

Rock on!