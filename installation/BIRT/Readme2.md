# BIRT Configuration Tutorial (Quick Version)

This tutorial will guide you through the process of configuring BIRT on Windows Server 2012. We will use tools like WinRar and Notepad++ for various steps in the process.PrerequisitesMake sure WinRar and Notepad++ are installed on your machine.Make sure you have access to the directories and files mentioned in the steps below.Steps

PS: If required, download jdk-7u80-windows-x64.exe from https://www.oracle.com/pk/java/technologies/javase/javase7-archive-downloads.html


Install JRE: Download and install ```jre-7-windows-x64.exe``` into ```C:\java\jre7```

Extract Eclipse: Extract ```eclipse-reporting-kepler-SR1-win32-x86_64``` into ```C:\birt_431\eclipse```

Copy the classes folder:cmd
```cmd
copy /Y "C:\IBM\SMP\maximo\reports\birt\scriptlibrary\classes" "C:\birt_431\eclipse\plugins\org.eclipse.birt.report.viewer_4.3.1.v201309171028\birt\WEB-INF\"
```

Copy the Oracle Thin driver:cmd
```cmd
copy /Y "C:\IBM\SMP\maximo\applications\maximo\lib\oraclethin.jar" "C:\birt_431\eclipse\plugins\org.eclipse.birt.report.viewer_4.3.1.v201309171028\birt\WEB-INF\lib\"
```

Extract the driver JAR file contents into the classes folder:

Please note that the ```tar``` command does not work on Windows. You can use WinRAR or 7-Zip to extract the ```.jar``` file. Right click on the ```oraclethin.jar``` file and select 'Extract files...'. Choose the target directory as ```C:\birt_431\eclipse\plugins\org.eclipse.birt.report.viewer_4.3.1.v201309171028\birt\WEB-INF\classes```.

Copy the BIRT report engine:cmd
```cmd
copy /Y "C:\IBM\SMP\maximo\applications\maximo\maximouiweb\webmodule\WEB-INF\birt\platform\plugins\org.eclipse.birt.report.engine_4.3.1.v201309161141.jar" "C:\birt_431\eclipse\plugins\"
```

Update mxreportdatasources.properties file:

Open the ```mxreportdatasources.properties``` file in Notepad++ located at ```C:\birt_431\eclipse\plugins\org.eclipse.birt.report.viewer_4.3.1.v201309171028\birt\WEB-INF\classes\```.

Set the following values in the properties file:properties
```properties
maximoDataSource.url=jdbc:oracle:thin:@//Vmax76.ots.com:1521/MAXDB
maximoDataSource.driver=oracle.jdbc.OracleDriver
maximoDataSource.username=maximo
maximoDataSource.password=xyz
maximoDataSource.schemaowner=maximo
```

Create a shortcut for BIRT settings: Create a shortcut with the following path:mathematica
```mathematica
C:\birt_431\eclipse\eclipse.exe -vm "C:\java\jre7\bin\javaw.exe" -vmargs -Xmx512m
```

Set the library resources path: Navigate to 'Report Design' and select 'Resources'. Set the path as follows:makefile
```makefile
C:\IBM\SMP\maximo\reports\birt\libraries
```

Set the templates path: Navigate to 'Report Design' and select 'Templates'. Set the path as follows:makefile
```makefile
C:\IBM\SMP\maximo\reports\birt\templates/
```

Create a new project: Click 'File' &gt; 'New' &gt; 'Project'. Under 'Business Intelligence and Reporting Tools', select 'Report Project'. Click 'Next'. Set the path as follows:makefile
```makefile
C:\IBM\SMP\maximo\reports\birt\reports 
```

Update the eclipse.ini file: Open the ```eclipse.ini``` file located at ```C:\birt_431\eclipse\``` in Notepad++ and append the following lines:ini
```ini
-Dorg.eclipse.swt.browser.DefaultType=ie,mozilla 
-Dorg.eclipse.swt.browser.IEVersion=7000 
```

Restart: Restart your system to complete the BIRT configuration.

Congratulations! You have now successfully configured BIRT on your Windows Server 2012. If you encounter any issues, please refer back to the corresponding step in this tutorial.

