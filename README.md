# Nette Coding Standard Vagrant Project

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](/LICENSE)

This project allows you to run a [Nette Coding Standard](https://github.com/nette/coding-standard/) check&fix in environments with PHP &lt;7.1.

## Usage

### Install

Install [Vagrant](https://www.vagrantup.com/downloads.html) and [Virtualbox](https://www.virtualbox.org/wiki/Downloads).

### Synchronize project folder


Add project folder, you want to check, to `Vagrantfile`:

```ruby
Vagrant.configure("2") do |config|
  ...
  config.vm.synced_folder "path/to/project-to-check", "/vagrant_data/project-to-check"
  ...
end
```
> Note: You can add multiple project folders

### Style check &amp; fix

Now run Vagrant and connect via SSH.

```bash
$ vagrant up
$ vagrant ssh
```

Once you are connected via SSH move to `/vagrant` folder and run check&amp;fix.

```bash
$ ./ecs check /vagrant_data/project-to-check/app/ --config vendor/nette/coding-standard/coding-standard-php70.neon --fix
```

For more details read [Nette Coding Standard documentation](https://github.com/nette/coding-standard/). 
