# DroidCast

An experimental demo for capturing and displaying screenshot of Android devices.

Usage:
------

* Install the apk properly on the phone

```
./gradlew clean installDebug
```

* Start our internal server process for image processing by `app_process`  
```
$ adb shell
D1C:/ $ export CLASSPATH=/data/app/com.rayworks.droidcast-1/base.apk
D1C:/ $ exec app_process /system/bin com.rayworks.droidcast.Main '$@'
>>> DroidCast main entry
```

![](/process_main.png)

* Use `adb` forward socket connection from your pc to the connected device
```
$ adb forward tcp:53516 tcp:53516
```

* View the image via web browser
http://localhost:53516/screenshot.jpg

 ![](/screen-shot.png)


Reference: <br>
------
[vysor原理以及Android同屏方案](http://zke1ev3n.me/2016/07/02/vysor%E5%8E%9F%E7%90%86%E4%BB%A5%E5%8F%8AAndroid%E5%90%8C%E5%B1%8F%E6%96%B9%E6%A1%88/)

## License

[![Creative Commons License](https://i.creativecommons.org/l/by-nc-nd/3.0/88x31.png)](http://creativecommons.org/licenses/by-nc-nd/3.0/)

This work is licensed under a Creative Commons Attribution-NonCommercial-NoDerivs 3.0 Unported License.
