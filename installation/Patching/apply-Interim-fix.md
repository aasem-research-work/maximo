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


## start the configuration program
- Windows: Use Start > Programs > Tivoli's process automation suite > Configuration Program (default location C:\IBM\SMP\ConfigTool\ConfigUI.exe)
- UNIX: In the <installLocation>/ConfigTool directory run ConfigUI, for example, /opt/IBM/SMP/ConfigTool/ConfigUI
- In the Deployment Operations pane, click **Update** Database, **Build** and **Deploy** Application EAR Files. Click **Finish**.
- Click Next.
- Click Finish. The Config tool will execute all selected tasks.

- The Config tool has completed its tasks. It has updated the database, rebuilt and redeployed the ear files, and started the Maximo application server. Log in to Maximo and check System Information.

## Source
- https://maximodevsupport.blogspot.com/2020/02/installing-interim-fix-in-maximo-76x.html?m=0 
