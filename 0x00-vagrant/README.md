Using Vagrant on the Holberton computers
0-Day

Why use Virtual Machines? And why Vagrant?
We’re glad that you’re adapting to the Holberton Framework! Always ask why!
It is important to ask yoursef: “Why am I not just developing on my computer? I have all the tools I need!”.

My machine vs. virtual environments
Your computer’s environment - whether it’s Windows, MacOS or a Linux distribution - will change a lot over time, with or without you noticing. You will install applications, games, tools, … that will require and install different dependencies and at the end of the day you can end up having completely different behaviors or even have something not work because of software conflicts.

We won’t go into the details of Virtual Machines, but as their name tells, they are Virtual “Computers” that will emulate everything from the CPU to the RAM and Disk. Virtual Machines in the context of development are a means to isolate and maintain a stable environment that will basically run the same way on any host (any computer). This way, you can have any software installed on your Windows, MacOS, or whatever Linux distribution; your Virtual Machine will run its own environment, have its own programs, with their own versions, etc.

Using virtual environments prevents developers from saying “I don’t understand, it works on my machine …”. Here at Holberton, we want to make sure that you have access to the same environment that will be used to correct your work (the Checker).

The tools
There are multiple tools out there that can help you create and manage virtual environments (notice that we use the term “virtual environment” here, as such environemnt is not necessarily a VM. Technologies using containerization allow one to manage virtual environments as well).
We are using two tools at Holberton: VirtualBox and Vagrant.

VirtualBox is a Virtual Machine provider. The virtual machines themselves will be spawned using VirtualBox. VirtualBox is free and lightweight, which make it a perfect choice for us.

Vagrant is a tool that sits on top of a VM provider. Again, we chose to use VirtualBox as a provider, but other providers exist out there and Vagrant offers the possibilty to use dfferent providers (More info here). Just like VirtualBox, we choose to use Vagrant because it is free, reliable and well maintained. Keep in mind that the purpose here is to use Virtual environments, and both VirtualBox and Vagrant are just means to achieve this purpose.

Alternatives
As mentioned previously, using VirtualBox and Vagrant at Holberton doesn’t mean that all companies are going to work exactly the same way. Different tools are used, as well as different development workflows. We want you to understand how important it is to isolate your development environment from any host machine, whether it’s your personal computer or one of the school’s computers.

Here are some examples of other softwares out there that are widely used to manage virtual environments:

The VMWare products
VMWare is one of the biggest virtualization company in the industry.
It is safe to say that their tools are among the most reliable.
On the other hands, most of their tools come for a price.
Docker
Containerization is a very good and efficient alternative to VMs for development environments
Containers are much more lightweight than VMs, thus much faster to start and stop.
The inconvinience of containers is that they sit on top of your OS. Unlike virtual machines, they don’t emulate the hardware, but rather share your machine’s hardware. We won’t go into the details of how containerization works, but to keep it simple, that means that if you run MacOS, it is not possible to run a Linux or Windows container. (Docker makes it work using VMs).
More info here
Conclusion
VirtualBox and Vagrant together allow you to manage and ship isolated development environments. Those isolated environments in the context of Holberton (and in the future, in the context of a company) allow you to match the environment we use to automatically check your work.
Although both VirtualBox and Vagrant are widely used in the industry, it doesn’t mean it is the only means to achieve virtualization, and other tools exist with their pros and cons.

Vagrant basics – or how to run Ubuntu on the Holberton computers
If you are using your own computer, please install vagrant before going any further.

Vagrant provides easy to configure, reproducible, and portable work environments built on top of industry-standard technology and controlled by a single consistent workflow to help maximize the productivity and flexibility of you and your team. You can read more about vagrant here.

Open a terminal and run vagrant box list will print the list of boxes available on the computers.

