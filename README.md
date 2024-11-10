
# How to make register website using laravel backend and react + vite as frontend with MySql Database (Including how to install the needs)

This readme has been created to help other to create their own register website.

But this only work in windows 10 and 11, but in Linux and MacOs idk if that still same.




## Badges

Add badges from somewhere like: [shields.io](https://shields.io/)

![Laravel](https://img.shields.io/badge/Laravel-FF2D20?logo=laravel&logoColor=white)
![React](https://img.shields.io/badge/React-61DAFB?logo=react&logoColor=black)
![Vite](https://img.shields.io/badge/Vite-646CFF?logo=vite&logoColor=white)

## Installation Steps

First, if you don't have Composer, install it by downloading it from [Composer.exe](https://getcomposer.org/download/).

- Click the link, then on the page, click the blue text to download.

![Composer download](https://github.com/Adornadowilliam2/fullstack-for-dummies/blob/main/assets/composer%20need%20to%20install.png?raw=true)

- Once Composer finishes installing, you’ll need to set up PHP. If you don’t have it, go to [PHP Download](https://windows.php.net/download#php-8.3).

- Click **Zip [30.82MB]** to download PHP.

![PHP download](https://github.com/Adornadowilliam2/fullstack-for-dummies/blob/main/assets/Screenshot%202024-11-09%20154417.png?raw=true)

- Extract the ZIP file.

![Extract PHP](https://github.com/Adornadowilliam2/fullstack-for-dummies/blob/main/assets/Screenshot%202024-11-09%20154659.png?raw=true)

- Next, go to the **php.ini-development** file and rename it to **php.ini**.

- Open the **php.ini** file and it should look like this:

![php.ini file](https://github.com/Adornadowilliam2/fullstack-for-dummies/blob/main/assets/sample.png?raw=true)

- Press **Ctrl + F** on your keyboard to search for specific lines.

![Search function](https://github.com/Adornadowilliam2/fullstack-for-dummies/blob/main/assets/search%20something.png?raw=true)

## Now, search for and uncomment (remove the `;` symbol) the following extensions:

- `;extension=sodium`
- `;extension=zip`
- `;extension=pdo_sqlite`
- `;extension=pdo_odbc`
- `;extension=pdo_mysql`
- `;extension=openssl`
- `;extension=mbstring`
- `;extension=curl`
- `;extension=fileinfo`

## Save the changes and move the folder into **Program Files**.

![Move to Program Files](https://github.com/Adornadowilliam2/fullstack-for-dummies/blob/main/assets/move%20into%20programfiles.png?raw=true)

Next, update your environment variables.

![Add to Path](https://github.com/Adornadowilliam2/fullstack-for-dummies/blob/main/assets/then%20add%20it%20into%20path.png?raw=true)

- Open **Environment Variables** and click the **Edit** button under **Path**.

![Edit Path](https://github.com/Adornadowilliam2/fullstack-for-dummies/blob/main/assets/add%20to%20path.png?raw=true)

- Then click **New** and add this path: `C:\Program Files\php-8.3.13-Win32-vs16-x64`. Press **OK** on both windows to apply the changes.

![Save Path](https://github.com/Adornadowilliam2/fullstack-for-dummies/blob/main/assets/save%20into%20env.png?raw=true)

After that, you can proceed with installing Composer. Just press **Next** until you reach **Finish**.

You can choose either installation option as they are essentially the same.

![Composer installation](https://github.com/Adornadowilliam2/fullstack-for-dummies/blob/main/assets/composer%20install%20next.png?raw=true)

Once installation is complete, open **Command Prompt** and type `composer -v` to verify the installation.

![Composer version](https://github.com/Adornadowilliam2/fullstack-for-dummies/blob/main/assets/look%20like%20this%20finished%20install.png?raw=true)

Now you have Composer and Laravel installed!
## Creating a Backend Laravel Project

First, type the following command in the command prompt:

`composer create-project laravel/laravel --ask`


It will ask you what type of project you want to create. After you finish naming your project, it will install the necessary vendor files to run your Laravel project.

![Creating Laravel project](https://github.com/Adornadowilliam2/fullstack-for-dummies/blob/main/assets/Screenshot%202024-11-09%20163757.png?raw=true)

If everything is set up correctly and you’ve uncommented the necessary extensions, it should look like this:

![Laravel project installation finished](https://github.com/Adornadowilliam2/fullstack-for-dummies/blob/main/assets/Screenshot%202024-11-09%20164136.png?raw=true)

## Now, Open Your IDE or Code Editor (e.g., VSCode)

If you don’t have it installed, you can download it from [VSCode for Windows](https://code.visualstudio.com/download).

![Download VSCode](https://github.com/Adornadowilliam2/fullstack-for-dummies/blob/main/assets/Screenshot%202024-11-09%20164753.png?raw=true)

After that, you need to set up a database. You can use **MySQL**, but if you're unfamiliar with it, I recommend using [XAMPP](https://www.apachefriends.org/download.html) for simplicity.

![Download XAMPP](https://github.com/Adornadowilliam2/fullstack-for-dummies/blob/main/assets/Screenshot%202024-11-09%20165043.png?raw=true)

## Once XAMPP is downloaded and installed, it should look like this. Then, start the **Apache** and **MySQL** services.

![Start Apache and MySQL](https://github.com/Adornadowilliam2/fullstack-for-dummies/blob/main/assets/Screenshot%202024-11-09%20165323.png?raw=true)

Go back to your Laravel project, and it should look like this:

![Laravel Project Directory](https://github.com/Adornadowilliam2/fullstack-for-dummies/blob/main/assets/back%20to%20laravel%20project.png?raw=true)

Now, type `code .` in your terminal to open the project in VSCode (this will include the current directory).

Next, open the `.env` file. It should look like this:

![Open .env File](https://github.com/Adornadowilliam2/fullstack-for-dummies/blob/main/assets/Screenshot%202024-11-09%20165730.png?raw=true)

Make the following changes to the `.env` file:

- Remove the **#** symbol.
- Change `DB_CONNECTION` to `mysql`.
- Change `SESSION_DRIVER` to `file`.

![Updated .env File](https://github.com/Adornadowilliam2/fullstack-for-dummies/blob/main/assets/Screenshot%202024-11-09%20170126.png?raw=true)

Next, go to the **migrations** folder and delete the `jobs` and `cache` migration files.

![Remove Unnecessary Files](https://github.com/Adornadowilliam2/fullstack-for-dummies/blob/main/assets/remove%20the%20user.png?raw=true)

After deletion, the folder should look like this:

![After Removing Files](https://github.com/Adornadowilliam2/fullstack-for-dummies/blob/main/assets/change%20this%20.png?raw=true)

Then, in the **users** migration file, remove unnecessary fields and change `name` to `username`.

![Update User Migration](https://github.com/Adornadowilliam2/fullstack-for-dummies/blob/main/assets/Screenshot%202024-11-09%20171009.png?raw=true)

Back in the terminal, run the following command to install the necessary API dependencies to connect to our frontend:

`php artisan install:api`


When prompted, type **yes**.

![Yes to All](https://github.com/Adornadowilliam2/fullstack-for-dummies/blob/main/assets/Screenshot%202024-11-09%20171521.png?raw=true)

Then, remove `laravel/sanctum`:

`composer remove laravel/sanctum`


We won’t be using Sanctum; instead, we’ll use Passport. You also need to delete the `config/sanctum` directory.

![Delete Sanctum](https://github.com/Adornadowilliam2/fullstack-for-dummies/blob/main/assets/delete%20this.png?raw=true)

Now, install Passport with the following command, which will include all the necessary dependencies:

`composer require laravel/passport -W`


Once Passport is installed, run the following command to create the Passport tables:

`php artisan install:passport`


Next, open the **config/auth.php** file. It should look like this:

![Auth Config](https://github.com/Adornadowilliam2/fullstack-for-dummies/blob/main/assets/Screenshot%202024-11-09%20172400.png?raw=true)

Change it to look like this:

```php
'api' => [
    'driver' => 'passport',
    'provider' => 'users',
],
```

![image look after](https://github.com/Adornadowilliam2/fullstack-for-dummies/blob/main/assets/Screenshot%202024-11-09%20172444.png?raw=true)

Then, in the `User model`, add HasApiTokens:

![image model](https://github.com/Adornadowilliam2/fullstack-for-dummies/blob/main/assets/model%20change%20in%20user.png?raw=true)

Next, update the `User model` like this:
- Change `name` to `username`.
- Add `HasApiTokens` after `HasFactory, Notifiable;`.
- Add this line at the top of the file:
`use Laravel\Passport\HasApiTokens;`

Next, go back to the command prompt and create a new controller:

`php artisan make:controller AuthController`

![image done](https://github.com/Adornadowilliam2/fullstack-for-dummies/blob/main/assets/create%20a%20controller.png?raw=true)

Once the controller is created, it will look like this

![image controller](https://github.com/Adornadowilliam2/fullstack-for-dummies/blob/main/assets/auth%20controller%20look%20like.png?raw=true)

```php
<?php

namespace App\Http\Controllers;

use Illuminate\Http\Request;
use App\Models\User;

class AuthController extends Controller
{
    public function register(Request $request)
    {
        $validator = validator($request->all(), [
            "username" => "required|unique:users|max:255",
            "email" => "required|unique:users,email",
            "password" => "required|confirmed"
        ]);

        if ($validator->fails()) {
            return response()->json([
                "ok" => false,
                "message" => "Request didn't pass validation",
                "data" => $validator->errors()
            ]);
        }

        $user = User::create($validator->validated());
        $user->token = $user->createToken("auth-api")->accessToken;
        
        return response()->json([
            "ok" => true,
            "message" => "Register Successfully",
            "data" => $user
        ]);
    }
}
```

Now, go to the ***routes/api.php*** file. It should look like this:

![api image look](https://github.com/Adornadowilliam2/fullstack-for-dummies/blob/main/assets/Screenshot%202024-11-09%20174400.png?raw=true)

Change it to this:
```php

<?php

use Illuminate\Http\Request;
use Illuminate\Support\Facades\Route;

Route::post('/register', [App\Http\Controllers\AuthController::class, 'register']);

```

Additionally, make sure to update the database seeder so that it works even if there are any issues with the database.


![seeder look image](https://github.com/Adornadowilliam2/fullstack-for-dummies/blob/main/assets/artisan.png?raw=true)

After making all these changes, the project should look like this:

![seeder after](https://github.com/Adornadowilliam2/fullstack-for-dummies/blob/main/assets/Screenshot%202024-11-09%20175744.png?raw=true)

Also, add the following line above the `DatabaseSeeder` class:
`use Artisan;`


Now you finish doing the backend, Now for the front-end.
