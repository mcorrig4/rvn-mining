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
6. Optional, use Windows task scheduler to automatically run.
