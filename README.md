# Simple Linux Driver
## Build memo

sudo apt install -y git build-essential

sudo make load 

## Test

to find driver major number

cat /proc/devices | grep Simple-driver  

    240 Simple-driver  
or

sudo dmesg | grep -E "Simple-driver:.+major number = [0-9]+"

    [ 1177.712889] Simple-driver: registered character device with major number = 240 and minor numbers 0...255

create char device via **major number**

sudo mknod /dev/simple-driver c  240 0

cat /dev/simple-driver 

    Hello world from kernel mode!
