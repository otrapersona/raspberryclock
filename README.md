# raspberryclock
raspberrypi + 80x24 screen= clock

It looks like this but prettier
```
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

# Install instructions:<br />
-Easiest method<br />
As the user "pi" which must be configured to autologin to cli insert these spooky commands
  ```
  sudo apt-get install git -y
  git clone https://github.com/otrapersona/raspberryclock
  cd raspberryclock
  chmod +x raspberryclock
  ./raspberryclock
  ```
-Best method<br />
Follow your heart

# Uninstall instructions:<br />
-Delete "clockwork" and "orange" from ~/opt/bin<br />
-Delete the following lines from .bashrc<br />
```
if ! screen -list | grep -q "clockscreen"; then
	if ! ps -C orange|tr -dC orange|grep -q "orange"; then
	screen -S clockscreen -s ~/opt/bin/orange
	fi
fi
```
-Remove dependencies you no longer need<br />
(weather-util, watch, figlet, screen, toilet)
