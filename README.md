
## Installation steps

```sh
sudo apt-get install build-essential python3-dev libssl-dev libffi-dev

# install buildbot outside of venv for easy access
pip3 install --upgrade pip
pip3 install 'buildbot[bundle]'

#setup main in one terminal
cd buildbot/main
python3 -m venv venv
source venv/bin/activate

# Setup worker venv in another terminal
cd buildbot/main
python3 -m venv venv
source venv/bin/activate
```

## Spinning this up for local testing

Start buildbot main and worker:
```sh
cd buildbot/main
buildbot start my_master

cd -
cd buildbot/worker
buildbot-worker start my_worker
```

Buildbot should be available at http://localhost:8010

## Fastbuild integration
Fastbuild should just work^tm with the current simple two file structure.

## Cheatsheet built from buildbot docs

Checking config:
```sh
buildbot checkconfig master.cfg
```

Updating config:
```sh
buildbot reconfig master
```


## References

Seems like a decent blog on sequencing by OpenVPN guy
https://www.puppeteers.net/blog/buildbot-build-order-how-to-run-certain-builds-before-others/