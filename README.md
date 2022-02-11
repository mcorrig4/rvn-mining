# rvn-mining
_________________________

This is using [Raven Miner pool](https://www.ravenminer.com/doc/howto)

## Steps (NVIDIA GPU):
1. Install GPU driver [here](https://developer.nvidia.com/cuda-downloads)
2. Install t-rex miner [here](https://github.com/trexminer/T-Rex/releases)
    1. chrome might block this download. I used curl to download through command prompt
    2. Open start menu. Search CMD and open command prompt. Enter the command:
      ```
      curl https://github.com/trexminer/T-Rex/releases/download/0.25.2/t-rex-0.25.2-win.zip -o .\trex.zip
      ```
3. Extract zip into a folder of known location. Mine is: `X:\win10\rvn\trex`
4. Create a `.bat` file using a text editor that can launch the miner
```bat
:loop
[FULL PATH]\t-rex.exe -a kawpow -o stratum+tcp://stratum.ravenminer.com:3838 -u [RVN Wallet]
goto loop
```

Mine batch script is:
```bat
:loop
X:\win10\rvn\trex\t-rex.exe -a kawpow -o stratum+tcp://stratum.ravenminer.com:3838 -u RUWXXXXRvTDDkrURPUmH9UnLFwPCXXXXXX
goto loop
```
*Note: I used Trust Wallet as my RVN wallet*
5. Save the `mine-rvn.bat` file on your desktop. Double click to start mining.
6. Once the miner is running you can check the web GUI to monitor progress. The GUI is accessible:
[http://127.0.0.1:4067/](http://127.0.0.1:4067/)
7. You can also monitor your pool progress by replacing your wallet address here:
[https://www.ravenminer.com/wallet/RUWXXXXRvTDDkrURPUmH9UnLFwPCXXXXXX/]9https://www.ravenminer.com/wallet/RUWXXXXRvTDDkrURPUmH9UnLFwPCXXXXXX/)

## Scheduling
Optionally, use Windows task scheduler to automatically run. (I'm running only at night)
1. Create a task
![image](https://user-images.githubusercontent.com/1342367/153629469-2ee56eda-6b6e-4561-9f85-1eb8046223a0.png)
2. Setup up for Windows 10
![image](https://user-images.githubusercontent.com/1342367/153630536-7bbfa2e6-c35d-4488-8cce-44eaf741b546.png)
3. Create a schedule to run every night at 11:30pm
![image](https://user-images.githubusercontent.com/1342367/153630807-29889a2c-2785-47d7-af83-a6c5ffb5d50e.png)
4. Make task run batch script to start the miner
![image](https://user-images.githubusercontent.com/1342367/153631186-8053f245-589d-41f4-9afe-b050caeb4472.png)
5. Have the task kill the process after 8 hours
![image](https://user-images.githubusercontent.com/1342367/153631426-aff256a7-6dc1-47a4-a131-b1a4e95eb45b.png)
6. Test running the task
![image](https://user-images.githubusercontent.com/1342367/153631698-186d9ed1-28eb-419d-ab47-fc9cf3f69a3e.png)
7. Then test making sure the task can be killed. Make sure the command window that opened automaticall closes.
![image](https://user-images.githubusercontent.com/1342367/153631803-3991596a-9024-412f-a10c-a21ab47b2d7d.png)
8. PROFIT $$$
