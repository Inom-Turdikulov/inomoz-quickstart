# My quick-start archlinux installation workflow

# NOT TESTED!

Clone this repository and run commands in the project root directory.

1. First, sync mirrors and install Ansible with dependencies

```shell
sudo pacman -Syy python-passlib ansible
```

2. Second, install and update the submodules, check carefully group_vars/all file (configuration).

```shell
git submodule init && git submodule update
```

3. Run the playbook as root (playbooks will use group_vars/all configuration, including username).

```shell
sudo ansible-playbook -i localhost playbook.yaml
```

4. It's recommended to reboot, to validate the installation.

```shell
reboot
```

# Info

some directories are preconfigured, you can change them if you want
for example in user.yml "/mnt/var/" used as prefix for logs

# Special thanks

- https://github.com/pigmonkey/spark

# TODO

- systemd... resolv.... ntp
- user ssh key info
- validate systemd enabled services, like reflector
- https://habr.com/ru/post/479540/
- https://venthur.de/2021-12-19-managing-dotfiles-with-stow.html

# Manual tests

ArchLinux 5.18.16-arch1-1

Some tests on complex tasks:

- [ ] android, `adb devices` - show some devices connected, if they are connected
 
- [ ] base, contains a lot of packages and require a lot of time to install
    - [ ] check pacman mirrors `sudo pacman -Syy`, must include core, extra, community, multilib
    - [ ] validate hostname `hostname -f`
    - [ ] validate group `id`
    - [ ] validate logrotate `logrotate --debug /etc/logrotate.conf`, home/...
    - [ ] run some applications: `tmux`, `git`, `ytfzf`, `ledger`, `ipython`, `sc-im`,  `bash`, `zsh`,  `krita`
      , `inkscape`, `darktable`, `blender`, `godot`, `maim`,
    - [ ] validate paccache service `systemctl status paccache.timer`

- [ ] media

- [ ] browsers:
    - w3m, lynx
    - using rofi: firefox, chromium, qutebrowser... can open url: http://acid3.acidtests.org/
      , `xdg-open http://acid3.acidtests.org/`
    - some browsers at first time require manual launch or extra configuration (tor browser)

- [ ] clipboard
- [ ] colemak-dh, vconsole works, ru layout works
- [ ] cups
- [ ] dconf
- [ ] dotfiles
- [ ] editors
- [ ] filesystems
- [ ] firejail
- [ ] fonts
- [ ] gnupg
- [ ] goesimage
- [ ] logitech
- [ ] mirrorlist
- [ ] mpv
- [ ] nettools
- [ ] office
- [ ] onlykey
- [ ] pass
- [ ] pdf
- [ ] postgresql
- [ ] pydev
- [ ] qbittorrent-nox
- [ ] ripgrep
- [ ] sound
- [ ] spell
- [ ] ssh
- [ ] sysctl
- [ ] sysmon
- [ ] systemd
- [ ] systemd-units
- [ ] udisks
- [ ] virtualenv
- [ ] visidata
- [ ] x
- [ ] zeal
