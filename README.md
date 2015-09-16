# vagrant-synced-folders
While it is cool to have a virtual machine so easily, not many people want to edit files using just plain terminal-based editors over SSH


## Lesson 3: Web Application Servers -> Installing Apache
### Exercise

Update the **index.html** to simply display “Hello, World!” and refresh your browser to see your new page.

Editor options include:
- nano
- vim

```
nano /var/www/html/index.html
```

## Synced Folders to the Rescue

https://docs.vagrantup.com/v2/synced-folders/basic_usage.html

```
Vagrant.configure("2") do |config|
  config.vm.synced_folder "html/", "/var/www/html"
end
```

The first parameter is a path to a directory on the host machine. If the path is relative, it is relative to the project root. The second parameter must be an absolute path of where to share the folder within the guest machine. This folder will be created (recursively, if it must) if it doesn't exist.