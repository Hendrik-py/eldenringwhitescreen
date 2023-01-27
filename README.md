# Elden Ring White Screen Crash
This is a small documentation in which I want to collect possible fixes for the white screen crash in elden ring.
Throughout this document I will discuss the fixes I personally came across and what I did to fix them.
When you want to add to this list or figure out what issue is the root of the problem i request you to search up the program "Reliability Monitor" click on your elden ring and check for the offset code.
The idea is to link the offset code for the crash to a fix, helping people with a more structored approach then current blogs are doing.

I want to shout out Dark Breed from Steam here, he helped me a lot throughout my process and is probably still working through steam threads as you read this.
Windows 10 related event logs with elden ring

<H1>Error Offset: 0000000000d431df</H1>


reinstall them from the microsoft website

https://aka.ms/vs/17/release/vc_redist.x86.exe
https://aka.ms/vs/17/release/vc_redist.x64.exe

you will need both and both need a restart, if they are installed you get a repair option, if they are not installed you wil get a install option.


<H1>Error Offset: 0000000001e3e49d</H1>

I dreaded this one the most. This is an issue with your graphic drivers and is quite a doozy, check for the newest update on the website. DONT USE DEVICE MANAGER it wont find the update
Nvidia
For Nvidia use this website: https://www.nvidia.com/download/index.aspx Make sure you take the correct one! You can also use GeForce Experience to stay up to date. If you have the newest update, use DDU to clean reinstall your nvidia drivers. 

<H1>Error Offset :  0x0000000000234619</H1>

this means a fault related to load game files

follow the basic error fixes.

<H1>error Offset: 0x0000000001e576bb</H1>

this means a outdated dx11 GPU is in use

new GPU is needed or using unsupported dx11 GPU hack without EAC and only offline

<H1>extrem high Error Offsets like : 0x000001f04c9c3363 or 0x0000026b3215aa5</H1>

is combination with this information: Faulting module name: unknown, version: 0.0.0.0, time stamp: 0x00000000

it can be different this means a external app caused the crash (mostly trend micro, norton, avast, mcafee but also some direct RAM capture stuff cause such crashes) the offset can massively change but so many characters is always a security breach by a third party software

the solution is also differen because it depends on the software that caused it, i recommence a deinstallation of software that cause such errors and never use them again.

some explanations what is going on at different offsets because different hardware configurations can have slightly different offset for the same cause.

<H1>Error Offsets above: 00000000fffffff</H1>

From here I will mostly add what dark breed told me: "data and mostly caused by background apps that elevated apps to the wrong offset segment" I heard some people struggle with epic games, i suggest trying after uninstalling it You can also try to clean out your %temp% folder

<H1>error Offsets below  00000000100000</H1>

related to core drivers in windows

<H1>error Offsets 00000000100000 till  00000000ffffff</H1>

related to connections between windows core functions, drivers and subsystemes

<H1>Error Offset between: 000000001000000 to 000000002000000</H1>

Dark Breed: "related to GPU driver and directx communications with the windows"

<H1>Error Offset above: 000000002000000</H1>

Again for this segment i will quote dark breed as he has more insight in it then me: "related to commnication between directx and GPU driver and the transport is made by the c++ library so any 
of this 3 parts can be involved into a crash there"



<H1>windows 11 related event logs with elden ring</H1>

Faulting module name: KERNELBASE.dll
Exception code: 0xc00000fd
different fault offsets possible


this is caused by a update bug in windows 11 at preinstalled and upgraded from windows 10 the solutions are different but the error is nearly the same for both windows variations
the offset can be completely different cause is a bug in windows 11 update

<H1>Preinstalled windows 11:</H1>

the solution is to repair install windows 11 with a fresh created installation media you can hold all data and files

you will need a minimum 8GB USB stick and you have to know how to boot from it

you download the actual installation media

Download Windows 11 (microsoft.com)

<H1>upgrades from windows 10 to 11:</H1>

at upgrades it can be a variation of different things:

1: a complete reinstall of EAC with delete all registry keys chance to solve it about 37%

delete the 'EasyAntiCheat_EOS' folder in C:\Program Files (x86)
then Use Registry Editor to delete all keys and values that had 'EasyAntiCheat_EOS' to do this 
use the command
regedit

right-click on HKEY_LOCAL_MACHINE > Find and look up the term EasyAntiCheat_EOS and delete all you can find.
then go into elden ring's game files in the installation folder and navigate to easy anti cheat, and click on the

install_easyanticheat_eos_setup

a prompt will pop up and hit enter.

2: a new windows administrator profile chance to solve the problem if 1: did not worked 52%

Create a local user or administrator account in Windows - Microsoft Support 

3: remnants of windows 10 cause complete malfunction of EAC

only solution a clean complete wipe reinstall of windows 11 or a downgrade back to windows 10

this is the second possible crash only appeared at upgrade versions where a fix at the running system is impossible

Faulting module name: ntdll.dll
Exception code: 0xc0000374
different offsets possible

wipe and reinstall of windows 11 is needed or downgrade to windows 10, it seams to be related to incompatible windows 10 audiodrivers with windows 11 upgrades a uninstall of the incompatible drivers at windows 11 is not possible


at any not specific mentioned Offset error: basic error fixes

first of all you do:

verify gamefiles, restart windows, verify again

test

in some cases the verify can not fix or find a error a reinstall of the game is needed

test

windows system checkup:

open command prompt as administrator and run these two commands in this order

DISM.exe /Online /Cleanup-Image /Restorehealth

after this

sfc /scannow

test

clean driver reinstallation:

Display Driver Uninstaller Download version 18.0.6.0 (guru3d.com) 
