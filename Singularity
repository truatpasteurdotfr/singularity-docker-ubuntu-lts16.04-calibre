Bootstrap: docker
From: ubuntu:16.04

%post
mkdir -p /selinux /misc /net
mkdir -p /pasteur
mkdir -p /local-storage /mnt/beegfs /baycells/home /baycells/scratch /c6/shared /c6/eb /local/gensoft2 /c6/shared/rpm /Bis/Scratch2 /mnt/beegfs
mkdir -p /c7/shared /c7/scratch /c7/home

# non interactive debian
export DEBIAN_FRONTEND=noninteractive
apt-get update && apt-get -y upgrade
# calibre requirements:
apt-get -y install xzdec curl libx11-dev libgl1-mesa-dev python-pyqt5 libnss3

mkdir -p /opt/calibre
curl \
https://download.calibre-ebook.com/4.5.0/calibre-4.5.0-x86_64.txz \
| xzdec | tar -C /opt/calibre -xf - && /opt/calibre/calibre_postinstall

%runscript
PATH=/opt/calibre/:${PATH}
export PATH
LANG=C /opt/calibre/calibre "$@"
