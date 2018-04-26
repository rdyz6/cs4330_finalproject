# Properties
Most Java application need to use properties at some point, generally to store simple parameters as key-value pairs, outside of compiled code.
And so the language has first class support for properties – the java.util.Properties – a utility class designed for handling this type of configuration files.
That’s what we’ll focus on in this article.

## loading properties
- From properties files
```Java
version=1.0
name=TestApp
date=2016-11-12

c1=files
c2=images
c3=videos

String rootPath = Thread.currentThread().getContextClassLoader().getResource("").getPath();
String appConfigPath = rootPath + "app.properties";
String catalogConfigPath = rootPath + "catalog";
 
Properties appProps = new Properties();
appProps.load(new FileInputStream(appConfigPath));
 
Properties catalogProps = new Properties();
catalogProps.load(new FileInputStream(catalogConfigPath));
```
As long as a file’s content meet properties file format requirements, it can be parsed correctly by Properties class. Here are more details for Property file format.
## Get properties
We can use getProperty(String key) and getProperty(String key, String defaultValue) to get value by its key.
If the key-value pair exists, the two methods will both return the corresponding value. But if there is no such key-value pair, 
the former will return null, and the latter will return defaultValue instead.
```Java
String appVersion = appProps.getProperty("version");
String appName = appProps.getProperty("name", "defaultName");
String appGroup = appProps.getProperty("group", "baeldung");
String appDownloadAddr = appProps.getProperty("downloadAddr");
System.out.println(appVersion);
System.out.println(appName);
System.out.println(appGroup);
System.out.println(appDownloadAddr);
```
## Set properties
We can use setProperty() method to update an existed key-value pair or add a new key-value pair.
```Java
appProps.setProperty("name", "NewAppName"); // update an old value
appProps.setProperty("downloadAddr", "www.baeldung.com/downloads"); // add new key-value pair
String newAppName = appProps.getProperty("name");
String newAppDownloadAddr = appProps.getProperty("downloadAddr");
System.out.println("new app name: " + newAppName);
System.out.println("new app downloadAddr: " + newAppDownloadAddr);
```
Note that although Properties class inherits put() method and putAll() method from Hashtable class, 
I wouldn’t recommend you use them for the same reason as for get() method: only String values can be used in Properties.
## Remove properties
If you want to remove a key-value pair, you can use remove() method.
```Java
System.out.println("before removal, version is: " + appProps.getProperty("version"));
appProps.remove("version");
System.out.println("after removal, version is: " + appProps.getProperty("version"));
```
