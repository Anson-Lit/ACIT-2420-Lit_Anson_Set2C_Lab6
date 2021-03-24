# ACIT-2420-Linux-Admin-wk11-Lab

# Usage
This service and timer will generate a weather report as a text file using the wttr.in service. It will run at startup as well at the start of every hour.

# Installation
1. Download files onto your linux machine. 
2. Move weather.service and weather.timer into `/etc/systemd/systems`
3. Move the weather_script to a folder where you want the weather report textfile to be generated.
4. Edit the weather.service file. You will need to change the filepath of `ExecStart` to the path of the weather_script. Example: `ExecStart=/home/vagrant/weather/weather_script`
5. You will also need to change the filepath of `WorkingDirectory`to the directory containing the weather_script. 
6. Enable weather.service and weather.timer using systemctl.
```
sudo systemctl enable weather.service
sudo systemctl enable weather.timer
``` 
8. Reload the daemon list using: `sudo systemctl daemon-reload`

# Dependencies
cURL is required to use wttr.in. Install with:
```sudo apt install curl```
