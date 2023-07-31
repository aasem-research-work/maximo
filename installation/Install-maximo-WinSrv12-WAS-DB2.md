# Maximo Installation on Windows Server 2012 R2 (WAS+DB2)

This tutorial will guide you through the process of installing IBM's Maximo Asset Management software. The process will be divided into four parts.

## Part One: OS and Utility Installations

In this section, we'll set up the operating system and utilities required for Maximo.

### Installing the Operating System

1. Install the 64-bit version of Windows Server 2012 R2 Datacenter GUI.

2. Set the Administrator password to `Maximo123`.

3. Change the computer's name to `maximo.demo.com`.

   ![Computer Name](https://github.com/aasem-research-work/maximo/assets/101444683/ca222415-cce4-4635-9584-d0848f057e8e)

4. Restart the computer.

   ![Restart](https://github.com/aasem-research-work/maximo/assets/101444683/24ca4b86-1b5a-4011-9413-3d0d989331b0)

### Installing the Utilities

5. Install Firefox (at least version 115.0.3) and set it as the default browser.

6. Install Notepad++ and the 64-bit version of Winrar.

### Installing the Java Development Kit

7. Install the Java Development Kit (JDK), at least version jdk-17.0.8_windows-x64_bin.exe.

## Part Two: Preparing the Maximo Media

In this section, we'll extract the Maximo media and verify the prerequisites for the installation.

8. Extract the Maximo media using Winrar to the local directory (C:\installation\MAM_7.6.0.0_WIN64).

9. Change the directory to the SystemRequirements folder within the extracted media.
```
cd C:\installation\MAM_7.6.0.0_WIN64\SystemRequirements
```


10. Execute the `tpae_req_check` command to verify the prerequisites.

 ```
 tpae_req_check -input tpae.properties -mode silent -trace none -component was,asset_mgt,db2
 ```

## Part Three: Installing Maximo

In this section, we'll go through the process of installing Maximo and configuring the IBM Tivoli Process Automation Engine.

### Starting the Installer

11. Go back to the directory containing the `launchpad64.exe` file.

 ```
 cd ..
 ```

12. Launch the installer.

 ```
 launchpad64.exe
 ```

### Installing the Product

13. When the Launchpad opens, make sure to select:
 - Middleware: IBM DB2
 - IBM WebSphere
 - IBM Maximo Asset Manager v7.6

 ![Product Selection](https://github.com/aasem-research-work/maximo/assets/101444683/a22a084f-be68-4488-9ad3-a1760597c78f)

14. Click on **install IBM Maximo Asset Management components**.

### Package Selection

15. In the Install Packages window, leave the default packages selected and click **Next**.

16. Accept the license agreement and click **Next**.

17. Set the following directories:
 - Shared Resources Directory: C:\IBMIBMIMShared
 - Installation Manager Directory: C:\IBMIBMIMShared\InstallationManager\eclipse

18. Replace all instances of "C:\\Program Files" in all paths with "C:\\IBM" to prevent warnings.

 ![Paths](https://github.com/aasem-research-work/maximo/assets/101444683/f1b65eb6-e6d8-4e6c-a15e-35cd52834cf2)

19. Keep English as the selected language in the language selection screen.

20. Review the components to be installed.

 ![Components](https://github.com/aasem-research-work/maximo/assets/101444683/4a68ce0b-dbee-45ef-9e5a-88b774ef72b2)

21. Set the password for DB2 configuration to `Maximo123` and leave all other settings as default.

 ![DB2 Configuration](https://github.com/aasem-research-work/maximo/assets/101444683/4f942961-3ed3-4476-a989-09ebcf16d25b)

22. Leave the default settings for IBM HTTP configuration.

 ![HTTP Configuration](https://github.com/aasem-research-work/maximo/assets/101444683/59c2a950-1710-4412-ad53-084a01a12512)

23. Verify the settings and begin the installation.

 ![Verify and Install](https://github.com/aasem-research-work/maximo/assets/101444683/7c6734e0-2ecd-4b76-8881-730796bc02bf)

24. Once the installation is complete, a confirmation dialog will appear.

 ![Successful Installation](https://github.com/aasem-research-work/maximo/assets/101444683/3f724fcf-4fd8-44c8-a63f-6387d35f1bb8)

### Installing IBM Tivoli Process Automation Engine Configuration Utility

25. Select "IBM Tivoli process automation engine configuration utility" and click **Finish** to begin the installation.

26. Click on the **Prepare WebSphere Application Server for configuration** link.

 ![Prepare WAS](https://github.com/aasem-research-work/maximo/assets/101444683/996c1efd-9a5a-4835-bae1-67af389e0262)

27. Leave the default locations for WebSphere Application Server and click **Next**.

 ![WAS Locations](https://github.com/aasem-research-work/maximo/assets/101444683/a1cb8a70-1fb8-4caa-9b5f-c562618a0a89)

28. Set the password for the `wasadmin` user to `Maximo123`, leave the default locations for WebSphere Application Server, and click **Next**.

 ![WAS Password](https://github.com/aasem-research-work/maximo/assets/101444683/6a299fa5-f934-4d28-991f-25500928dab4)

29. Leave the default settings and click **Next**.

 ![Default Settings](https://github.com/aasem-research-work/maximo/assets/101444683/d23f4e59-f2db-467c-ab66-4db57a9aea5c)

30. Leave the default settings and click **Finish**.

 ![Finish](https://github.com/aasem-research-work/maximo/assets/101444683/e0446a10-d36e-4de2-a4f6-1b1c63ffb566)

31. The utility will validate the installation and display a confirmation dialog.

 ![Validation](https://github.com/aasem-research-work/maximo/assets/101444683/8c72b8b4-9cb6-40e5-8a80-120b065a88c3)

## Part Four: Configuring and Validating Maximo

In this section, we'll validate the installation and configure the software.

### Verifying the Installation

32. Navigate to the script folder in the config tool directory.

 ```
 cd C:\IBM\SMP\ConfigTool\script
 ```

33. Run the `installValidation.bat` script.

 ```
 installValidation.bat
 ```

34. Open Firefox and enter `about:config` in the address bar.

35. Search for `security.tls.version.min` and double-click on the preference.

36. Change the value according to your server's TLS version and restart Firefox.

### Validating Maximo

37. Open the following URLs in Firefox and log in with the provided credentials:

- [http://localhost:9080/maximo](http://localhost:9080/maximo) (username: maxadmin, password: Maximo123)
- [https://localhost:9443/maximo](https://localhost:9443/maximo) (username: wilson, password: wilson)
- [https://localhost:9043/ibm/console](https://localhost:9043/ibm/console) (username: wasadmin, password: Maximo123)

 ![Maximo Login](https://github.com/aasem-research-work/maximo/assets/101444683/8fc60c0b-72d5-4611-a49d-5266751fd8bb)

38. Congratulations! You've successfully installed IBM Maximo Asset Management components.

