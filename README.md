
## Get-DellSpeculationControlBIOSVersion

This commandlet will allow you to check if a Dell computer has a BIOS that is protected for the side-channel CPU vulnerabilities [Meltdown & Sprectre](https://meltdownattack.com/).
To check a Dell machine runing windows run the following ***powershell*** command.

    (new-object Net.WebClient).DownloadString('http://bit.ly/2mBg24K') | iex

    Get-DellSpeculationControlBIOSVersion
This will check the current machines status against the [official Dell list of hardware](http://www.dell.com/support/article/us/en/04/sln308587/microprocessor-side-channel-vulnerabilities-cve-2017-5715-cve-2017-5753-cve-2017-5754-impact-on-dell-products).

![enter image description here](https://i.imgur.com/w7ra55o.png)

If you would like to look up a list of models you can do that as well. The commandlet will also accept a list of models from the pipeline as well.

Examples

    Get-DellSpeculationControlBIOSVersion -Model "Latitude E6520"
    Get-DellSpeculationControlBIOSVersion -Model "Latitude E5570"
    Get-DellSpeculationControlBIOSVersion -Model "XPS 15 9550"
    $Models = "Precision Tower 3420", "OptiPlex 3010"
    $Models | Get-DellSpeculationControlBIOSVersion 

![enter image description here](https://i.imgur.com/w88dRyF.png)

To query a Windows machine for all speculation control settings run the [Speculation Control script](https://www.powershellgallery.com/packages/SpeculationControl).
