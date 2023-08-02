# Apply Interim Fix

## Shut down the Maximo application server
- navigate to https://localhost:9043/ibm/console 
- login as user: wasadmin, password: Maximo123
- Goto All servers, check MXServer.* and click **stop** button

## Run IBM Installation Manager
Navigate to:
- Windows: ```C:\IBM\InstallationManager\eclipse\IBMIM.exe```
- Linux: ```/opt/IBM/InstallationManager/eclipse``` directory, then run ```./IBMIM```

## Select and Apply 
- From the Installation Manager main window, select File > Preferences...
- Click Add Repository
- Click Browse and navigate to the location of the interim fix compressed file, and click Open.
- Browse to interim fix location
- In the Add Repositories dialog box, click Apply, and then click OK.
- At the Installation Manager main window, click Update.
- In Update Packages, select the package group to update: in this example, IBM Tivoli's process automation suite.
- Click Next.
- Follow the onscreen instructions to complete the installation. The following images show progress bars leading to the Update Packages screen.
- When the installation is complete, exit IBM Installation Manager.
