
# Easiest way of Networking in Android Studio

Learnoset Networking is a powerful library for any type networking in Android Application.
<br><br>
You can make a internet request in just few lines of code. This library is a modified version of Volley library
<br><br>

<h3>Why use Learnoset Networking Library</h3>
<ul>
<li>
  Fast, Secure and Easy to use. 
 </li>
  <li>
  Support both GET & POST methods
 </li>  
  <li>
  Easy to implement
 </li>
  <li>
  In-Built Progress Bars
 </li>
  <li>
  Easy way tp handle Networking errors.
 </li>
  <li>
  Download Images from Url
 </li>
</ul>
<br><br>
<h3>How to use Learnoset Networking Library</h3>
1. Add below line in your module level build.gradle file

```groovy
implementation 'com.github.learnoset:networking:5.21.1'
```

<br>

2. Add below line in your project level build.gradle file

```groovy
maven {url 'https://jitpack.io' }
```

<br>


3. Add Internet permissions in the Manifest file

```xml
<uses-permission android:name="android.permission.INTERNET" />
```

<br>

4. Initialize

```java
LearnosetNetRequest.init("url_here", this);
```

<br>

5. Make POST Request

```java
// creating object
LearnosetNetRequest request = new LearnosetNetRequest(this, RequestMethod.POST);

// adding post parameters
request.addParam("param_1_key", "param_1_value");
request.addParam("param_2_key", "param_2_value");
request.addParam("param_3_key", "param_3_value");
request.addParam("param_4_key", "param_4_value");
request.addParam("param_5_key", "param_5_value");

// execute request
request.execute(true, 10, new NetResponseListener() {
    @Override
    public void onRequestSuccess(String response, Context context, int resultCode) {

        // handle response here
    }

    @Override
    public void onRequestFailed(String errorMessage, Context context, int resultCode) {

        // handle errors here
    }
});
```

<br>

6. Make GET Request

```java
// creating object
LearnosetNetRequest request = new LearnosetNetRequest(this, RequestMethod.GET);

// adding post parameters
request.addParam("param_1_key", "param_1_value");
request.addParam("param_2_key", "param_2_value");

// execute request
request.execute(true, 11, new NetResponseListener() {
    @Override
    public void onRequestSuccess(String response, Context context, int resultCode) {

        // handle response here
    }

    @Override
    public void onRequestFailed(String errorMessage, Context context, int resultCode) {

        // handle errors here
    }
});
```

<h5>execute() method parameters</h5>
1. showDialog = true if you want to show process dialog, false otherwise<br>
2. resultCode = If you want to use single NetResponseListener for more than 1 requests then in onRequestSuccess method resultCode will help you to identifies of which request you have recieved response<br>
3. NetResponseListener instance to get response and errors after request success

<br>

<h3>Use your Custom Dialog as Progress Dialog</h3>

```java
request.setCustomDialog(YourCustomDialogObject);
```

<br>

You can Visit our Website to learn more about Android App Development<br>
[Learnoset Website](https://learnoset.com/)

<br>
We provide source code for Login & Register pages, Custom Dialogs, Custom Navigation Bar, Custom Toolbar, Custom Bottom Bar with material UI design and complete project files
