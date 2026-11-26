ADB -  android debug bridge
emulator start - ~/Android/Sdk/emulator/emulator -avd Gu3ssWeak_Android14_API34
adb devices
adb shell 
adb logcat | grep whatyouwannalookfor
run-as -> bypass application sandbox
adb servers runs on 5073 port 
android 11 ke upar usb ke bina adb use kr sakti hu wireless debugging follow -> https://developer.android.com/tools/adb



android arch 
system apps
java api framework
Natice C/C++ libs
Android runtime
(HAL) Hardware abstraction layer
Linux Kernel
Power Management


mobsf use krna sikha
using same wifi dev mode me rooted phone ko connect kiya and adb use kr ke apk download kiye by using su -c "ls path" i can list the stuff aise i can use 
run-as nahi chala cause android debugger shayad off hai idk
and vo downloaded apk ko mobsf me upload kr ke dekh and it gave vuls so we just need to validate it against the vuls that were given by mobsf 

abhi main goal hoga vulnerabilities ko samjhna and vo vulnerabilities ko achese understand krna 


jadx -> decompile krta hai 

Decompile matlab -> converting the byte code into java code


actual app compile kaise hoti hai? -> Java/Kotlin Source code convert hota hai bytecode main -> which is converted to DEX (ek executable files) and phir uska Android Package banta hai 


The **.xz** file extension is a ==lossless data compression format== that typically uses the **LZMA2** algorithm to shrink file sizes.