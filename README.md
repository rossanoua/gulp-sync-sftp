# [gulp](http://gulpjs.com)-sync-sftp

> Upload files via SSH


Actually it's just merge of next two repos:  
- [gulp-sftp](https://github.com/krysalead/gulp-sftp.git)  
- [gulp-sftp-clean](https://github.com/webksde/gulp-sftp.git)  


Merge was created for the next reason:
- There was error `TypeError: file.pipe is not a function` for plugin [gulp-sftp-clean](https://github.com/webksde/gulp-sftp.git)  
- error which was in the [gulp-sftp-clean](https://github.com/webksde/gulp-sftp.git) have been solved in the [gulp-sftp](https://github.com/krysalead/gulp-sftp.git)  
so, I'm just merged them.  

###How to use:  
Add new line into your `package.json` like follows:  

```json
{
  ...
  "devDependencies": {
    ...
    "gulp-sync-sftp": "git+https://git@github.com/rossanoua/gulp-sync-sftp.git",
    ...
  },
  ...
}

```  

Run `npm install`.  

Configure it as before, and define new option `clearDestination: true` for delete sync folder before upload:
```javascript
function sftpUpload() {
    return src('src/**/*')
        .pipe(sftp({
            host: 'your.host',
            auth: 'keyMain', // credentials going from .ftppass file
            remotePlatform: 'windows', // in my case
            clearDestination: true,
            remotePath: '\\you\\remote\\path' // for 'unix' like remote server => /you/remote/path 
        }));
}
```  

Any questions: just write me an email.  
Enjoy.