p7-3:~ 27$ vagrant box list
modernIE/w10-edge (virtualbox, 0.0.3)
ubuntu/trusty64 (virtualbox, 20160108.0.0)
In this example, we have two VM images: - Windows 10 (moderIE/w10-edge) - Ubuntu (ubuntu/trusty64)

If you do not see any boxes, please run this command and try again.

p7-3:~ 27$ export VAGRANT_HOME=/Users/Shared/.vagrant.d/
To initialize vagrant (create a Vagrantfile) run the following command: vagrant init.

p7-3:~ 27$ vagrant init
A `Vagrantfile` has been placed in this directory. You are now
ready to `vagrant up` your first virtual environment! Please read
the comments in the Vagrantfile as well as documentation on
`vagrantup.com` for more information on using Vagrant.
Open the file Vagrantfile with your favorite editor (probably Emacs or vi). Find the config.vm.box variable and replace base or any other value with your Ubuntu VM name, in this case ubuntu/trusty64. It should look something like this when you open the Vagrantfile for the fist time:

# Every Vagrant development environment requires a box. You can search for
# boxes at https://atlas.hashicorp.com/search.

config.vm.box = "base"
Save your Vagrantfile and go back to your shell. Run vagrant up to start the virtual machine.

p7-3:~ 27$ vagrant up
Bringing machine 'default' up with 'virtualbox' provider...
==> default: Importing base box 'ubuntu/trusty64'...
==> default: Matching MAC address for NAT networking...
==> default: Checking if box 'ubuntu/trusty64' is up to date...
==> default: A newer version of the box 'ubuntu/trusty64' is available! You currently
==> default: have version '20160108.0.0'. The latest is version '20160122.0.0'. Run
==> default: `vagrant box update` to update.
==> default: Setting the name of the VM: 27_default_1454011316873_96446
==> default: Clearing any previously set forwarded ports...
==> default: Clearing any previously set network interfaces...
==> default: Preparing network interfaces based on configuration...
default: Adapter 1: nat
==> default: Forwarding ports...
default: 22 (guest) => 2222 (host) (adapter 1)
==> default: Booting VM...
==> default: Waiting for machine to boot. This may take a few minutes...
default: SSH address: 127.0.0.1:2222
default: SSH username: vagrant
default: SSH auth method: private key
default:
default: Vagrant insecure key detected. Vagrant will automatically replace
default: this with a newly generated keypair for better security.
default:
default: Inserting generated public key within guest...
default: Removing insecure key from the guest if it's present...
default: Key inserted! Disconnecting and reconnecting using new SSH key...
==> default: Machine booted and ready!
==> default: Checking for guest additions in VM...
default: The guest additions on this VM do not match the installed version of
default: VirtualBox! In most cases this is fine, but in rare cases it can
default: prevent things such as shared folders from working properly. If you see
default: shared folder errors, please make sure the guest additions within the
default: virtual machine match the version of VirtualBox you have installed on
default: your host and reload your VM.
default:
default: Guest Additions Version: 4.3.34
default: VirtualBox Version: 5.0
==> default: Mounting shared folders...
default: /vagrant => /Users/27
In order to go into your VM, run the vagrant ssh command.

p7-3:~ 27$ vagrant ssh
Welcome to Ubuntu 14.04.3 LTS (GNU/Linux 3.13.0-74-generic x86_64)

* Documentation: https://help.ubuntu.com/

System information as of Thu Jan 28 20:02:16 UTC 2016

System load: 0.2 Processes: 81
Usage of /: 3.4% of 39.34GB Users logged in: 0
Memory usage: 25% IP address for eth0: 10.0.2.15
Swap usage: 0%

Graph this data and manage this system at:
https://landscape.canonical.com/

Get cloud support with Ubuntu Advantage Cloud Guest:
http://www.ubuntu.com/business/services/cloud

0 packages can be updated.
0 updates are security updates.

vagrant@vagrant-ubuntu-trusty-64:~$
That’s it! You are now in your Ubuntu VM.