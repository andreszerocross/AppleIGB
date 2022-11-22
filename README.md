# AppleIGB

## ⚠ This fork is deprecated

### There is by [far better](https://github.com/mbarbierato/IntelMausi) effort by @mbarbierato (check branches there and correspondent links in discussions) to patch well-formed and stable IntelMausi codebase to support the whole I211 family (including X570 and TRX40). Discussions and issues will be closed soon. 🎉

#### Kind thanks and kudos for testing, contribution and dedication to following people 🤗 (ASC order):
- [Allubz](https://github.com/Allubz)
- [aospiridonov](https://github.com/aospiridonov) 
- [Cryptiiiic](https://github.com/Cryptiiiic)
- [Dawn13](https://github.com/Dawn13)
- [emaa10](https://github.com/emaa10)
- [emanuelbalea](https://github.com/emanuelbalea)
- [gabevf](https://github.com/gabevf)
- [gentcys](https://github.com/gentcys)
- [henkiewie](https://github.com/henkiewie)
- [jjlorenzo](https://github.com/jjlorenzo)
- [jobheger](https://github.com/jobheger)
- [Leborgne23](https://github.com/Leborgne23) 
- [llyonard](https://github.com/llyonard)
- [Lorys89](https://github.com/Lorys89)
- [marsqing](https://github.com/marsqing)
- [mbarbierato](https://github.com/mbarbierato)
- [meteoro](https://github.com/meteoro)
- [n374](https://github.com/n374)
- [Natedude](https://github.com/Natedude)
- [nolevuhao](https://github.com/nolevuhao)
- [NyaomiDEV](https://github.com/NyaomiDEV) 
- [residentcode](https://github.com/residentcode)
- [SapixIV](https://github.com/SapixIV)
- [seven-of-eleven](https://github.com/seven-of-eleven)
- [sharklatan](https://github.com/sharklatan)
- [smartass08](https://github.com/smartass08)
- [the3venthoriz0n](https://github.com/the3venthoriz0n)
- [thedxrklord](https://github.com/thedxrklord) 
- [yhl452493373](https://github.com/yhl452493373)

<br />

#### Intel onboard LAN driver for macOS. Courtesy of [hnak](https://www.insanelymac.com/forum/profile/228503-hnak/?wr=eyJhcHAiOiJmb3J1bXMiLCJtb2R1bGUiOiJmb3J1bXMtY29tbWVudCIsImlkXzEiOjI3MzA3MywiaWRfMiI6MTc3NTc1Mn0=), refer to the [original post](https://www.insanelymac.com/forum/topic/273073-appleigbkext/) for more details.
<br />

  - Updated to [Intel's IGB source 5.11.4](https://www.intel.com/content/www/us/en/download/14098/intel-network-adapter-driver-for-82575-6-82580-i350-and-i210-211-based-gigabit-network-connections-for-linux.html) (initial update to [5.7.2](https://www.intel.com/content/www/us/en/download/14098/13663/intel-network-adapter-driver-for-82575-6-82580-i350-and-i210-211-based-gigabit-network-connections-for-linux.html) by [Shanee](https://github.com/Shaneee))
 - Adopting/merging IntelMausi link management and code structure approach (for potential further merge)
 - Explicitly stalling packets when transmit queue is busy (as in IntelMausi)
  - Added options to (un)select EEE mode (there are notes that disabling it could fix spontaneous link problems)
 - Ensured software interrupt register in watchdog for rx ring cleaned

<hr />

## Supported Devices

 - 82575
 - 82576
 - 82580
 - dh89xxcc
 - i210/i211
 - i350
 - i354

Updated version only tested on AMD versions of Intel I211-AT so far. 

Feel free to post issues (ensure you provide additional device info and whether [SmallTree](https://github.com/khronokernel/SmallTree-I211-AT-patch) is fully working on 11.x)

## Known Current Issues

 - Although it's fully stable in my setup (i211 @ B450) and some [others](https://github.com/donatengit/AppleIGB/discussions/6), specifically B470, X299, Z390, Z270, WS C246 - there are multiple reports for instability and connection drops on X570, TRX40 motherboards. So for those having these MB I'd recommended to stay on SmallTree and corresponding MacOS versions 11.x or attach USB Ethernet until there is someone could help with a deep diagnosis of the problem.
 - This driver doesn't use MSI-X interrupts
