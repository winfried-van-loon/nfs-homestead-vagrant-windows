
# Using NFS in Homestead / Vagrant on Windows

- Navigate to your Homestead directory, for me that's `~/Homestead`.
- Install NFS for vagrant: `vagrant plugin install vagrant-winnfsd`
- SSH into the VM: `vagrant ssh %ip/hostname of the VM%`
- Open NGINX config: `sudo nano /etc/nginx/nginx.conf`
- Within the config file, find `sendfile`, turn it off
- Restart NGINX: `sudo service nginx restart`
- Edit Homestead config: `nano ~/.homestead/Homestead.yaml`, 
- Within the file, add `type: "nfs"` to `folders`


## Oh my ZSH

Optional, but fun addition: Check out Oh-My-ZSH. It's pretty damn cool. 

```
sudo apt-get update && sudo apt-get install zsh -y && sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```


## Sources and more information

- https://laracasts.com/discuss/channels/general-discussion/for-those-who-find-homesteadvagrantvirtualbox-slow-on-windows
- https://websanova.com/blog/laravel/speeding-up-homestead-on-windows-using-nfs
- https://laracasts.com/discuss/channels/servers/how-do-i-setup-2-homestead-boxes-one-with-php-56-and-one-with-php-7
- https://enrise.com/2012/12/git-and-vagrant-in-a-windows-environment/
