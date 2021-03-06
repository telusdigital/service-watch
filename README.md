# Service Watch
A simple script to read if a service is up or down and notify you when the service is up

[![Licence](https://img.shields.io/badge/Licence-ISC-blue.svg)](https://opensource.org/licenses/ISC) [![Code Climate](https://codeclimate.com/github/telusdigital/service-watch/badges/gpa.svg)](https://codeclimate.com/github/telusdigital/service-watch) [![Issue Count](https://codeclimate.com/github/telusdigital/service-watch/badges/issue_count.svg)](https://codeclimate.com/github/telusdigital/service-watch)

## clone the repo
```
git clone https://github.com/telusdigital/service-watch.git
cd service-watch
```

## install node dependancies
```
node install # yes node NOT npm
```

## set up your config file to send emails and / or slack in alerts/
```
module.exports.EMAIL_USER     = 'youremail';
module.exports.EMAIL_PASSWORD = 'yourpassword';

module.exports.EMAIL_PASSWORD = 'TOKEN/TOKEN/TOKEN';
```

## copy or symlink parsers from parsers-avilable to parsers-enabled
```
cd parsers-enabled
ln -s ../parsers-available/github.js ./
cd ..
```

## run the program selecting which alert to use and where to alert too
```
node service-watch {{ alert_type }} [{{ alert_list }}]
```
### example
```
node service-watch email first@email.com second@email.com third@email.com
node service-watch slack "#channel1" @person1 "#channel2" @person2
```
