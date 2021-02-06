# Table of contents
  - [Importance of low input lag](#importance-of-low-input-lag)
  - [Disclaimer](#disclaimer)
  - [Physical setup](#physical-setup)
  - [Peripherals](#peripherals)
    - [Mouse](#mouse)
    - [Monitor](#monitor)
  - [BIOS](#bios)
  - [Hardware clocking](#hardware-clocking)
    - [Temperature](#temperature)
    - [Intel Lake platform (6000-10000 series)](#intel-lake-platform-6000-10000-series)
    - [RAM (Intel & AMD)](#ram-intel--amd)
    - [CPU (Intel)](#cpu-intel)
    - [GPU (NVIDIA)](#gpu-nvidia)
  - [Windows](#windows)
  - [Tools & resources](#tools--resources)
    - [Mouse](#mouse-1)
    - [Mousepad](#mousepad)
    - [Keyboard](#keyboard)
    - [Monitor](#monitor-1)
    - [PSU](#psu)
    - [CPU](#cpu)
    - [RAM](#ram)
    - [GPU](#gpu)
    - [Motherboard](#motherboard)
    - [Storage](#storage)
    - [BIOS](#bios-1)
    - [Windows](#windows-1)
    - [Alternatives to bloated programs](#alternatives-to-bloated-programs)
    - [Miscellaneous](#miscellaneous)
# Importance of low input lag
  - ["While participants performed dragging and scribbling tasks, very low levels of latency could be discriminated, i.e., ~1 versus 2 milliseconds while dragging"](https://doi.org/10.1145/2556288.2557037).
  - [Visual demonstration of 1 vs 10 milliseconds](https://youtu.be/vOvQCPLkPt4?t=80)
  - ["The average difference in aiming task completion (the time it takes to acquire and shoot a target) between a 12ms and 20ms PCs was measured to be 182ms - that is about 22 times the system latency difference."](https://www.nvidia.com/en-us/geforce/news/reflex-low-latency-platform/#why-does-system-latency-matter)
  - ["In all studies, the trend shows continued improvements all the way toward zero latency."](https://developer.nvidia.com/blog/aiming-faster-in-games-with-low-computer-system-latency/)
  - [Summary in form of an infographic](https://raw.githubusercontent.com/BoringBoredom/PC-Optimization-Hub/main/content/importance%20of%20low%20input%20lag/latency.png)
# Disclaimer
  - Due to the sheer complexity of hardware and software and differences between various architectures, your mileage may vary. However, it is useful to be aware of things that can impact user experience and adjust them according to your needs.
  - Create a personal document and keep track of everything you do. Adopt a systematic approach with proper testing methodologies instead of just blindly changing many settings at once. Some settings are trade-offs between latency and consistency / graphics quality. Some settings may not show a visible impact at first due to other bottlenecks.
# Physical setup
  - [Electromagnetic interference](https://en.wikipedia.org/wiki/Electromagnetic_interference) and issues with electricity (e.g. [ground loops](https://en.wikipedia.org/wiki/Ground_loop_(electricity))) can cause unintended behavior of electronic components, potentially [increasing input lag](content/physical%20setup/emc%20problem%20list.md#list-of-forum-threads-from-users-reporting-increased-input-lag-due-to-lack-of-electromagnetic-compatibility-or-issues-with-electricity). Here are [some resources](https://github.com/djdallmann/GamingPCSetup/blob/master/CONTENT/TECHNICAL%20REFERENCES/README.md#electrical) and a [short summary](https://forums.blurbusters.com/viewtopic.php?f=10&t=7168&start=30#p62185).
  - ["EMC tests were developed to make them easier to perform, provide better repeatability from one lab to another, and reduce testing costs. But even though the EUT may pass its EMC tests, it still may fail when it's put into service. Laboratory tests performed in accordance with the standards are not adequate to guarantee that an EMC failure will not occur during actual operation because the tests do not represent the operational EME."](https://www.evaluationengineering.com/home/article/13003718/emc-failures-happen)  
Here are some examples: [1](https://bit-tech.net/news/tech/motherboards_not_passing_emi_tests/1/) [2](https://www.theverge.com/circuitbreaker/2017/2/3/14496044/lg-ultrafine-5k-display-router-fix-redesign) [3](https://edition.cnn.com/2021/01/25/tech/iphone-12-medical-device-interference/index.html) [4](https://www.techpowerup.com/review/corsair-ax1600i/11.html#:~:text=The%20Corsair%20AX1600i%20failed%20here.%20We%20noticed%20increased%20EMI%20emissions%20with%20lower%20frequencies.) [5](https://www.techpowerup.com/review/evga-supernova-t2-1600/10.html#:~:text=As%20you%20can%20easily%20figure%20by%20looking%20at%20the%20graph%20above,%20EVGA's%20PSU%20failed%20to%20pass%20our%20EMC%20tests.) [6](https://www.techpowerup.com/review/be-quiet-dark-power-pro-1500-w/10.html#:~:text=There%20are%20some%20high%20EMI%20spikes,%20with%20the%20more%20severe%20one%20close%20to%201%20MHz.) [7](https://www.techpowerup.com/review/seasonic-connect-750w/11.html#:~:text=EMI%20noise%20is%20increased%20at%20frequencies%20below%201%20MHz.) [8](https://www.techpowerup.com/review/corsair-ax1000/5.html#:~:text=There%20are%20two%20high%20spurs%20that%20go%20over%20the%20limits.) [9](https://www.techpowerup.com/review/be-quiet-dark-power-pro-11-1000w/10.html#:~:text=EMI%20noise%20was%20higher%20than%20it%20should%20be%20at%20low%20frequencies,%20so%20this%20PSU%20didn't%20do%20too%20well%20in%20this%20test.) [10](https://www.techpowerup.com/review/chieftronic-powerplay-750-w/10.html#:~:text=Three%20spurs%20go%20over%20the%20limit%20with%20the%20QP%20detector.) [11](https://www.techpowerup.com/review/corsair-ax1000/5.html#:~:text=There%20are%20two%20high%20spurs%20that%20go%20over%20the%20limits.) [12](https://www.techpowerup.com/review/corsair-rm650i/11.html#:~:text=While%20performance%20at%20low%20frequencies%20could%20be%20better,%20EMI%20is%20kept%20at%20very%20low%20levels%20above%201%20MHz.)
  - Make sure your outlets are properly grounded.
  - If you don't have enough outlets, buy a proper power strip ( < power conditioner < voltage regulator) and connect all devices directly to it. Only connect your hardware (no phone chargers etc.).
  - Disconnect all things you don't use from your motherboard to minimize risk of [coupling](https://youtu.be/950XhSPanlA). E.g. front USB, front audio, (RGB) LEDs, hard drive activity LED, system power LED, reset button etc.
  - Move all devices that have electric or electromagnetic fields away from your PC and peripherals. E.g. [router](https://raw.githubusercontent.com/BoringBoredom/PC-Optimization-Hub/main/content/physical%20setup/router.jpg), power strip/[conditioner](https://raw.githubusercontent.com/BoringBoredom/PC-Optimization-Hub/main/content/physical%20setup/conditioner.jpg), voltage regulator etc.
  - Make sure there is enough space between your [cables](https://www.phidgets.com/docs/Improving_Phidgets_Hardware_Reliability#Device_Resets_.28Due_to_Cable_to_Cable_Interference.29) and untangle them. This applies to everything, including power and [peripheral](https://raw.githubusercontent.com/BoringBoredom/PC-Optimization-Hub/main/content/physical%20setup/mouse%20cable.png) cables.
  - Check the USB layout of your system with [USB Device Tree Viewer](https://www.uwe-sieber.de/usbtreeview_e.html). Connect your mouse (or primary input device) to the first port of the first controller (usually [this port](https://i.imgur.com/QGKAVoA.png)).
  - If your motherboard has multiple USB controllers, [offload](https://forums.blurbusters.com/viewtopic.php?f=10&t=7618) your other devices to them. Lower their polling rate to an acceptable level. E.g. your microphone doesn't need 1000 Hz
  - Test both HDMI and DP on each GPU port (don't Plug & Play these).
  - Keep your PC clean. Clogged heatsinks and dust filters will reduce airflow and consequently heat dissipation. Furthermore, ["dust may cause
electrical leakage, shorting and opening of PCBs under different conditions"](https://www.circuitinsight.com/pdf/impact_of_dust_ipc.pdf).
# Peripherals
  - Turn off (RGB) LEDs since USB current output is very limited ([USB 2: 0.5 A, USB 3: 0.9 A](https://en.wikipedia.org/wiki/USB)). Moreover, ["running an RGB effect/animation can take a great toll on the MCU. It requires a lot of processing power and will delay other processes."](https://blog.wooting.nl/what-influences-keyboard-speed/)
  - ## Mouse
    - ### Wired vs. Wireless
      - The convenience of cordless mice is very appealing. However, there are significant drawbacks. Nowadays, [2.4 GHz](https://en.wikipedia.org/wiki/2.4_GHz_radio_use) is everywhere, causing a lot of interference. Additionally, aggressive power saving mechanisms are implemented to increase battery life, affecting both [sensor](https://raw.githubusercontent.com/BoringBoredom/PC-Optimization-Hub/main/content/peripherals/hero%20power%20saving.PNG) and [click](https://twitter.com/CaIypto/status/1354186350665363457/photo/1) latency.
    - ### DPI
      - Depending on your preferred cm/360°, [mousepad](https://raw.githubusercontent.com/BoringBoredom/PC-Optimization-Hub/main/content/peripherals/mousepad.png) and FOV in games, you may want to experiment with different DPI. Higher DPI [reduces latency](https://raw.githubusercontent.com/BoringBoredom/PC-Optimization-Hub/main/content/peripherals/dpi.PNG) and [improves motion clarity](https://youtu.be/QrF_e5vKqPk). Most modern sensors are able to handle around 1600 DPI without sensor smoothing. To counteract the increased sensitivity on the Desktop and in game menus you can adjust the [Windows sensitivity](https://liquipedia.net/counterstrike/Mouse_Settings#Windows_Sensitivity).
    - ### Polling rate
      - Higher polling rate reduces latency and [improves motion clarity](https://youtu.be/gOQNRvJbpmk?t=540) ([another example](https://forums.blurbusters.com/viewtopic.php?f=10&t=7569)).
  - ## Monitor
    - ### Capping FPS
      - [Input lag increases as GPU utilization increases](https://youtu.be/8ZRuFaFZh5M?t=817).
      - [Frame mistiming](https://youtu.be/_73gFgNrYVQ) causes severe stutters. To prevent this phenomenon you can cap your FPS at various values depending on your monitor's refresh rate. Consider your [1% and 0.1% Lows](https://youtu.be/uXepIWi4SgM) when choosing a value. There are two formulae (X = monitor's refresh rate, Y = any integer):
        - X * Y
        - X / Y if X %Y = 0
      - These are some of the FPS cap values that will prevent mistiming:
        - 360 Hz: ... , 45, 60, 72, 90, 120, 180, 360, 720, 1080, ...
        - 280 Hz: ... , 40, 56, 70, 140, 280, 560, 840, 1120, ...
        - 240 Hz: ... , 48, 60, 80, 120, 240, 480, 720, 960, ...
        - 144 Hz: ... , 48, 72, 144, 288, 432, 576, 720, 864, 1008, ...
        - 120 Hz: ... , 40, 60, 120, 240, 360, 480, 600, 720, 840, 960, 1080, ...
# BIOS
  - Generally, follow the principle of "Don't use it? Disable it." E.g. disable all power saving features, unused network/audio/SATA controllers, unused USB/PCI/DIMM/SATA ports, (RGB) LEDs that can't physically be disconnected etc.
  - [How to change hidden settings without flashing a modded BIOS](https://github.com/BoringBoredom/IFR-Formatter)
  - ## Optimization guides
    - [Fujitsu guide](https://sp.ts.fujitsu.com/dmsp/Publications/public/wp-bios-settings-primergy-ww-en.pdf)
    - [r0ach's guide](https://www.overclock.net/threads/gaming-and-mouse-response-bios-optimization-guide-for-modern-pc-hardware.1433882/)
# Hardware clocking
  - I called this category *clocking* rather than *overclocking* because in the end all you do is run your components at their safe capabilities (which may not always be *over*clocking due to temperature, for example).
  - A stable system should be able to run anything indefinitely. A single error is one too many.
  - ## Temperature
    - ["Charge leakage rate of DRAM cells approximately doubles for every 10°C increase in the temperature"](https://www.pdl.cmu.edu/PDL-FTP/NVM/chargecache_low-latency-dram_hpca16.pdf).
    - ["The load has increased the main board temperature by 5 deg. (centigrade scale) only, but the influence to the measured performance counter frequency is quite considerable."](http://www.windowstimestamp.com/description)
    - ["According to a report on reliability prediction of electronic equipment prepared by the U.S. Department of Defense, the failure factor, which is relative failure rate at any temperature over failure rate at 75 °C, increases exponentially with increasing the device temperature as demonstrated in Fig. 3. Pedram and Nazarian also reported that more than 50% of all integrated circuit (IC) failures are related to thermal issues. Thus a rule of thumb is that the failure rate of electronic components can be halved for each 10 °C reduction in their junction temperature and the cooler the devices operate, the more reliable they are."](https://doi.org/10.1016/j.rser.2017.04.112)
    - ["The operating leakage current of an aluminium electrolytic capacitor with non-solid electrolyte is extremely dependent on the temperature and voltage."](https://tadiranbatteries.de/pdf/applications/leakage-current-properties-of-modern-electrolytic-capacitors.pdf)
    - Conclusion: Maintaining near ambient temperature of components is desirable.
    - ### Controlling temperature
      - Manually set voltages and clocks of all components.
      - Use zip-ties to extend fans over VRMs, RAM and PCH. Avoid CPU air coolers due to incompatibility with dedicated VRM and RAM cooling.
      - Liquid cool all components (expensive).
  - ## Intel Lake platform (6000-10000 series)
    - [Voltages](https://youtu.be/WK5Md-90XHQ?t=203)
    - Beware of degradation by high voltage, temperature and current. Personally, I think the voltages and temperature mentioned in the previous video are too high.
    - [Core](https://youtu.be/WK5Md-90XHQ?t=851), [Uncore and RAM](https://youtu.be/WK5Md-90XHQ?t=1116) affect each other's stability. Since the effectiveness of CPU stress testing is much lower with stock RAM, I suggest adjusting RAM first and eventually revisiting it to verify it didn't destabilize.
  - ## RAM (Intel & AMD)
    - [Importance of memory clocking](https://kingfaris.co.uk/ram)
    - Stress test overnight to maximize long-term stability. Retest with a [variety of programs](#stress-testing-programs-1) since ["data pattern dependence exists. Coverage varies significantly between data patterns in each of the device families shown, indicating that the retention time of many DRAM cells depends on the data stored in other cells."](https://www.pdl.cmu.edu/PDL-FTP/NVM/dram-retention_isca13.pdf)
    - [Integralfx's DDR4 guide](https://github.com/integralfx/MemTestHelper/blob/master/DDR4%20OC%20Guide.md)
  - ## CPU (Intel)
    - Adjust VCORE, [LLC and VRM switching frequency](https://elmorlabs.com/index.php/2019-09-05/vrm-load-line-visualized/).
    - Stress test with [Linpack Xtreme](https://www.ngohq.com/linpack-xtreme.html) for a few minutes.
    - Monitor the temperature and make sure you are below your threshold. Personally, I would aim for <60°C.
    - Continue raising both All Core and Uncore by 100 MHz and do quick stress tests. Eventually, you will encounter either instability or temperature above your threshold.
    - If the temperature is too high, you can try lowering VCORE (P = I * V).
    - If you encounter instability, lower All Core and Uncore by 100 MHz and continue raising All Core from now on.
    - Ultimately, stress test overnight to maximize long-term stability.
  - ## GPU (NVIDIA)
    - [Cancerogeno's guide](https://docs.google.com/document/d/14ma-_Os3rNzio85yBemD-YSpF_1z75mZJz1UdzmW8GE/edit)
# Windows
  - I highly recommend setting up a multi-boot environment to separate the gaming and the "can-be-bloated" operating system. Keeping your programs and files on a different partition (separate from operating system partitions) is also convenient due to all operating systems having shared access to everything and the ease of reinstalling either of them without having to back up your data.
  - As usual, disable everything you don't explicitely need.
  - The Task Manager is a very inaccurate representation of system load since it only displays Core usage on a very superficial level. It doesn't account for things like [context switching](https://en.wikipedia.org/wiki/Context_switch) which can be very expensive. I recommend using [Process Explorer](https://docs.microsoft.com/en-us/sysinternals/downloads/process-explorer) with [modified settings](https://raw.githubusercontent.com/BoringBoredom/PC-Optimization-Hub/main/content/windows/process%20explorer%20settings.reg) instead.
  - [NVIDIA Profile Inspector](https://github.com/Orbmu2k/nvidiaProfileInspector) exposes a lot of settings that are hidden from the control panel.
  - Whenever possible, use portable versions of programs. Sometimes installers come with background services/drivers which may run even if the program is not running.
  - ## Optimization guides
    - [Calypto's guide](https://docs.google.com/document/d/1c2-lUJq74wuYK1WrA_bIvgb89dUN0sj8-hO3vqmrau4/edit)
    - [Timecard's guide](https://github.com/djdallmann/GamingPCSetup)
  - ## ISO creation
    - [USB and storage drivers](https://www.win-raid.com/f25-General-Storage-Drivers-AHCI-RAID-NVMe-and-USB.html) (mostly relevant for W7) & [driver integration guide](https://www.win-raid.com/t750f25-Guide-Integration-of-drivers-into-a-Win-image.html)
    - [Rufus](https://github.com/pbatard/rufus)
    - ### ISO sources
      - Always check legitimacy of ISO by comparing [hashes](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/get-filehash?view=powershell-7.1) -> [Heidoc's hash archive](https://www.heidoc.net/php/myvsdump_directory.php?letter=W)
      - [Heidoc](https://www.heidoc.net/joomla/technology-science/microsoft/67-microsoft-windows-iso-download-tool)
      - [Techbench](https://tb.rg-adguard.net/public.php)
      - [The Eye](https://the-eye.eu/public/MSDN/)
      - [DigitalRiver](https://digitalrivermirror.com/) (W7 only)
      - [KichHoatBanQuyen's list](https://docs.google.com/spreadsheets/d/14-D4tIlFp9APP0OOvQBRXvfLOYC447UygywenX5LXfo/edit)
      - [Unknown list](https://docs.google.com/spreadsheets/d/1zTF5uRJKfZ3ziLxAZHh47kF85ja34_OFB5C5bVSPumk/edit)
# Tools & resources
  - ## Mouse
    - ### Information
      - [Newbrict's page](https://sensor.fyi/info/)
      - [Click latency database](https://github.com/NVIDIA/Reflex-Latency-Analyzer-Mouse-Database/blob/main/NVIDIA%20RLA%20Mice%20Database%20-%20Github.csv)
    - ### Tools
      - [Gearsearch shape comparison](https://gearsearch.gg/shape.html)
      - [RTINGS shape comparison](https://www.rtings.com/mouse/tools/3d-model-shape-compare/?orientation=3D)
      - [Mouse Sensitivity Calculator](https://www.mouse-sensitivity.com/)
      - [Aiming.Pro Sensitivity Calculator](https://aiming.pro/mouse-sensitivity-calculator)
  - ## Mousepad
    - [Hoya's sheet](https://docs.google.com/spreadsheets/d/1RAnmZxDNduaGV8kB-GCvZ0MO6d9-0j9jmrU2f8dp0Ww/edit)
  - ## Keyboard
    - ["What influences keyboard speed?"](https://blog.wooting.nl/what-influences-keyboard-speed/)
  - ## Monitor
    - ### Reviews
      - [RTINGS](https://www.rtings.com/monitor/tools/table)
      - [TFT Central](https://www.tftcentral.co.uk/reviews_index.htm)
    - ### Tools
      - [Blur Busters' utilities](https://www.testufo.com/)
      - [EIZO monitor test](https://www.eizo.be/monitor-test/)
      - [Custom Resolution Utility](https://www.monitortests.com/forum/Thread-Custom-Resolution-Utility-CRU)
      - [piLagTester](https://alantechreview.blogspot.com/2020/08/pilagtester-pro-order-page.html) (input lag and response time tester)
  - ## PSU
    - ### Information
      - ["Defining Power Supply Voltage Ripple & Its Real-World Impact"](https://www.gamersnexus.net/guides/2053-power-supply-voltage-ripple-and-relevance)
    - ### Reviews
      - [Cybenetics](https://www.cybenetics.com/index.php?option=power-supplies)
      - [TechPowerUp](https://www.techpowerup.com/review/?category=Power+Supplies&manufacturer=&pp=25&order=date)
      - [Tom's Hardware](https://www.tomshardware.com/topics/power-supplies/reviews)
      - [PSUGuru's sheet](https://docs.google.com/spreadsheets/d/1_GMev0EwK37J3zZL98zIqF-OSBuHlFEHmrc_SPuYsjs/edit)
  - ## CPU
    - ### Information
      - [Intel resources](https://www.intel.com/content/www/us/en/products/docs/processors/core/core-technical-resources.html)
    - ### Tools
      - [CPU-Z](https://www.cpuid.com/softwares/cpu-z.html)
    - ### Stress testing programs
      - [Linpack Xtreme](https://www.ngohq.com/linpack-xtreme.html)
      - [Prime95](https://www.mersenne.org/download/)
  - ## RAM
    - ### Information
      - [DDR4 basics](https://www.systemverilog.io/)
      - [DDR4 JEDEC paper](http://www.softnology.biz/pdf/JESD79-4B.pdf)
      - [B-Die list](https://translate.google.com/translate?sl=auto&tl=en&u=https://www.hardwareluxx.de/community/threads/die-ultimative-hardwareluxx-samsung-8gb-b-die-liste-alle-hersteller-13-12-20.1161530/)
    - ### Tools
      - [ASRock Timing Configurator 4.0.4](https://download.asrock.com/Utility/Formula/TimingConfigurator(v4.0.4).zip)
      - [ASUS MemTweakIt 2.02.48](https://cdn.discordapp.com/attachments/653171331256549386/755097007240249416/MemTweakIt_V20248.zip)
      - [Intel Memory Latency Checker](https://software.intel.com/content/www/us/en/develop/articles/intelr-memory-latency-checker.html)
      - [AIDA](https://www.aida64.com/downloads)
    - ### Stress testing programs
      - [Karhu RAM Test](https://www.karhusoftware.com/ramtest/) ([Enable *Caching* on all operating systems and change the *RNG* to *XORWOW* if testing on Windows 7](https://www.karhusoftware.com/ramtest/README.txt))
      - [TestMem5](https://testmem.tz.ru/testmem5.htm) + [anta777's config](https://bit.ly/2MUvl6n) (link taken from [anta777's profile](https://forums.overclockers.ru/memberlist.php?mode=viewprofile&u=203320))
      - [OCCT](https://www.ocbase.com/)
      - [HCI MemTest](https://hcidesign.com/memtest/)
      - [GSAT](https://github.com/stressapptest/stressapptest)
  - ## GPU
    - ### Tools
      - [Afterburner](https://www.msi.com/Landing/afterburner)
      - [NVIDIA NVFlash](https://www.techpowerup.com/download/nvidia-nvflash/)
      - [NVCleanstall](https://www.techpowerup.com/download/techpowerup-nvcleanstall/)
      - [NVSlimmer](https://forums.guru3d.com/threads/nvslimmer-nvidia-driver-slimming-utility.423072/)
      - [GPU-Z](https://www.techpowerup.com/gpuz/)
      - [NVIDIA Profile Inspector](https://github.com/Orbmu2k/nvidiaProfileInspector)
      - [NVIDIA Nsight](https://developer.nvidia.com/nsight-graphics)
      - [NVIDIA FrameView](https://www.nvidia.com/en-us/geforce/technologies/frameview/)
    - ### Stress testing programs
      - [Geeks3D's tools](https://www.geeks3d.com/dlz/#gpu_benchmarks)
      - [Unigine's tools](https://benchmark.unigine.com/)
  - ## Motherboard
    - ### Information
      - [Z590/B560 VRM list](https://docs.google.com/spreadsheets/d/1_ZGSXi1deJEXhHZNcm3bGvP-r8KkNKKPdTuBoFPctH4/edit)
      - [Z490/Z590 VRM list](https://docs.google.com/spreadsheets/d/16YJm4L1-ohpL8s-4rLDDDCBZvi97ZYwkc44s7LS5-2Q/edit)
      - [eXtensible Host Controller Interface for Universal Serial Bus (xHCI)](https://www.intel.com/content/dam/www/public/us/en/documents/technical-specifications/extensible-host-controler-interface-usb-xhci.pdf)
      - [Message Signaled Interrupts](https://www.intel.com/content/dam/www/public/us/en/documents/white-papers/msg-signaled-interrupts-paper.pdf)
  - ## Storage
    - ### Reviews
      - [TechPowerUp](https://www.techpowerup.com/review/?category=SSD&manufacturer=&pp=25&order=date)
      - [Tom's Hardware](https://www.tomshardware.com/topics/storage/reviews)
      - [AnandTech](https://www.anandtech.com/tag/ssd%2breview)
    - ### Profiling / Monitoring / Benchmarking
      - [CrystalDiskMark](https://crystalmark.info/en/)
      - [ATTO Disk Benchmark](https://www.techpowerup.com/download/atto-disk-benchmark/)
    - ### Tools
      - [WinDirStat](https://sourceforge.net/projects/windirstat/) (disk usage analyzer)
      - [Total Commander](https://www.ghisler.com/) (file manager)
      - [Ventoy](https://github.com/ventoy/Ventoy) (multi-boot USB drive)
      - [Rufus](https://github.com/pbatard/rufus) (ISO mounting)
  - ## BIOS
    - [Win-Raid modding section](https://www.win-raid.com/f16-BIOS-Modding-Guides-and-Problems.html)
    - [Cancerogeno's compendium](https://sites.google.com/view/cancerogenoslab/bios-mods-and-tools)
  - ## Windows
    - ### Information
      - [Windows Internals](https://docs.microsoft.com/en-us/sysinternals/resources/windows-internals)
    - ### Profiling / Monitoring / Benchmarking
      - [HWInfo](https://www.hwinfo.com/download/) + [LogViewer](https://www.hwinfo.com/forum/threads/logviewer-for-hwinfo-is-available.802/) (hardware analysis, monitoring and reporting)
      - [CapFrameX](https://github.com/CXWorld/CapFrameX) (frametime capture and analysis)
      - [Windows Performance Toolkit](https://docs.microsoft.com/en-us/windows-hardware/test/wpt/) ([Windows 7](https://www.microsoft.com/en-us/download/details.aspx?id=8279))
      - [Intel VTune Profiler](https://software.intel.com/content/www/us/en/develop/tools/vtune-profiler.html)
      - [Mouse Tester](https://github.com/microe1/MouseTester)
      - [Latencymon](https://www.resplendence.com/latencymon)
      - [Liblava](https://github.com/liblava/liblava-demo)
      - [PC Clock Timing](https://www.satsignal.eu/software/net.htm) (resolution of system time calls)
    - ### Tools
      - [Sysinternals](https://docs.microsoft.com/en-us/sysinternals/downloads/)  (huge compendium)
      - [Nirsoft's Tools](https://www.nirsoft.net/utils/index.html) (huge compendium)
      - [NTLite](https://www.ntlite.com/) (ISO creation)
      - [Process Lasso](https://bitsum.com/) (priority and affinity saver)
      - [Power Plan Settings Explorer](https://forums.guru3d.com/threads/windows-power-plan-settings-explorer-utility.416058/)
      - [Timer Resolution Service](https://forums.guru3d.com/threads/windows-timer-resolution-tool-in-form-of-system-service.376458/)
      - [NSudo](https://github.com/M2Team/NSudo)
      - [Compatibility Manager](https://github.com/Skymirrh/CompatibilityManager) (compatibility settings editor)
      - [VC++ Redist. AIO](https://www.techpowerup.com/download/visual-c-redistributable-runtime-package-all-in-one/) (TPU)
      - [VC++ Redist. AIO](https://github.com/abbodi1406/vcredist) (abbodi1406)
      - [Quick CPU](https://coderbag.com/product/quickcpu) (power plan management)
      - [MSI Utility](https://forums.guru3d.com/threads/windows-line-based-vs-message-signaled-based-interrupts-msi-tool.378044/) (interrupt mode and priority control)
      - [Microsoft Interrupt Affinity Policy Tool](http://download.microsoft.com/download/9/2/0/9200a84d-6c21-4226-9922-57ef1dae939e/interrupt_affinity_policy_tool.msi)
      - [USB Device Tree Viewer](https://www.uwe-sieber.de/usbtreeview_e.html)
      - [DeviceTree](https://www.osronline.com/article.cfm%5Earticle=97.htm)
  - ## Alternatives to bloated programs
    - Epic Games: [Legendary](https://github.com/derrod/legendary)
    - Spotify: [Foobar2000](https://www.foobar2000.org/)
    - Discord: [Ripcord](https://cancel.fm/ripcord/) ([use at your own risk](https://github.com/Bios-Marcel/cordless/blob/master/README.md#i-am-closing-down-the-cordless-project))
    - GHUB / LGS: [Logitech Onboard Memory Manager](https://support.logi.com/hc/en-us/articles/360059641133)
    - Antivirus software: [Virustotal](https://www.virustotal.com/gui/home/upload), [Hybrid Analysis](https://www.hybrid-analysis.com/) & [uBlock Origin](https://github.com/gorhill/uBlock)
    - Chrome: [Ungoogled Chromium](https://github.com/Eloston/ungoogled-chromium)
  - ## Miscellaneous
    - [Geizhals database](https://geizhals.eu/) (useful for finding specific hardware due to the very extensive filtering functionality)
    - [NVIDIA article on lag reduction](https://www.nvidia.com/en-us/geforce/guides/system-latency-optimization-guide/)
# [My Twitter](https://twitter.com/Bra1nlet)
# Keywords for Google indexing (ignore this)
input lag latency optimization performance gaming overclock oc windows ping debloat milliseconds fps boost increase decrease guide mouse tweak tweaks bios uefi pc overclocking 7 8.1 8 10 w7 w8 w8.1 w10 game gamer optimizations frametime frametimes 0.1 1 1080p 720p reaction time vrt average avg minimum maximum min max tweaking fortnite overwatch apex call of duty cs:go csgo dota league of legends valorant rocket league rainbow six pubg tarkov rust starcraft destiny ow fn cod lol kovaak aim trainer krunker battlefield bf roblox delay delayed bloat bloated debloated steam battle origin epic games quake counter strike battle royale br intel nvidia pascal turing ampere reflex amd ati ryzen r9 r7 r5 r3 radeon rdna core i9 i7 i5 i3 memory ram gpu ssd nvme psu power supply emi emf emc ef power electricity coupling interference
