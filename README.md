# Xingjian-Chen-setup-guide-ESE519
Xingjian Chen:
https://www.linkedin.com/in/xingjian-chen-64632b207/

Test platform:
Lenoveo R9000P 2021; Windows 10 CPU: AMD RYZEN 5800H GPU: Nvidia RTX3060 laptop

The prelab of lab2 is to help us setup the required programing enviorment and relevant SDK to develop the Raspberry Pi with C language. To setup these enviorment and SDK we need to install a couple of extra tool first.

To do this, we need to refer to the document with the link below:
https://datasheets.raspberrypi.com/pico/getting-started-with-pico.pdf

Hint: DO NOT follow the guide of this document from the very beginning if you are a Windows user, since the beginning of the document is the guides for Linux. To build SDK and examples, you need to refer to part:9.2. Building on MS Windows, this is the part you actually need.

Once you find the correct part to refer, here is the tools you will need.

The list of extra tools:
1. Arm GNU Toolchain
2. CMake
3. Building tool for Visual Studio 2022
4. Python 3.10
5. Git

Installation guide:

1.Arm GNU Toolchain

There are many option in the downloading page, which one should we choose? Just follow the guide, which saids download the "executable installer", therefore we should download the file with .exe
![image](https://user-images.githubusercontent.com/57385262/194974692-3d347fde-787f-46b9-a679-5060f6cc311c.png)

Then we start to install it as any other installation. However, remember to the box which saids "Add path to environment variable"
![image](https://user-images.githubusercontent.com/57385262/194974936-0ea67e73-3159-40c7-953b-c23f1be69616.png)

There you go! You have successfully installed the Arm GNU Toolchain!

2.CMake

For CMake installation, we should choose Windows x64 Installer 
![image](https://user-images.githubusercontent.com/57385262/194975342-21a2a7f9-2188-41d5-ac57-6069baeccf6e.png)

When you come to this Install Options: select Add CMake to the system PATH for all users
![image](https://user-images.githubusercontent.com/57385262/194975438-775e2843-7c56-4c3b-9e41-f4b23162e3f8.png)

Then CMake is done now!

3.Building tool for Visual Studio 2022

Just install VS2022 and remember to click the "desktop development with C++"
![image](https://user-images.githubusercontent.com/57385262/194975795-f99693fb-4ba1-404c-975e-45f1e1ac049d.png)

4. Installaton of Python 3.10

There are many version of Python 3.10 and I choose to use 3.10.7 because it is the latest verison. This could be change in the future, this part of the guide may not valid in the future
![image](https://user-images.githubusercontent.com/57385262/194976193-2a47fce0-862a-4992-84e0-ca7727150e7c.png)

When you come to this step of installation, remember to click the "Add Python 3.10 to PATH"
![image](https://user-images.githubusercontent.com/57385262/194976405-157b7925-b206-4ab0-a32e-a7443024efea.png)

5. Git

When you come to this step of setup, you should choose "Use Notepad as Git's default editor"
![image](https://user-images.githubusercontent.com/57385262/194976692-8e6af97b-b5bb-49d6-b015-01bfd5e4fc5a.png)

Once you successfully install Git, you have installed all the extra tools you need to get the SDK and examples.



To get the SDK and examples, you need to input the following command into you terminal, this could the command window in Windows10.
![image](https://user-images.githubusercontent.com/57385262/194976944-ffdbec03-5cb4-4329-8427-9233800f85fb.png)

Hint: the content behind C:/Users could be different. They show up as C:/Users/xingj in my computer, so don't get panic if you see some difference here.


There are two ways to build "Hello World" example. I choose to use Command Line to build it. Therefore, this guide will only cover how to use command line to build it.

First, you need to open your VS2022 document and find the "Developer Command Prompt for VS2020" command window in Windows10 doesn't work in this step.
![image](https://user-images.githubusercontent.com/57385262/194977496-b34890ba-ae81-44bf-8996-21ff021cf7f9.png)

Then input the following command:

![image](https://user-images.githubusercontent.com/57385262/194977538-f1b8252b-2d4a-4ac0-9c74-809920aa2ee4.png)

Next, you need to close your current command prompt window and open a new one. Then input the following command
![image](https://user-images.githubusercontent.com/57385262/194977991-8a6b11d4-8ffd-47dd-abb5-54e83e14c16a.png)
Hint:Don't miss that two dots behind!

If everything goes well, after a long time of building,you should be able to find a folder call "pico-examples". In that folder, follow the path: "../pico-examples/build/hello_world/usb", you should be able to see elf, bin and uf2 file in the folder
![image](https://user-images.githubusercontent.com/57385262/194978586-9dd46d10-c78a-405f-aa14-865cec288a01.png)

Hint: 

1.Remember, there are two "hello_world" folder, one is in the "build" folder and the other is in "pico-examples" but out of "build", the one we need is the one inside the "build" folder, in which you can see the elf, bin and uf2 file while the other is not.

2.If things are not going well, you may want to reinstall the extra tool you installed before, there could be some issue during your installation. In my case, I found that there are some problem relative to my CMake, so I unistall it and installed it again, problem solved. You can try that too if you encounter the same issue as I did.


After you build the SDK and examples, you need to reset your Raspberry Pi(by hold the BOOTSEL button and press the other button once) and connected it to your PC. The Raspberry should show up as a external drive, and then drag the hello_usb.uf2 into the drive. The Raspberry should reboot and unmount itself from your PC. 

Next, for Windows10 user, you can open your putty then setup the serial line and the speed:
![image](https://user-images.githubusercontent.com/57385262/194980633-a7cacf79-ba29-425e-b875-e9c4d22c3684.png)

click in, you should see the "Hello World" is printing on your screen!
![image](https://user-images.githubusercontent.com/57385262/194980726-f7f862f4-9655-4357-a589-22b8782ad8ec.png)

Congratulation! You have successfully setup your SDK and examples!




