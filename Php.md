# PHP

## Laravel

- Commands to run after transfer project to another system

  > 1. composer install
  > 2. php artisan key:generate
  > 3. php artisan cache:clear
  > 4. php artisan migrate

```PHP
// Upload Image
 if ($request->hasFile('image')) {
    $image = $request->file('image');
    $imageName = time() . '.' . $image->getClientOriginalExtension();
    $image->move(public_path('images/user'), $imageName);
}

// Hash Password
$user->password = Hash::make($request->password);

// JSON Response
 return response()->json(['status' => false, 'message' => 'Password is required.'], 203);


// Check for Email Exists
if (!Admin::where('email', $request->only('email'))->exists()) {
    return redirect()->route('register')->with('status', 'Email Not Found Please Register!');
}

// Email Password Login with remember token
if (!auth()->attempt($request->only('email', 'password'), $request->remember)) {
    return back()->with('status', 'Invalid Login Details');
}

// Validator for Web
$this->validate($request, [
    'name' => 'required|string|max:255',
    'email' => 'required|string|email|max:255|unique:admins,email',
    'password' => 'required|string|min:6|confirmed',
]);


// Validator for API
$validator = Validator::make($request->all(), [
    'name' => 'required|string|max:255',
    'email' => 'required|string|email|max:255|unique:admins,email',
    'password' => 'required|string|min:6|confirmed',
]);

if ($validator->fails()) {
    return response()->json(['status' => false, 'message' => $validator->errors()->first()], 203);
}


// Artisan Commands
// Clear and Key Generate
Route::get('/clear', function () {
        $exitCode = Artisan::call('cache:clear');
    $exitCode = Artisan::call('route:cache');
    $exitCode = Artisan::call('route:clear');
    $exitCode = Artisan::call('view:cache');
    $exitCode = Artisan::call('view:clear');
    $exitCode = Artisan::call('config:cache');
    $exitCode = Artisan::call('config:clear');
    $exitCode = Artisan::call('event:cache');
    $exitCode = Artisan::call('event:clear');
    $exitCode = Artisan::call('optimize');
    return '<h1>Cache facade value cleared</h1>';
});
```

- Create a new

> composer create-project laravel/laravel my-project-name

- Get laravel Installer

> composer global require laravel/installer>

- Laravel Debug Bar

> composer require barryvdh/laravel-debugbar --dev

## XAMPP Configuration

### Services

- Run Apache and MySQL as Services so you don't have to start them manually
- You can do this by running the opening xampp as an administrator and then click the checkboxes in front of Apache and MySQL

### Start Xampp as Administrator

- Go to Xampp location Probably `C:\ProgramData\Microsoft\Windows\Start Menu\Programs\XAMPP`
- Open Properties of `XAMPP Control Panel`
- Click on Advanced Option and then check `Run as administrator`
- After that Go to `Compatibility Tab` and check `Run this program as an administrator`
- At last click apply and ok buttons and your are Good To Go

### Make phpMyAdmin available to local network

1. Close XAMPP all services
2. Got to httpd-xampp.conf file and change from `Require local` to `Require all granted`
3. Start back all the services

### Change the Default localhost location of Xampp i.e. htdocs => your Project folder

- Close XAMPP all services
- Go the httpd.conf file and change the `DocumentRoot` to your project folder as

```Bash
# DocumentRoot "C:/xampp/htdocs"
# <Directory "C:/xampp/htdocs">
DocumentRoot "D:/Projects"
<Directory "D:/Projects">
```

### Change the default Text Editor to Visual Studio Code in XAMPP

- Click on `Config` button of XAMPP Control Panel
- then change the editor location to `C:\Users\kingt\AppData\Local\Programs\Microsoft VS Code\Code.exe`

## Clear Laravel Cache

```Bash
php artisan cache:clear
php artisan route:clear
php artisan config:clear
php artisan view:clear
```
