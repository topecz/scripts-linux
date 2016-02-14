# Update the raspbian with freeswitch intallation
#############################################
## update rasp2 software
## Tmux

https://www.raspbian.org/RaspbianRepository
https://www.raspberrypi.org/forums/viewtopic.php?f=66&t=47944

https://welldefinedbehaviour.wordpress.com/2015/07/17/upgrading-the-raspberry-pi-2-from-wheezy-to-jessie/

TODAY=$(date +"%Y-%m-%d")
REPO="/etc/apt/sources.list.d/my_own_repo.list"
echo "${TODAY}" >> ${REPO}
echo "deb http://archive.raspbian.org/raspbian wheezy main contrib non-free" >> ${REPO}
echo "deb-src http://archive.raspbian.org/raspbian wheezy main contrib non-free" >> ${REPO}
wget https://archive.raspbian.org/raspbian.public.key -O - | sudo apt-key add -
aptitude update && aptitude -y upgrade && aptitude -y dist-upgrade

