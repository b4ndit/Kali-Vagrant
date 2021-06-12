# kali-vagrant

## Setup
First, install [packer](https://www.packer.io/) and [VirtualBox](https://www.virtualbox.org/).

On Kali Linux, this can be accomplished by running
```
apt install packer virtualbox virtuabox-ext-pack
```

Then `cp kali-vars.json.template kali-vars.json` and fill the values.

## Running the build

```
packer build -var-file=kali-vars.json config.json
```

This will upload to the Vagrant cloud.
To avoid doing that and keeping the build local, remove the `vagrant-cloud` post-processor from the config file.

## Running the build (headless)
To run headless builds, you will need to ensure you have the Extension Pack installed and then edit the config.json file to add
```
"headless": "1",
```
In the `"builders"` section before `"boot_command"`
