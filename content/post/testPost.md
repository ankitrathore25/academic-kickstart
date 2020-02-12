+++
title = "How to install Ubuntu 16.04 server ASUS GPU machine" 
date = 2018-12-21T00:00:00

# Authors. Comma separated list, e.g. `["Bob Smith", "David Jones"]`.
authors = ["AR"]

#List format.
#0 = Simple
#1 = Detailed
#2 = Stream
list_format = 2

# Tags (optional).
#   Set `tags = []` for no tags, or use the form `tags = ["A Tag", "Another Tag"]` for one or more tags.
tags = ["Server","Installation"]

# Step to follow.
Desable_Secure_boot_in_ASUS_machine="1) Enter Boot Menu."
advancemenuimg=""


#Optional featured image (relative to static/img/ folder).
[header] 
image = "" 
caption = "" 
+++
1)[Disable boot menu in ASUS machine](../disable-secure-boot-asus-machine)<br />
2)[Download Ubuntu 16.04LTS](http://releases.ubuntu.com/16.04/)<br />
3)Creat bootable USB drive in UEFI mode( I used rufus software)<br />
{{< figure src="/img/ubuntu_1604_28.JPG" title="" >}}
4)Go to bios and keep USB drive (boot medium) at priority<br />
5)Save and exit<br />
6)Select Install with the HWE kernel<br />
{{< figure src="/img/ubuntu_1604_1.JPG" title="" >}}
7)Select Install ubuntu server<br />
{{< figure src="/img/ubuntu_1604_2.JPG" title="" >}}
8)Select all required option like language, country etc to next screen<br />
9)Enter host Name<br />
{{< figure src="/img/ubuntu_1604_3.JPG" title="" >}}
10)Enter user name and password<br />
{{< figure src="/img/ubuntu_1604_4.JPG" title="" >}}
11)Unmount partition (These steps are for fresh installation from scratch, don’t follow if you don’t want to format your data)<br />
{{< figure src="/img/ubuntu_1604_5.JPG" title="" >}}
12)Select manual partition<br />
13)Select partition and create new partition<br />
{{< figure src="/img/ubuntu_1604_6.JPG" title="" >}}
14)Select partition space<br />
15)Create new partition<br />
{{< figure src="/img/ubuntu_1604_7.JPG" title="" >}}
16)Select partition size<br />
{{< figure src="/img/ubuntu_1604_8.JPG" title="" >}}
17)Done setting (External hard disk use as /home directory to save data if OS crash in future)<br />
{{< figure src="/img/ubuntu_1604_9.JPG" title="" >}}
18)Select free space from ssd<br />
19)Create 256 MB of memory for EFI partition (for the UEFI boot information)<br />
{{< figure src="/img/ubuntu_1604_11.JPG" title="" >}}
20)Select created partition<br />
{{< figure src="/img/ubuntu_1604_14.JPG" title="" >}}
21)Select use as<br />
{{< figure src="/img/ubuntu_1604_13.JPG" title="" >}}
22)Change it to EFI system partition<br />
{{< figure src="/img/ubuntu_1604_15.JPG" title="" >}}<br />
{{< figure src="/img/ubuntu_1604_16.JPG" title="" >}}
23)Select Done setting and partition<br />
{{< figure src="/img/ubuntu_1604_17.JPG" title="" >}}
24)Select free space<br />
{{< figure src="/img/ubuntu_1604_19.JPG" title="" >}}
25)Create 16 GB of swap memory<br />
{{< figure src="/img/ubuntu_1604_20.JPG" title="" >}}
26)Create 16 GB of swap memory<br />
{{< figure src="/img/ubuntu_1604_20.JPG" title="" >}}
{{< figure src="/img/ubuntu_1604_21.JPG" title="" >}}
{{< figure src="/img/ubuntu_1604_22.JPG" title="" >}}
{{< figure src="/img/ubuntu_1604_23.JPG" title="" >}}
27)Select remaining free space and  mount it as root directory<br />
{{< figure src="/img/ubuntu_1604_24.JPG" title="" >}}
28)Select Finish partition and write change to disk<br />
{{< figure src="/img/ubuntu_1604_25.JPG" title="" >}}
29)Select Finish partition and write change to disk<br />
{{< figure src="/img/ubuntu_1604_25.JPG" title="" >}}
{{< figure src="/img/ubuntu_1604_26.JPG" title="" >}}
30)Select OpenSSH server from software selection screen<br />
{{< figure src="/img/ubuntu_1604_27.JPG" title="" >}}
31)Install unity desktop<br />
&nbsp;  &nbsp;  &nbsp;  &nbsp; a)sudo apt-get update<br />
&nbsp;  &nbsp;  &nbsp;  &nbsp; b)sudo apt-get install ubuntu-desktop<br />
&nbsp;  &nbsp;  &nbsp;  &nbsp; c)sudo shutdown -r now<br />
32)Install the NVIDIA display driver <br />
&nbsp;  &nbsp;  &nbsp;  &nbsp; a)sudo add-apt-repository ppa:graphics-drivers/ppa<br />
&nbsp;  &nbsp;  &nbsp;  &nbsp; b)sudo apt-get update<br />
&nbsp;  &nbsp;  &nbsp;  &nbsp; c)sudo ubuntu-drivers devices(Check recommended version which need to install)<br />
&nbsp;  &nbsp;  &nbsp;  &nbsp; d)sudo ubuntu-drivers autoinstall<br />
&nbsp;  &nbsp;  &nbsp;  &nbsp; e)sudo shutdown -r now<br />
&nbsp;  &nbsp;  &nbsp;  &nbsp; f)nvidia-smi<br />
33)Create New sudo user <br />
&nbsp;  &nbsp;  &nbsp;  &nbsp; a)sudo adduser username<br />
&nbsp;  &nbsp;  &nbsp;  &nbsp; b)sudo usermod -aG sudo username<br />
&nbsp;  &nbsp;  &nbsp;  &nbsp; c)Test sudo access<br />
&nbsp;  &nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp;  &nbsp;  &nbsp; A)su – username<br />
&nbsp;  &nbsp;  &nbsp;  &nbsp; &nbsp;  &nbsp;  &nbsp;  &nbsp; B)sudo whoami<br />
34)Install ssh <br />
&nbsp;  &nbsp;  &nbsp;  &nbsp; a)sudo apt-get update<br />
&nbsp;  &nbsp;  &nbsp;  &nbsp; b)sudo apt-get upgrade<br />
&nbsp;  &nbsp;  &nbsp;  &nbsp; c)sudo apt-get install openssh-server<br />
35)Install tmax <br />
&nbsp;  &nbsp;  &nbsp;  &nbsp; a)sudo apt-get update<br />
&nbsp;  &nbsp;  &nbsp;  &nbsp; b)sudo apt-get install tmux<br />