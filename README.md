# Integrated Design Project / Capstone Project

## 1.Project Description
<p><center>In today's digital age, mobile devices have become an integral part of our lives. They enable us to stay connected, access information, and perform various tasks on the go. However, with the increasing reliance on mobile devices, corporate organizations and parents are faced with the challenge of ensuring a secure and controlled mobile environment. This requires addressing concerns such as unauthorized app installations, unrestricted website access, privacy risks associated with bloatware and Google services, and the need for effective device management. To address these challenges, we have undertaken the development of a custom ROM specifically tailored for corporate companies and parents. This custom ROM aims to provide enhanced control mechanisms and prioritize privacy and security, empowering organizations and parents to create a safe and productive digital ecosystem.</center></p>

## 2.Project Procedure
Our project is divided into three phases: 
- Research
- Development 
- Testing
<p><center>
The research phase involves understanding the current state of the art and identifying the requirements of our target users. The development phase involves the implementation of the custom ROM. The testing phase involves the evaluation of the custom ROM.</p></center>


## 3.Project Deliverables
<p><center>Our project will deliver a custom ROM that can be installed on Android devices. The custom ROM will be developed using the Android Open Source Project (AOSP) and will be based on the latest version of Android. The custom ROM will be designed to provide enhanced control mechanisms and prioritize privacy and security. The custom ROM will be evaluated using a combination of quantitative and qualitative methods.</center></p>

## 4.Project Team
Our project team consists of three members 
- Fathma Khatun Mim
- Gourob Roy
- Md. Arik Rayhan
<p><center>
All three members are students of the Department of Computer Science and Engineering at BAUET. Md. Arik Rayhan is the team leader. Fathma Khatun Mim is the project manager. Gourob Roy is the project coordinator.
</center></p>

## 5.Project Steps
### 5.1. Research Phase
<p><center>The research phase involves understanding the current state of the art and identifying the requirements of our target users.After completing the research we choose the Nokia 2.2 as our target device. We planed to develop the ROM for children and corporate companies. We also planed to develop the ROM based on Android 11 because thats the lastest version for this phone.</center></p>

### 5.2. Development Phase
#### 5.2.1. Setting up the development environment
For the OS we used windows 11. We used the following tools to set up the development environment:
- A Good Computer, Better Network Connection and a Good usb cable
- <a href="https://github.com/mdarikrayhan/IDP/blob/main/Driver/15_Second_ADB_Installer_v1.5.6.zip">15 seconds minimal ADB</a>
- <a href="https://github.com/mdarikrayhan/IDP/blob/main/Driver/Mediatek_Driver_Auto_Installer_v1.1352.zip">Mediatek Driver Auto Installer</a>
- <a href="https://developer.android.com/studio/releases/platform-tools">Android SDK Platform tools</a> 
- <a href="https://github.com/bkerler/mtkclient">MTK Client by Bkerler</a>

The platfrom tools need to be placed at C:\adb and for the MTK Client we need to install the <a href="https://www.python.org/downloads/">Python</a> ,<a href="https://git-scm.com/downloads">Git</a> and <a href="https://github.com/daynix/UsbDk/releases/">USB DK</a>. 

#### 5.2.2. Unlocking the bootloader
- Step 1: Do a full backup of your device using 
<a href="https://github.com/mdarikrayhan/IDP/blob/main/Required%20Software/SP_Flash_Tool_v5.1924_Win.zip">SP Flash Tool v5.1924</a>

- Step 2: The firmware for this procedure can be downloaded <a href="https://sourceforge.net/projects/fihsw-mtk/files/WSP/HCTSW_WSP-1680-0-00WW-B01_600WW_9_20191005_huaqin_ZAL1670.full.lzma2.d056631a.7z/download">here</a>.SHA256: D056631A8A795A06795B3A4E5F334DBF9B55C3C71269831F8E7926FA3ABA5637

- Step 3: Do backup of of these 5 images from the phone using "altunlock-MT6761_Android_scatter.txt" and SP Flash Tool v5.1924
  - nvcfg.img
  - nvram.img
  - proinfo.img
  - protect1.img
  - protect2.img
Please follow the procedure in <a href="https://xdaforums.com/t/guide-how-to-convert-your-nokia-x5-to-global-nokia-5-1-plus-unbrick-guide.3858253/">this topic</a> to do readback:

- Step 4: Format all + Download to flash the firmware with altunlock scatter file 
          Switch to Download tab, and choose format all + download to flash the entire phone with this scatter file: "altunlock-MT6761_Android_scatter.txt" Once flash complete, disconnect the phone.

- Step 5: Bootloader unlock


