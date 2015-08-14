Packer Nucivic VM
=================

These are the Packer instructions for building fully provisioned Vagrant
Virtual boxes (or Fusion VM Desktops) from the NuCivic [ansible-dev-vm Playbook][1]

This configuration is used to provision the boxes at
https://atlas.hashicorp.com/dkinzer/boxes/ansible-dev-vm

## Building Instructions:

### Requirements
```
brew cask update
brew cask install packer
```

### Intallation
```
git clone --recursive  nucivic/packer-dev-vm
cd packer-dev-vm/ansible-dev-vm/
rm -fR .git
ansible-galaxy install -r requirements.txt -p ./roles
cp config.yml.sample config.yml
```

## Building
```
# Make your changes to the template.json before running then push changes.
# Example:

ATLAS_TOKEN=<your-token> packer push -name=dkinzer/ansible-dev-vm template.json
```
[1]: https://github.com/nucivic/ansible-dev-vm
