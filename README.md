# interesting linux tidbits
thanks to terry

## Distros
### Arch
https://archlinux.org/ - Probably the best desktop distro.

Pros:
- rolling release (software is always most recent)
- you will most likely always find anything you're looking for
- one of the most popular distros
- best documentation
- manual installation giving more control.

Cons:
- rolling release (software can sometimes be buggy or break, this can be avoided by doing snapshots, not updating the system daily and reading the arch news)
- not "minimal" despite the claims of some users
- AUR can potentially be insecure and unstable

### openSUSE
https://www.opensuse.org/ - Great for newcomers from Windows

Pros:
- Very powerful GUI control panel "YasT" 
- Rolling and LTS releases
- Great integration of KDE making it even easier for Windows users to switch.
- Backed by a big company and paid developers, direct competitors to redhat.

Cons:
- codecs have to be manually installed because of licensing issues, often skipped by people that didnt read properly. (https://en.opensuse.org/Additional_package_repositories)
- Backed by a big company take that how you want.
      
### Others:
https://www.debian.org/ - Stable or SID (testing)

https://linuxmint.com/ - based on Ubuntu but better, apparently very easy for windows users.

http://puppylinux.com/ - for very old laptops or computers.

Avoid: 
Ubuntu - the company behind it (Canonical) has been doing some shady stuff lately and are pushing their closed source package manager "snap" to become the standard on ubuntu. Use Mint instead.

Any "bastard" distro - for example Manjaro and Garuda, distros that are based on independent distros but change nothing other than adding a installer (for example) and pre configured desktops, they are inferior in every way learn doing it yourself.

Fedora - become unpaid beta tester for redhat.

## Desktop enviroment (DE)
Explaination: Although Xorg provides the basic framework for building a graphical environment, additional components may be considered necessary for a complete user experience.

Desktop environments such as GNOME, KDE, LXDE, and Xfce bundle together a wide range of X clients, such as a window manager, panel, file manager, terminal emulator, text editor, icons, and other utilities.

Users with less experience may wish to install a desktop environment for a more familiar environment

[None]
- If its not possible to live without one, look into LXQt or for the full Windows-like experience KDE. Others: MATE, Cinnamon, Xfce

Avoid: GNOME, anything else really (no matter how cool they look on the screen you saw on /r/unixporn, you can rice the others to look like that too).

## alternatives and other recommendations
[doas to replace sudo]
- doas is much simpler, easily configurable and probably better for most desktop users. sudo is for sysadmins that need more control

[xinit to replace Display Managers]
- we don't need a display manager and gain more freedom and control over what commands to run on startup. Read: https://wiki.archlinux.org/index.php/Start_X_at_login

[compositor]

[None] - If possible disable the compositor that comes with your DE
- a compositor can add A LOT of latency and we want to reduce this as much as possible. (Latency is also one of the reasons GNOME is not recommended)
- Wayland forces both compositing and vsync so its important to avoid it and use Xorg instead.

## ricing
https://scriptim.github.io/bash-prompt-generator/

https://terminal.sexy/

https://github.com/mbadolato/iTerm2-Color-Schemes

## QOL aliases
`alias cp="cp -i"` # ask before overwriting

`alias mv="mv -i"` # ask before overwriting

`alias ln='ln -i'` # ask before creating link

`alias rm="rm -I"` # ask before deleting recursively ( using -f will overwrite this )

`alias mkdir="mkdir -p"` # create directory (make parent directories as needed)

## useful wikis and other information
https://wiki.archlinux.org/ - most extensive wiki, in most cases applies to any distro.

https://wiki.gentoo.org/wiki/Main_Page - more advanced but sometimes more in depth than archwiki.

https://linux.die.net/man/ - linux man pages

## optimization
### latency
https://rigtorp.se/low-latency-guide/

https://access.redhat.com/sites/default/files/attachments/201501-perf-brief-low-latency-tuning-rhel7-v1.1.pdf

https://www.intel.com/content/www/us/en/developer/articles/technical/optimizing-computer-applications-for-latency-part-1-configuring-the-hardware.html

https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux_for_real_time/8/html-single/optimizing_rhel_8_for_real_time_for_low_latency_operation/index
### idk
#### useful:
https://github.com/clearlinux-pkgs/linux/blob/master/0108-smpboot-reuse-timer-calibration.patch ( decreases boot time )

https://github.com/clearlinux-pkgs/linux/blob/master/0120-use-lfence-instead-of-rep-and-nop.patch

https://github.com/clearlinux-pkgs/linux/blob/master/0112-kernel-time-reduce-ntp-wakeups.patch

https://github.com/clearlinux-pkgs/linux/blob/master/0105-ksm-wakeups.patch

#### no idea:
https://github.com/clearlinux-pkgs/linux/blob/master/0126-x86-microcode-echo-2-reload-to-force-load-ucode.patch

https://github.com/clearlinux-pkgs/linux/blob/master/0125-x86-microcode-Force-update-a-uCode-even-if-the-rev-i.patch

https://github.com/clearlinux-pkgs/linux/blob/master/0127-fix-bug-in-ucode-force-reload-revision-check.patch

#### useful to specific hardware only:
https://github.com/clearlinux-pkgs/linux/blob/master/0119-add-scheduler-turbo3-patch.patch

( https://ark.intel.com/content/www/us/en/ark/search/featurefilter.html?productType=873&3_TurboBoostMaxTechMaxFreq-Min=3800&3_TurboBoostMaxTechMaxFreq-Max=5200&1_Filter-Family=122139 )

#### included in tkg ( https://github.com/Frogging-Family/linux-tkg/blob/master/linux-tkg-patches/5.10/0002-clear-patches.patch ):
https://github.com/clearlinux-pkgs/linux/blob/master/0106-intel_idle-tweak-cpuidle-cstates.patch

https://github.com/clearlinux-pkgs/linux/blob/master/0104-pci-pme-wakeups.patch ( only specific to laptops? )

https://github.com/clearlinux-pkgs/linux/blob/master/0111-ipv4-tcp-allow-the-memory-tuning-for-tcp-to-go-a-lit.patch

https://github.com/clearlinux-pkgs/linux/blob/master/0122-locking-rwsem-spin-faster.patch

https://github.com/clearlinux-pkgs/linux/blob/master/0109-initialize-ata-before-graphics.patch
