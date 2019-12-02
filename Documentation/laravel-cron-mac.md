# Setting laravel cron task on mac

### Step 1: Enter this command in terminal

```
env EDITOR=nano crontab -e
```

### Step 2: Add this command and save

```
* * * * * cd /path-to-your-project && php artisan schedule:run >> /dev/null 2>&1
```

### Step 3: Add scheduler in laravel project

```PHP
$schedule->call(function() {
  \Log::info('Cron works');
})->everyMinute();
```

### Step 4: Check laravel log file in every minute
