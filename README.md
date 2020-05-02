# Personal Pimutils Configs

## Setup

### vdirsyncer

```sh
sudo apt install seahorse libsecret-tools
secret-tool store --label=keepassxc name keepassxc
ln -s $(pwd)/vdirsyncer/config ~/.vdirsyncer/config
ln -s $(pwd)/vdirsyncer/get-password.sh ~/.vdirsyncer/get-password.sh
vdirsyncer discover
```

Manual sync

```
vdirsyncer sync
```

Automate sync

```sh
mkdir -p ~/.local/share/systemd/user
curl -o ~/.local/share/systemd/user/vdirsyncer.service https://raw.githubusercontent.com/pimutils/vdirsyncer/master/contrib/vdirsyncer.service
curl -o ~/.local/share/systemd/user/vdirsyncer.timer https://raw.githubusercontent.com/pimutils/vdirsyncer/master/contrib/vdirsyncer.timer
systemctl --user enable vdirsyncer.time
# view logs
journalctl --user -u vdirsyncer
```


### khal

__NB:__ Set timezone to `Africa/Harare` for Android 7. 

[Usage examples](http://lostpackets.de/khal/usage.html#examples)

Link config

```sh
ln -s $(pwd)/khal/config /home/cm/.config/khal/config
```

Show events for week

```sh
khal list today 7d
```

### todomann

[Usage examples](https://todoman.readthedocs.io/en/stable/usage.html)

```sh
mkdir -p /home/cm/.config/todoman
ln -s $(pwd)/todoman/todoman.conf ~/.config/todoman/todoman.conf
ln -s $(which todoman) ~/bin/todo
```

## Resources

- [Running as a systemd.timer](http://vdirsyncer.pimutils.org/en/stable/tutorials/systemd-timer.html)
- [Automatize your logins with gnome-keyring (and optionally with KeePassXC)](https://isamert.net/jekyll/update/2018/10/05/automatize-your-logins-with-gnome-keyring-and-keepassxc.html)
- [Simple Mobile Tools](https://www.simplemobiletools.com/)
