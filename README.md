# Laravel 11 Passport REST API Authentication Tutorial

  Build an Laravel 11 REST API Authentication using Passport Step by Step example. you have to simply follow the below steps:
  - Step 1: Install Laravel 11 
        composer create-project laravel/laravel example-app

  - Step 2: Run Migration i.e. php artisan migarte (Only migrate users,cache,jobs and products table from project, becuase after passport installation other tables will migrate by self)

  - Step 3: Install Passport API i.e. php artisan install:api --passport
        In this step, we have to configure three places: the model, the service provider, and the auth config file. So, you just need to follow the changes in those files.

        In the model, we added the HasApiTokens class of Passport.
        - app/Models/User.php  - go in this file and check line:
            use Laravel\Passport\HasApiTokens;
            use HasFactory, Notifiable, HasApiTokens; inside the class

        In the auth.php file, we added API auth configuration.
            'guards' => [
                'web' => [
                    'driver' => 'session',
                    'provider' => 'users',
                ],

                'api' => [
                    'driver' => 'passport',
                    'provider' => 'users',
                ],
            ],

  - Step 4: Add Product Table and Model
  - Step 5: Create API Routes (E.g routes\api.php)
  - Step 6: Create Controller Files (E.g app\Http\Controllers)
  - Step 7: Create Eloquent API Resources (E.g app\Http\Resources)
  - Run Laravel 11 App

  make sure in details api we will use following headers as listed bellow:
  'headers' => [
    'Accept' => 'application/json',
    'Authorization' => 'Bearer '.$accessToken,
]