Issues while setting up the Raspiblitz V1.3 with parts from CH shoppinglist
---------------------------

https://github.com/rootzoll/raspiblitz/blob/master/shoppinglist_ch.md


**3.5inch RPi LCD (B) Waveshare is not working**
------------------------------------------------
This LCD doesn't work with preconfigured drivers.

***Delete preconfigured drivers and install V2 of the LCD35 driver:***

```
sudo rm -rf LCD-show
git clone https://github.com/waveshare/LCD-show
chmod -R 755 LCD-show
cd LCD-show/
sudo ./LCD35-show-V2
```


**Flickering screen / slow boot up**
------------------------------------

It takes over an hour until a ssh connection is possible and the screen is flickering during the boot process.

***Errors in /var/log/boot.log:***

```
admin@haui:/var/log $ sudo cat boot.log | grep -a 'FAILED'
[FAILED] Failed to start …lymouth Boot Screen.
```

***Remove plymouth packages:***

``sudo apt-get purge plymouth``

https://github.com/rootzoll/raspiblitz/issues/898



