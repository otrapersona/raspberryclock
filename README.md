# raspberryclock
raspberrypi + 80x24 screen= clock

It looks like this but prettier

```text
               ____   _____    _  _        _  _  _    __     ____
              |___ \ |___ / _ / |/ |      / || || |  /  \   / ___|
                __) |  |_ \(_)| || |      | || || |_| () | | |
               / __/  ___) |_ | || |      | ||__   _|\__/  | |___
              |_____||____/(_)|_||_|      |_|   |_|         \____|

                       _____       _      _
                      |  ___|_ __ (_)  __| |  __ _  _   _
                      | |_  | '__|| | / _` | / _` || | | |
                      |  _| | |   | || (_| || (_| || |_| |
                      |_|   |_|   |_| \__,_| \__,_| \__, |
                                                    |___/
                   ____   ___     __ _  ____      __ _   ___
                  |___ \ ( _ )   / // ||___ \    / // | ( _ )
                    __) |/ _ \  / / | |  __) |  / / | | / _ \
                   / __/| (_) |/ /  | | / __/  / /  | || (_) |
                  |_____|\___//_/   |_||_____|/_/   |_| \___/
    
```

## Install instructions:

### Easiest method

As the user "pi" which must be configured to autologin to cli insert these spooky commands

``` sh
git clone https://github.com/otrapersona/raspberryclock
cd raspberryclock
chmod +x raspberryclock
./raspberryclock
```

If it fails, you might not have git installed, in that case you need to insert the following

``` sh
sudo apt-get install git -y
```

### Best method

Follow your heart

## Uninstall instructions:

1. Delete "clockwork" and "orange" from ~/opt/bin

2. Delete the following lines from .bashrc

``` sh
if ! screen -list | grep -q "clockscreen"; then
	if ! ps -C orange|tr -dC orange|grep -q "orange"; then
	screen -S clockscreen -s ~/opt/bin/orange
	fi
fi
```

3. Remove dependencies you no longer need        
      (weather-util, watch, figlet, screen, toilet)

> note from Matus: I just reviewed the code, it works but it's kind of a mess from the time I knew a little bit less about bash scripting, take it as a base for your project and not as a completed "product".