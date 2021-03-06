## PyWeather Configuration Readme
Since configparser hates comments, this will do for now.

## SUMMARY section
### sundata_summary
This option will let you turn on/off PyWeather showing sunrise/sunset data on startup.

If this option is enabled, PyWeather may take a bit longer to start up, and will use 1 more API call at start.

**Default option: False**

###almanac_summary
This option will let you turn on/off PyWeather showing almanac data on startup.

If this option is enabled, PyWeather may take a bit longer to start up, and will use 1 more API call at start.

**Default option: False**

## VERBOSITY section
PyWeather can give you extra information across all scripts, to help debug problems.

### verbosity
This option will let you turn on/off PyWeather showing logging information.

Useful for troubleshooting, and seeing if something is abnormal.

**Default option: False**

### json_verbosity
This option will let you turn on/off PyWeather printing out full .json files that it fetches.

Useful for troubleshooting, but it'll spam your console. Use wisely.

**Default option: False**

### setup_verbosity
This option will let you turn on/off PyWeather Setup showing logging information.

Useful for troubleshooting, and seeing if something is abnormal.

**Default option: False**

### setup_jsonverbosity
This option will let you turn on/off PyWeather Setup printing out .json files that it fetches.

Useful for troubleshooting, but it'll spam your console. Use wisely.

**Default option: False**

### updater_verbosity
This option will let you turn on/off PyWeather Updater showing logging information.

Useful for troubleshooting, and seeing if something is abnormal.

**Default option: False**

### updater_jsonverbosity
This option will let you turn on/off PyWeather Updater printing out .json files that it fetches.

Useful for troubleshooting, and it doesn't spam your console as much.

**Default option: False**

### keybackup_verbosity
This option will let you turn on/off PyWeather API Key Backup showing logging information.

Useful for troubleshooting, and seeing if something is abnormal.

**Default option: False**

## TRACEBACK section
PyWeather can optionally show you a full traceback when an error occurs in a safety net. Turning this on is especially useful when you need to report an error.

### tracebacks
This option allows you to turn on printing full tracebacks in PyWeather.

Useful for reporting issues, and seeing what went wrong.

**Default option: False**

### setup_tracebacks
**This option is useless, but will be implemented in 0.5.1 beta.**

This option allows you to turn on printing full tracebacks in PyWeather Setup.

Useful for reporting issues, and seeing what went wrong.

**Default option: False**

### updater_tracebacks
**This option is useless, but will be implemented in 0.5.1 beta.**

This option allows you to turn on printing full tracebacks in PyWeather Updater.

Useful for reporting issues, and seeing what went wrong.

**Default option: False**

### keybackup_tracebacks
**This option is useless, but will be implemented in 0.5.2 beta.**

This option allows you to turn on printing full tracebacks in PyWeather API Key Backup.

Useful for reporting issues, and seeing what went wrong.

**Default option: False**

## UI section
This section controls parts of the UI in PyWeather.

### show_enterToContinue
This option allows you to show the "Enter to Continue" prompt when viewing detailed weather information.

This should probably be left on, unless you feel like scrolling through 240 iterations of 10 day hourly weather.

**Default option: True**

### detailedInfoLoops
This option allows you to control how many loops, or iterations PyWeather will go through before stopping for an "Enter to Continue" prompt, when viewing detailed hourly, 10 day hourly, and historical hourly information.

Increasing this option above 10 isn't recommended, as it gets pretty annoying to scroll up through a lot of iterations to get the information you need.

**Default option: 6**

### forecast_detailedInfoLoops
This option allows you to control how many loops, or iterations PyWeather will go through before stopping for an "Enter to Continue" prompt, when viewing detailed forecast information.

If you increase this option above 9, you basically get rid of the prompt.

**Default option: 5**

### show_completedIterations
This option allows you to see how many iterations you've gone through, when viewing detailed hourly, 10 day hourly, historical hourly, or the 10 day forecast.

It blends in with the rest of the data, so it can be a little hard to notice.

**Default option: False**

## HOURLY section

### 10dayfetch_atboot
This option controls if PyWeather should fetch the 10 day hourly forecast JSON at boot. Here's how it works.

By default, PyWeather fetches a 3 day hourly JSON at boot. When you go into the 10 day hourly menu, it'll fetch the 10 day hourly JSON. This method is less call-efficient, but doing this makes PyWeather load faster.

When enabled, PyWeather will only fetch the 10 day hourly JSON at boot. A downside to this is that loading will take longer, as it has more to download. However, you won't need to wait for PyWeather to fetch the 10 day JSON when you want to view 10 day hourly, and saves on calls.

This isn't a default in the code due to the pros/cons of using each method.

(and implementing this was a complete pain in the NECK.)

**Default option: False**

## UPDATER section
This section controls PyWeather's updating mechanism.

### autocheckforupdates
This option allows for PyWeather to automatically check for updates on boot.

It's very minimal, and all it'll say if PyWeather is out of date is something like "PyWeather is not up to date. You have version x, and the latest version is y".

If PyWeather is up to date, nothing will be outputted.

It's useful, but enabling this makes it so PyWeather starts a little slower at boot.

**Default option: False**

### show_updaterReleaseTag
This option allows you to show the release tag (branch) for the latest version of PyWeather.

This is especially useful for those using Git, who want to pull from the source, and check out to the latest stable version.

It's off by default as it's presumed you're not using Git to download and update PyWeather.

**Default option: False**

## KEYBACKUP section
This section allows you to control parts of the Key Backup script.

### savelocation
This option allows you to control where your backup API key is stored. It's a global setting, meaning (in future versions) that PyWeather will load your backup key (if your primary one is dead) from this location.

You can save it anywhere in PyWeather's folder. However, you'll want to take note of three things.

1. If you want to save your key to a folder that doesn't exist, make the folder first. If you don't do this, you might run into issues.

2. When you want your backup key in a folder, instead of doing "/" or "\" for the folder (e.g. test/test.txt, or test\test.txt), you'll want to use "//" instead. (e.g. test//test.txt)

3. The file extension has to end in .txt. I don't know what happens if you decide to use .md, or some other foreign file format.

**Default option: backup//backkey.txt**