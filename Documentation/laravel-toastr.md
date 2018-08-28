# Laravel Toastr

### Implementing Toastr messages in laravel.

##### Step 1 : Add toastr dependancy
```
  composer require brian2694/laravel-toastr
```

##### Step 2 : Add service provider in config/app.php
```PHP
  Brian2694\Toastr\ToastrServiceProvider::class,
```

##### Step 3 : Add facade in config/app.php
```PHP
  'Toastr'  => Brian2694\Toastr\Facades\Toastr::class,
```

##### Step 4 : Run this command to get configuration of toastr under config folder
```
php artisan vendor:publish
```

##### Step 5 : Add toastr js and css cdn into blade file
```HTML
<link rel="stylesheet" href="http://cdn.bootcss.com/toastr.js/latest/css/toastr.min.css">
<script src="http://cdn.bootcss.com/jquery/2.2.4/jquery.min.js"></script>
<script src="http://cdn.bootcss.com/toastr.js/latest/js/toastr.min.js"></script>
```

##### Step 5 : Do not forget to add this line into blade file below toastr js script tag
```PHP
{!! Toastr::message() !!}
```

### Usage

```PHP
Toastr::info('message', 'title', ['options']);
Toastr::success('message', 'title', ['options']);
Toastr::warning('message', 'title', ['options']);
Toastr::error('message', 'title', ['options']);
Toastr::clear();
Toastr()->info('message', 'title', ['options']);
```

### Example
```PHP
Toastr::success('Messages in here', 'Title', ["positionClass" => "toast-top-center"]);
```
