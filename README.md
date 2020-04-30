# Personal Pimutils Configs

## Setup

### vdirsyncer

```sh
ln -s $(pwd)/vdirsyncer/config ~/.vdirsyncer/config
vdirsyncer discover
```

Manual sync

```
vdirsyncer sync
```

Automate sync

```sh
# auto sync
systemctl --user enable vdirsyncer.time
```

### khal

[Usage examples](http://lostpackets.de/khal/usage.html#examples)

Generate config

```sh
khal configure
```
See config

```sh
cat /home/cm/.config/khal/config
```

### todomann

[Usage examples](https://todoman.readthedocs.io/en/stable/usage.html)

```sh
mkdir -p /home/cm/.config/todoman
ln -s $(pwd)/todoman/todoman.conf ~/.config/todoman/todoman.conf
ln -s $(which todoman) ~/bin/todo
```

