
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


Once Passport is installed and **config/auth** been changed,you can now run the following command to create the Passport tables:

`php artisan passport:install`

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

## Issue Possible happen

- if you add this to your version control like github and gitlab then you clone it you need first to create a **.env** then type this command

`php artisan key:generate`

for adding like this 

![image of adding key:generate](https://github.com/Adornadowilliam2/fullstack-for-dummies/blob/main/assets/Screenshot%202024-11-10%20104658.png?raw=true)

- if you have to delete the database for new changes just simply type 

`php artisan migrate:fresh --seed`

this will do to refresh whole thing inside the migration and Database seeder.


- also if you don't know how to run this to see it work just type

`php artisan serve`
## Creating a frontend react + vite

For this we need to install first the node, if you dont have just click here [node link](https://nodejs.org/dist/v22.11.0/node-v22.11.0-x64.msi)

then once the link has been download you now install it. after it finished you can check to your command prompt if it now install using this command


![image of command prompt to see the node install](https://github.com/Adornadowilliam2/fullstack-for-dummies/blob/main/assets/Screenshot%202024-11-10%20110357.png?raw=true)

This mean it also install the npm and npx


now for creating a react+vite project just simply type 

`npm create vite@latest`

and this will show some prompt like this 

![name of react project](https://github.com/Adornadowilliam2/fullstack-for-dummies/blob/main/assets/react%20+%20vite%20install.png?raw=true)


now choose the React and Javascript

![react option](https://github.com/Adornadowilliam2/fullstack-for-dummies/blob/main/assets/Screenshot%202024-11-10%20111034.png?raw=true)

![javascript option](https://github.com/Adornadowilliam2/fullstack-for-dummies/blob/main/assets/Screenshot%202024-11-10%20111111.png?raw=true)


then after that go to the instruction it given to like 

```php
cd "name of you folder"
npm install
npm run dev
```

![image look](https://github.com/Adornadowilliam2/fullstack-for-dummies/blob/main/assets/THEN%20once%20you%20follow%20it%20will%20look%20like%20this.png?raw=true)

then go to the url it will look like this 

![localhost:5173](https://github.com/Adornadowilliam2/fullstack-for-dummies/blob/main/assets/Screenshot%202024-11-10%20111609.png?raw=true)

then to edit this you need to go in your IDE or VScode to edit it just go to src and you will see App.jsx

![vscode look like](https://github.com/Adornadowilliam2/fullstack-for-dummies/blob/main/assets/ide%20look%20like%20in%20react+%20vite%20as%20default.png?raw=true)


also you can remove the index.css as there is App.css input in the src to avoid confusion for designing

![remove the index.css](https://github.com/Adornadowilliam2/fullstack-for-dummies/blob/main/assets/remove%20the%20css%20connect%20to%20the%20main.jsx.png?raw=true)

![remove the index.css in the main.jsx](https://github.com/Adornadowilliam2/fullstack-for-dummies/blob/main/assets/remove%20the%20index.css.png?raw=true)

also remove the content in App.css. and make it look like this

![app.css removed content](https://github.com/Adornadowilliam2/fullstack-for-dummies/blob/main/assets/Screenshot%202024-11-10%20112242.png?raw=true)

now you need to create pages folder to store the pages need like Home, Register, Login and etc.

![images look like in react](https://github.com/Adornadowilliam2/fullstack-for-dummies/blob/main/assets/create%20a%20pages%20folder.png?raw=true)


then install react es7 formatting auto the function 

![image function extension](https://github.com/Adornadowilliam2/fullstack-for-dummies/blob/main/assets/install%20react%20E56.png?raw=true)

![extension installed](https://github.com/Adornadowilliam2/fullstack-for-dummies/blob/main/assets/vscode%20install%20need%20install.png?raw=true)

then once it install create a register.jsx

![creating a Register.jsx](https://github.com/Adornadowilliam2/fullstack-for-dummies/blob/main/assets/register.jsx%20website.png?raw=true)

then type 

`rfc`

it will look like this

![image rfc look like](https://github.com/Adornadowilliam2/fullstack-for-dummies/blob/main/assets/then%20type%20rfc.png?raw=true)

then it will look like this if you press enter

![image register default](https://github.com/Adornadowilliam2/fullstack-for-dummies/blob/main/assets/it%20will%20look%20like%20this.png?raw=true)]

then after that you can change it by putting this code 

```php
import { useState } from "react";

function Register() {
  const [formData, setFormData] = useState({
    username: "",
    email: "",
    password: "",
    passwordConfirmation: "",
  });

  const [errors, setErrors] = useState({});

  // Handle input changes
  const handleChange = (e) => {
    const { name, value } = e.target;
    setFormData({
      ...formData,
      [name]: value,
    });
  };

  // Validate form fields
  const validateForm = () => {
    const newErrors = {};
    if (!formData.username) newErrors.username = "Username is required";
    if (!formData.email) {
      newErrors.email = "Email is required";
    } else if (!/\S+@\S+\.\S+/.test(formData.email)) {
      newErrors.email = "Email is not valid";
    }
    if (!formData.password) newErrors.password = "Password is required";
    if (formData.password !== formData.passwordConfirmation) {
      newErrors.passwordConfirmation = "Passwords do not match";
    }
    return newErrors;
  };

  // Handle form submission
  const handleSubmit = (e) => {
    e.preventDefault();
    const validationErrors = validateForm();
    setErrors(validationErrors);
    if (Object.keys(validationErrors).length === 0) {
      alert("Form submitted successfully");
      // Handle actual form submission, e.g., send to server
    }
  };

  return (
    <div className="app-container">
      <h1>Register</h1>
      <form onSubmit={handleSubmit} className="form">
        <div className="form-group">
          <label htmlFor="username">Username</label>
          <input
            type="text"
            id="username"
            name="username"
            value={formData.username}
            onChange={handleChange}
            className="input"
          />
          {errors.username && <span className="error">{errors.username}</span>}
        </div>

        <div className="form-group">
          <label htmlFor="email">Email</label>
          <input
            type="email"
            id="email"
            name="email"
            value={formData.email}
            onChange={handleChange}
            className="input"
          />
          {errors.email && <span className="error">{errors.email}</span>}
        </div>

        <div className="form-group">
          <label htmlFor="password">Password</label>
          <input
            type="password"
            id="password"
            name="password"
            value={formData.password}
            onChange={handleChange}
            className="input"
          />
          {errors.password && <span className="error">{errors.password}</span>}
        </div>

        <div className="form-group">
          <label htmlFor="passwordConfirmation">Confirm Password</label>
          <input
            type="password"
            id="passwordConfirmation"
            name="passwordConfirmation"
            value={formData.passwordConfirmation}
            onChange={handleChange}
            className="input"
          />
          {errors.passwordConfirmation && (
            <span className="error">{errors.passwordConfirmation}</span>
          )}
        </div>

        <button type="submit" className="submit-btn">
          Register
        </button>
      </form>
    </div>
  );
}

export default Register;
```
this code i only got from chat gpt to create a fast register design and for App.css

```php
/* General styles */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: Arial, sans-serif;
  background-color: #f0f0f0;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

.app-container {
  background-color: white;
  border-radius: 8px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
  padding: 2rem;
  width: 100%;
  max-width: 400px;
}

h1 {
  text-align: center;
  margin-bottom: 2rem;
  font-size: 24px;
}

.form {
  display: flex;
  flex-direction: column;
}

.form-group {
  margin-bottom: 1rem;
}

label {
  font-size: 14px;
  font-weight: bold;
  margin-bottom: 0.5rem;
  display: block;
}

.input {
  padding: 0.8rem;
  font-size: 16px;
  border: 1px solid #ddd;
  border-radius: 5px;
  width: 100%;
}

.input:focus {
  border-color: #4caf50;
  outline: none;
}

.error {
  color: red;
  font-size: 12px;
  margin-top: 0.25rem;
}

.submit-btn {
  background-color: #4caf50;
  color: white;
  padding: 1rem;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  font-size: 16px;
}

.submit-btn:hover {
  background-color: #45a049;
}

```

once you finish it will look like this
![image register](https://github.com/Adornadowilliam2/fullstack-for-dummies/blob/main/assets/and%20once%20you%20finish%20paste%20it%20will%20look%20like%20this.png?raw=true)


you can also change the title just go to the index.html and edit it

![changing the title](https://github.com/Adornadowilliam2/fullstack-for-dummies/blob/main/assets/you%20can%20also%20change%20the%20title%20in%20index.html%20in%20title%20like%20register.png?raw=true)

 and now we need to create a folder for the api to connect it to our front-end

 ![image of configuration.js](https://github.com/Adornadowilliam2/fullstack-for-dummies/blob/main/assets/create%20a%20configuration.js%20file%20and%20type%20this.png?raw=true)


 if you remember this url same with the url when it run in our laravel after it php artisan serve
 this will show.

 then now we will create an auth.js to put the method connection to our register

then type this you will see the url form configuration earlier you input

![image look in configuration](https://github.com/Adornadowilliam2/fullstack-for-dummies/blob/main/assets/just%20pressed%20enter%20to%20import%20the%20configuration.js%20from%20the%20other%20file.png?raw=true)

then it will look like this 

![add this to your site](https://github.com/Adornadowilliam2/fullstack-for-dummies/blob/main/assets/it%20will%20look%20like%20this%20if%20you%20perfect%20import%20the%20url%20from%20teh%20configuration%20.png?raw=true)

or you can just copy this command if you're a lazy once
```php
import { url } from "./configuration";

export const register = async (body) => {
  const response = await fetch(`${url}/register`, {
    method: "POST",
    headers: {
      Accept: "application/json",
      "Content-Type": "application/json",
    },
    body: JSON.stringify(body),
  });
  return await response.json();
};
```
then last is to add this to your  register site make it look like this 
![image of register from auth](https://github.com/Adornadowilliam2/fullstack-for-dummies/blob/main/assets/you%20need%20to%20add%20this%20to%20your%20site%20to%20add%20all.png?raw=true)

now you have a register website but if you want to make more beautiful we can install something


- `npm i react-toastify` (for alternative for alert message)
- `npm i react-router-dom` (for redirection help)
