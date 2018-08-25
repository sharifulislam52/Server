# Server
Server is a light and fast HTTP library that makes networking for Android apps very simple. It is specially designed for transfer **String and JSON data** between android app and live server. Another major advantage of this is that it is very friendly with PHP.

Server offers the following benefits :
------
* It's light and fast.
* Easy to learn and use.
* Transfer String and JSON data.
* Receiving data as String or JSONObject.
* Very friendly with PHP.
* There is no exception.

build.gradle (Project)
------
```
allprojects {
	repositories {
		...
		maven { url 'https://jitpack.io' }
	}
}
```

build.gradle (Module: app)
------
```
dependencies {
	implementation 'com.github.sharifulislam52:Server:1.0.0'
}
```

Usage
-----
**Import**
```java
import shariful.server.Server;
```

**MainActivity.java**
```java
public class MainActivity extends AppCompatActivity {
	...

	JSONObject object = new JSONObject();
	...

	conn_server conn = new conn_server();
	conn.execute("request_name", "http_Link.php", object.toString());
	
	private class conn_server extends Server{
		@Override
		public void HttpResult(String name, String data){}

		@Override
		public void HttpResult(String name, JSONObject object){}

		@Override
		public void HttpRequestFailed(String name){}
	}
}
```

Changelog
---------
* **1.0.0**
    * Initial release


License
-------
```
	MIT License

	Copyright (c) 2018 shariful islam

	Permission is hereby granted, free of charge, to any person obtaining a copy
	of this software and associated documentation files (the "Software"), to deal
	in the Software without restriction, including without limitation the rights
	to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
	copies of the Software, and to permit persons to whom the Software is
	furnished to do so, subject to the following conditions:

	The above copyright notice and this permission notice shall be included in all
	copies or substantial portions of the Software.

	THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
	IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
	FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
	AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
	LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
	OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
	SOFTWARE.
```