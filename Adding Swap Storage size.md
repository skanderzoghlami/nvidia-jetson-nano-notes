# Increase Swap Storage size
The course runs best if there is a "swap" file of size 4GB, so that if the Jetson Nano is a little short of RAM it can extend a bit by swapping with some of the (slower) disk space. After setting up the microSD card and booting the system, check your memory and swap values with this command, which shows the values in megabytes. You should see 4071 as the size of the swap if you have 4GB configured:

free -m



# Disable ZRAM:
sudo systemctl disable nvzramconfig

# Create 4GB swap file
sudo fallocate -l 4G /mnt/4GB.swap
sudo chmod 600 /mnt/4GB.swap
sudo mkswap /mnt/4GB.swap

# Append the following line to /etc/fstab
sudo su
echo "/mnt/4GB.swap swap swap defaults 0 0" >> /etc/fstab
exit

# REBOOT!