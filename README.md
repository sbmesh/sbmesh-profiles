# sbmesh network profiles

LibreMesh network profiles for the [Santa Barbara Mesh](http://sbmesh.net) project.

To be used with the [lime-sdk](https://github.com/libremesh/lime-sdk) firmware cooker.

Supported devices:
- Ubiquiti NanoStation M5 (XW)


## Build Instructions

### Requirements

- NanoStation M5 (XW) w/ airOS downgraded to v5.5.10
- VM or build environment similar to the [Vagrantfile](https://github.com/sbmesh/sbmesh-profiles/blob/master/Vagrantfile) in this repo


### Preparing the environment

```
git clone https://github.com/libremesh/lime-sdk.git
cd lime-sdk
```

Update **options.conf** to fetch our network profiles:

`nano options.conf`

Replace **communities_git** to:

`communities_git=https://github.com/sbmesh/sbmesh-profiles.git`

Save file.

### Cook the firmware

**Note:** Running `umask 022` might only be necessary in our particular Vagrant instance
umask 022
./cooker -c ar71xx/generic --profile=ubnt-nano-m-xw --flavor=lime_default --community=ubnt-nano-m-xw/default --remote
```

Images will be in `output/`.
