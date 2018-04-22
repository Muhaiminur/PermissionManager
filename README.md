# PermissionManager
Welcome to the PermissionManager wiki!
### Project Gradle
`allprojects {
	repositories {
		...
		maven { url 'https://jitpack.io' }
	}
}`

### App Gradle
`dependencies {
        compile 'com.github.karanchuri:PermissionManager:0.1.0'
}` 
### Main Activity
`PermissionManager permissionManager;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        permissionManager=new PermissionManager() {};
        permissionManager.checkAndRequestPermissions(this);
        //runtime permission check
        if (checkPermission()){
            
        }
    }
    private boolean checkPermission(){
        int result = ContextCompat.checkSelfPermission(getApplicationContext(), Manifest.permission.ACCESS_FINE_LOCATION);
        if (result == PackageManager.PERMISSION_GRANTED){

            return true;

        } else {

            return false;

        }
    }
    @Override
    public void onRequestPermissionsResult(int requestCode,String permissions[], int[] grantResults) {
        permissionManager.checkResult(requestCode,permissions, grantResults);
    }
}
//

<uses-permission android:name="android.permission.INTERNET" />
    <uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />
    <uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION" />
`

### Example
# picture
![](https://github.com/Muhaiminur/PermissionManager/blob/master/Screenshot_20180422-145641.png)

# Video
[Video Link here](https://github.com/Muhaiminur/PermissionManager/blob/master/EXAMPLE.mp4)
# App
[App link here](https://github.com/Muhaiminur/PermissionManager/blob/master/app-debug.apk)
