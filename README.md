# singularity-docker-ubuntu-lts16.04-calibre
calibre version 4.x singularity container on ubuntu-16.04 LTS (same build host as upstream?)

Download the container
```
singularity pull calibre.sif library://tru/default/ubuntu-lts16.04-calibre
or 
singularity pull calibre.sif library://tru/default/calibre
```

Run it with:
```
singularity exec -B /run  calibre.sif  bash -c "LC_ALL=C /opt/calibre/calibre $@"
```

This is not an official/supported version from upstream (https://calibre-ebook.com).
It is downloading their binary build, in a Ubuntu 16.04 container, and is provided as-is.
