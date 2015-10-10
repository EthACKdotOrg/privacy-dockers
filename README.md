# privacy-dockers

## Project goal
You might already know [Qubes OS](https://www.qubes-os.org/) — this small project is just a test in order to see
if Docker might replace Xen.

## How to install
### Prerequists
* docker
* docker-compose
* some knowledge of [Alpine Linux](http://alpinelinux.org/)

### Create the base images
#### Firefox
```Bash
$ docker build -t ethack/firefox:latest firefox
```

#### Tor
```Bash
$ docker build -t ethack/tor:latest tor
```

### Run the composition
```Bash
$ docker-compose up -d
```

### Composition management
Please check [the documentation](https://docs.docker.com/compose/)

## Security
For now, it's only a test. Security is NOT TESTED, hence you just shouldn't use it in production.


## Why Docker?
Docker is light, fast, and, with compose, might prove to be really easy to use.

## Docker has no X… How do you access graphical application?
using ssh -Y. For now. We can probably have an easier way to do that.
