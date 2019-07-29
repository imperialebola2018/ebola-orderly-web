## Ebola OrderlyWeb configuration

### Prerequisites

First, install the deploy tool (this will be installable from the python package repository soon)

```
git clone https://github.com/vimc/orderly-web-deploy
cd orderly-web-deploy
pip3 install -r requirements.txt
python3 setup.py install --user
```

Ensure that the path that the script is copied into is in your path (on Linux, most likely `~/.local/bin`, on OSX `~/Library/Python/<version>/bin`

### Start

```
orderly-web start config
```

Preparing the volume

```
docker run -it --rm -v ${PWD}/.ssh:/root/.ssh:ro -v ebola_orderly_volume:/orderly ubuntu
apt-get update && apt-get install -y git
git clone git@github.com:imperialebola2018/ebola-outputs /orderly
git -C /orderly checkout mrc-328
```
