# apex-change-defaut-page-from-4550-to-100
apex-change-defaut-page-from-4550-to-100

Assume we are using: ords

Look at the ```misc.defaultPage``` parameter in your ORDS configuration file (```default.xml```). 

the default value is ```apex```.

then, changed from

```<entry key="misc.defaultPage">f?p=apex</entry>```

to 

```<entry key="misc.defaultPage">f?p=100</entry>```
 
When you enter to the url: ```http://hostname:8080/ords```, ORDS will be redirected to ```http://hostname:8080/ords/apex``` , because ```apex``` is currently set as the default value, then ```apex``` will be redirected to ```http://hostname:8080/ords/f?p=4550:1```, ```4550:1``` is the APEX developer login page.

Or you can change using:

```java -jar ords.war set-property misc.defaultPage f?p=100:1:0```

And then restart the ORDS.


