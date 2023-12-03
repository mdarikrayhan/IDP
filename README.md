# Integrated Design Project

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

#### 5.2.2. Unlocking the bootloader on (Android 9)
- Step 1: Do a full backup of your device using 
<a href="https://github.com/mdarikrayhan/IDP/blob/main/Required%20Software/SP_Flash_Tool_v5.1924_Win.zip">SP Flash Tool v5.1924</a>

- Step 2: The firmware for this procedure can be downloaded <a href="https://sourceforge.net/projects/fihsw-mtk/files/WSP/HCTSW_WSP-1680-0-00WW-B01_600WW_9_20191005_huaqin_ZAL1670.full.lzma2.d056631a.7z/download">here</a>.

- Step 3: Do backup of of these images
  - use "altunlock-MT6761_Android_scatter.txt" and SP Flash Tool v5.1924
    - nvcfg.img
    - nvram.img
    - proinfo.img
    - protect1.img
    - protect2.img
  - Please follow the procedure in <a href="https://xdaforums.com/t/guide-how-to-convert-your-nokia-x5-to-global-nokia-5-1-plus-unbrick-guide.3858253/">this topic</a> to do readback.

- Step 4: Format all + Download to flash the firmware with altunlock scatter file 
  - Switch to Download tab, and choose format all + download to flash the entire phone with this scatter file: "altunlock-MT6761_Android_scatter.txt" Once flash complete, disconnect the phone.

- Step 5: Bootloader unlock
  - Press and hold volume down key and connect to PC - keep that condition for around 12 seconds then the phone will boot to Fastboot mode.
  - Open command prompt and type the following command:
    - fastboot flashing lock_critical
    - fastboot oem unlock
  - Look at your phone and press volume up to confirm unlock. Once done, disconnect the phone and remove the battery, wait 5 seconds and place the battery back.

- Step 6: Do readback again
  - Use "unlock-MT6761_Android_scatter.txt" and SP Flash Tool v5.1924
    - sec1.img
    - seccfg.img
  - Please follow the procedure in <a href="https://xdaforums.com/t/guide-how-to-convert-your-nokia-x5-to-global-nokia-5-1-plus-unbrick-guide.3858253/">this topic</a> to do readback.

- Step 7: Flash the firmware again
  - Extract the firmware and open the folder, copy the following files to the extracted firmware folder:
    - nvcfg.img
    - nvram.img
    - proinfo.img
    - protect1.img
    - protect2.img
    - <a href="https://github.com/mdarikrayhan/IDP/blob/main/Android%209.0/1.Boot%20and%20NvData/MT6761_Android_scatter_Stock_Rom.txt">MT6761_Android_scatter_Stock_Rom.txt</a>
  - Open SP Flash Tool v5.1924 and select mode "Format all + Download"
  - Click on "Choose" and select the scatter file "MT6761_Android_scatter_Stock_Rom.txt" and click on "Download"
  - Connect the phone in BROM mode
    - Shut down the phone, and after 5 seconds, press and hold both volume up and down keys (without the power button) and connect the phone to your computer via cable while still holding the volume buttons.
  - Wait for the flash to complete, and disconnect the phone.

#### 5.2.3. Unlocking the bootloader on (Android 11)
- Step 1: After the flash is complete on Android 9, boot the phone and update to Android 11 via OTA.

- Step 2: Open MTK Client folder and open a CMD window there by typing in cmd in the address bar. then write python mtk_gui and hit enter.

- Step 3: Connect the phone in BROM mode
  - Shut down the phone, and after 5 seconds, press and hold both volume up and down keys (without the power button) and connect the phone to your computer via cable while still holding the volume buttons.
  - The phone will be failed at first try, so disconnect the phone and repeat the procedure again. The phone will be detected as MediaTek USB Port (COMx) in Device Manager.

- Step 4: Read partitions
  - Click on Read Partitions tab and select the following partitions:
    - Boot_a
    - Boot_b 
    - sec1 
    - seccfg
  - click on Read partitions button in the right side, and choose a location to save these partitions

- Step 5: Unlock the bootloader
  - After everything is backed up, go to "Write partitions" tab, and find sec1 and seccfg, click on "set", browse and select the respective unlocked partitions we got in Step 6 of 5.2.2. (you may need to change their extension from .img to .bin for them to show up).
  - Click on "Write partitions", and done! You have unlocked your OEM on Android 11!! and if everything is done correctly, you'll see
    - Orange state Your device is unlocked and cannot be trusted Your device will boot in 5 seconds...
  - Now you can reboot your phone and enjoy your unlocked bootloader!

#### 5.2.4. Installing the TWPR recovery
- Step 1: Download the <a href="https://github.com/mdarikrayhan/IDP/blob/main/Android%2011.0/TWRP/1.Installl%20on%20Android%2011.0/twrp.img">twrp.img</a> and <a href="https://github.com/mdarikrayhan/IDP/blob/main/Android%2011.0/TWRP/1.Installl%20on%20Android%2011.0/vbmeta.img">vbmeta.img</a> files.
- Step 2: Extract the <a href="https://github.com/mdarikrayhan/IDP/blob/main/Required%20Software/platform-tools_r34.0.5-windows.zip">platform-tools_r34.0.5-windows.zip</a> and copy the twrp.img and vbmeta.img files to the extracted folder.
- Step 3: power off your phone, then boot into fastboot by holding Volume down + Power for a few seconds, until it says FASTBOOT MODE

- Step 4: Connect your phone to your PC via USB cable

- Step 5: Open a command prompt in the folder where you have the twrp.img and vbmeta.img files. To do that, hold shift + right click on any empty white space inside the folder, and select Open command window here from the context menu.

- Step 6: Type the following commands in the command prompt window and hit Enter after each line:
  - fastboot --disable-verity  --disable-verification flash vbmeta vbmeta.img 
  - fastboot flash boot twrp.img 
  - fastboot reboot recovery

- Step 7: Your phone will now reboot into TWRP recovery. If you see a prompt asking you to swipe to allow modifications, swipe it to allow modifications. We will root the phone using Magisk, which is a systemless method and does not modify the system partition.

#### 5.2.5. Rooting the phone using Magisk
- Step 1: Download the <a href="https://github.com/topjohnwu/Magisk/releases/">Magisk APK</a> file and install it on your phone.

