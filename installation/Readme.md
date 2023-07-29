
# Part One
## Install OS
1. Install Windows Server 2012 R2 64-bit [Datacenter GUI]
2. Set Administrator password as ```Maximo123```
3. Change computer Name to ```maximo.demo.com```
<img width="995" alt="image" src="https://github.com/aasem-research-work/maximo/assets/101444683/ca222415-cce4-4635-9584-d0848f057e8e">

* Restart computer

<img width="807" alt="image" src="https://github.com/aasem-research-work/maximo/assets/101444683/24ca4b86-1b5a-4011-9413-3d0d989331b0">


## Install utilities
4. Install firefox (at leaset: Firefox Setup 115.0.3) and set it as default browser
5. Install Notepad++ and Winrar 64bit
   
## Install JDK
6. Install JDK (at least: jdk-17.0,8_windows-x64_bin.exe)

# Part Two
## Extract Maximo Media
7. Extract via winrar to local directory (C:\installation\MAM_7.6.0.0_WIN64)

## Verify prerequisites
8. Change directory
```
cd C:\installation\MAM_7.6.0.0_WIN64\SystemRequirements
```

9. Execute tpae_req_check

```
tpae_req_check -input tpae.properties -mode silent -trace none -component was,asset_mgt,db2
```

# Part Three

## start with launchpad64.exe
10. Go back to the the directory having launchpad:
    
```
cd ..
```
11. lauch it

```
launchpad64.exe
```

## Install Product
12. Lauchpad opens dialog. make sure to select:
   a. Middleware: IBM DB2
   b. IBM WebSphare
   c. IBM Maximo Asset Manager v7.6
<img width="903" alt="image" src="https://github.com/aasem-research-work/maximo/assets/101444683/a22a084f-be68-4488-9ad3-a1760597c78f">

14. Click on **install IBM Maximo Asset Management components**

## Package selection
14. In *Install Packages* leave the default packages and click **Next** Button
15. Accept the licence and click **Next** Button
16. Set locations as following:
   - Shared Resources Directory: C:\IBMIBMIMShared
   - Installation Manager Directory: C:\IBMIBMIMShared\InstallationManager\eclipse
17. Make sure to replace all "C:\\Program Files" in the all paths with "C:\\IBM". This will remove warnings
<img width="964" alt="image" src="https://github.com/aasem-research-work/maximo/assets/101444683/f1b65eb6-e6d8-4e6c-a15e-35cd52834cf2">

18. In language selection screen, keep the default i.e., English
19. Verify components to be installed
<img width="656" alt="image" src="https://github.com/aasem-research-work/maximo/assets/101444683/4a68ce0b-dbee-45ef-9e5a-88b774ef72b2">

20. Set password **Maximo123** for DB2 configuration and leave all as default
<img width="982" alt="image" src="https://github.com/aasem-research-work/maximo/assets/101444683/4f942961-3ed3-4476-a989-09ebcf16d25b">

21. Leave default for IBM HTTP configuration
<img width="662" alt="image" src="https://github.com/aasem-research-work/maximo/assets/101444683/59c2a950-1710-4412-ad53-084a01a12512">

22. Verify and Install
<img width="610" alt="image" src="https://github.com/aasem-research-work/maximo/assets/101444683/7c6734e0-2ecd-4b76-8881-730796bc02bf">

23. At successful installation, a diaglog appear. 
<img width="610" alt="image" src="https://github.com/aasem-research-work/maximo/assets/101444683/3f724fcf-4fd8-44c8-a63f-6387d35f1bb8">

## Install IBM Tivoli Process Automation Engine Configuration Utility
24. Make sure to select "IBM Tivoli process automation engine configuration utility" open and click **Finish** button to start next step installation.
25. Click on **Prepare WebSphere Application Server for configuration** link
<img width="876" alt="image" src="https://github.com/aasem-research-work/maximo/assets/101444683/996c1efd-9a5a-4835-bae1-67af389e0262">

26. Leave default locations for WebSphere Application Server and click **Next** button
<img width="876" alt="image" src="https://github.com/aasem-research-work/maximo/assets/101444683/a1cb8a70-1fb8-4caa-9b5f-c562618a0a89">

27. Set password as ```Maximo123``` for *wasadmin* user. Leave default locations for WebSphere Application Server and click **Next** button
<img width="876" alt="image" src="https://github.com/aasem-research-work/maximo/assets/101444683/6a299fa5-f934-4d28-991f-25500928dab4">

28. Leave default and click **Next** button
<img width="876" alt="image" src="https://github.com/aasem-research-work/maximo/assets/101444683/d23f4e59-f2db-467c-ab66-4db57a9aea5c">

29. Leave default and click **Next** button
<img width="876" alt="image" src="https://github.com/aasem-research-work/maximo/assets/101444683/a7398352-cd2a-4389-849d-90b46c5ef130">

30. Leave default and click **Finish** button
<img width="876" alt="image" src="https://github.com/aasem-research-work/maximo/assets/101444683/e0446a10-d36e-4de2-a4f6-1b1c63ffb566">

31. Validation and Installation will start and may take approx 30 to 60 minutes
32. Click **OK** when Configuration and Deployment Complete dialog appeares
    
## Post Installation
33. Run installValidation to verify if installation was successsful
```

cd C:\IBM\SMP\ConfigTool\script
```
and execute:
```
installValidateion.bat
```

