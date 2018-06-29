# Using NFS in Homestead / Vagrant on Windows

- Navigate to your Homestead directory, for me that's:
    ```bash
    cd ~/Homestead
    ```
- Install NFS for vagrant:
    ```bash
    vagrant plugin install vagrant-winnfsd
    ```
- SSH into the VM (one of the following):
    ```bash
    vagrant ssh
    vagrant ssh %ip/hostname of the VM%
    ```
- Edit Homestead config:
    ```bash
    nano ~/.homestead/Homestead.yaml
    ```
- Within the file, add NFS to `folders`:
    ```yml
    folders:
        - map: ~/code
          to: /home/vagrant/code
          type: "nfs"
    ```

- When using NFS, you should consider installing the [vagrant-bindfs](https://github.com/gael-ian/vagrant-bindfs) plug-in. This plug-in will maintain the correct user / group permissions for files and directories within the Homestead box.
    ```bash
    vagrant plugin install vagrant-bindfs
    ```


## Oh my ZSH

Optional, but fun addition: Check out Oh-My-ZSH. It's pretty damn cool.

```bash
sudo apt-get update && sudo apt-get install zsh -y && sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```
