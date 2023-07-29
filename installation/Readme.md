
# Part One
## Install OS
1. Install Windows Server 2012 R2 64-bit [Datacenter GUI]
2. Set Administrator password as ```Maximo123```
3. Change computer Name to ```maximo.demo.com```

* Restart computer

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
13. Click on **install IBM Maximo Asset Management components**

## Package selection
14. In *Install Packages* leave the default packages and click **Next** Button
15. Accept the licence and click **Next** Button
16. Set locations as following:
   - Shared Resources Directory: C:\IBMIBMIMShared
   - Installation Manager Directory: C:\IBMIBMIMShared\InstallationManager\eclipse
17. Make sure to replace all "C:\\Program Files" in the all paths with "C:\\IBM". This will remove warnings
18. In language selection screen, keep the default i.e., English
19. Verify components to be installed
20. Set password **Maximo123** for DB2 configuration and leave all as default
21. Leave default for IBM HTTP configuration
22. Verify and Install


