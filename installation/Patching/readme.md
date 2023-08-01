# Maximo Fix Pack Installation Tutorial (High Level)

This tutorial is intended for new Maximo learners using a Windows Server 2012 R2 64-bit system and Firefox browser. Follow the steps below to install the fix pack:

## Step 1: Prerequisites
Check your current version of Maximo Asset Management. You can install the feature pack if one of the following versions is installed:
- 7.6.0.0
- ...
- 7.6.0.8

## Step 2: Before You Begin
### Task 1: Clear Cache
Clear the WebSphere Application Server cache. 
This is needed if you've made customizations or changes that require you to rebuild the EAR file. 
You can clear the cache by:
- navigating to the WebSphere Application Server's temporary directory (typically `WAS_HOME/temp` or `WAS_HOME/profiles/profile_name/temp`), and
- deleting all the files and folders.

### Task 2: Confirm File Integrity
Confirm that the **fixpack.zip** compressed file was not corrupted during the download using an MD5 checksum utility.

### Task 3: Understand Customization Limitations
Please note that any customizations made to commonenv.bat are lost when this feature pack is applied.

## Step 3: Preparation
### Task 1: Check for Pending Changes
- Ensure that no database configuration changes are pending.
- You can do this by checking the Database Configuration application in Maximo and ensuring there are no rows with a status of **Pending**.

### Task 2: Shut Down Applications
Shut down all Maximo Asset Management applications.
You can do this by stopping the application server (for example, WebSphere Application Server) that hosts Maximo.

### Task 3: Back Up Database
Back up the database and save it to a secure location.

### Task 4: Copy Maximo Directory
Copy the entire Maximo Asset Management directory and save it to another location.

### Task 5: Administrator Login
Log in as an administrator. This is important because if you attempt to upgrade when you are not logged in as an administrator, the installation fails.

## Step 4: Installation
### Task 1: Extract Fix Pack
- Extract the contents of the fix pack zip file to a location of your choice.

### Task 2: Open Installation Manager
- Open the IBM Installation Manager.

### Task 3: Add Repository
- Click on "File" > "Add Repository" and navigate to the location where you extracted the fix pack. Select the repository.config file and click "OK."

### Task 4: Install Fix Pack
- Back on the main screen of the Installation Manager, click on "Update."
- Follow the prompts to install the fix pack.

## Step 5: After Installation
### Task 1: Clear Browser Cache
- Open Firefox and press `Ctrl + Shift + Delete` to open the "Clear Recent History" window.
- In the "Time range to clear" dropdown, select "Everything."
- Make sure "Cache" is checked and then click on "Clear Now."
- Repeat these steps on every computer that uses the product.

## Step 6: Database Update
### Task 1: Stop Application Server
- Manually stop the Maximo application server.

### Task 2: Update Database
- Run the database update script that comes with the fix pack. This can be done through the Maximo Admin Mode Utilities (Admin Mode > Update Database).

## Step 7: Post-Installation
### Task 1: Start Application Server
- Start the Maximo application server.

### Task 2: Verify Fix Pack Installation
- Log in to Maximo and verify that the fix pack version is reflected in the System Information screen (System Configuration > Platform Configuration > System Properties > System Information).

### Task 3: Check System Functionality
- Check that everything is working correctly.
