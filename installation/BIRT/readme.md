# BIRT Configuration Tutorial

This tutorial will guide you through the process of configuring BIRT (Business Intelligence and Reporting Tools) on a Windows Server 2012 system. We'll be using various software tools like Java Runtime Environment (JRE), Eclipse, and Oracle's JDBC driver, and we'll be setting up BIRT to work with Maximo Asset Management.

## Prerequisites

- Windows Server 2012
- Installed WinRAR for extracting files
- Installed Notepad++ for editing files
- Access to the files `jre-7-windows-x64.exe`, `eclipse-reporting-kepler-SR1-win32-x86_64.zip`, and `oraclethin.jar`

PS: If required, download jdk-7u80-windows-x64.exe from https://www.oracle.com/pk/java/technologies/javase/javase7-archive-downloads.html

## Step-by-Step Guide

### Step 1: Install JRE

Install `jre-7-windows-x64.exe` into the directory `C:\java\jre7`.

### Step 2: Extract Eclipse

Use WinRAR to extract `eclipse-reporting-kepler-SR1-win32-x86_64.zip` into the directory `C:\birt_431`.

### Step 3: Copy the Classes Folder

Copy the `classes` folder from `C:\IBM\SMP\maximo\reports\birt\scriptlibrary\classes` to `C:\birt_431\eclipse\plugins\org.eclipse.birt.report.viewer_4.3.1.v201309171028\birt\WEB-INF\`.

### Step 4: Copy the JDBC Driver

Copy `oraclethin.jar` from `C:\IBM\SMP\maximo\applications\maximo\lib\` to `C:\birt_431\eclipse\plugins\org.eclipse.birt.report.viewer_4.3.1.v201309171028\birt\WEB-INF\lib\`.

### Step 5: Extract JDBC Driver Contents

Use WinRAR to extract the contents of `oraclethin.jar` from the above directory to `C:\birt_431\eclipse\plugins\org.eclipse.birt.report.viewer_4.3.1.v201309171028\birt\WEB-INF\classes`.

### Step 6: Copy the BIRT Engine Jar File

Copy `org.eclipse.birt.report.engine_4.3.1.v201309161141.jar` from `C:\IBM\SMP\maximo\applications\maximo\maximouiweb\webmodule\WEB-INF\birt\platform\plugins\` to `C:\birt_431\eclipse\plugins\`.

### Step 7: Update mxreportdatasources.properties File

Update the `mxreportdatasources.properties` file located at `C:\birt_431\eclipse\plugins\org.eclipse.birt.report.viewer_4.3.1.v201309171028\birt\WEB-INF\classes\` with the following properties:

```properties
maximoDataSource.url=jdbc:oracle:thin:@//Vmax76.ots.com:1521/MAXDB
maximoDataSource.driver=oracle.jdbc.OracleDriver
maximoDataSource.username=maximo
maximoDataSource.password=xyz
maximoDataSource.schemaowner=maximo
```

### Step 8: Configure Eclipse Shortcut

Create a shortcut for Eclipse with the following path:
```
C:\birt_431\eclipse\eclipse.exe -vm "C:\java\jre7\bin\javaw.exe" -vmargs -Xmx512m
```

### Step 9: Set Resource Paths

In Eclipse, navigate to Report Design and select Resources, then set the following paths:

- Library Resources Path: `C:\IBM\SMP\maximo\reports\birt\libraries`
- Templates Path: `C:\IBM\SMP\maximo\reports\birt\templates/`

### Step 10: Create a New Project

In Eclipse, click `File > New > Project`. Under `Business Intelligence and Reporting Tools`, select `Report Project`, click `Next`, and select the directory `C:\IBM\SMP\maximo\reports\birt\reports`.

### Step 11: Update eclipse.ini File

Open `C:\birt_431\eclipse\eclipse.ini` in Notepad++ and append the following lines:

```ini
-Dorg.eclipse.swt.browser.DefaultType=ie,mozilla
-Dorg.eclipse.swt.browser.IEVersion=7000
```
### Step 12: Restart the System
Finally, restart your system for the changes to take effect.

Congratulations, you have successfully configured BIRT on your Windows Server 2012 system!

