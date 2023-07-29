
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

