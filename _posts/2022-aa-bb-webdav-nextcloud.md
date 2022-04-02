---
title: Use WebDAV with nextcloud
published: true
---
Hello once again. So today, I'm just going to do a quick tutorial on how to use WebDAV with Nextcloud,
even though it would probably work with all WebDAV instances. While their [docs](https://docs.nextcloud.com/server/latest/developer_manual/client_apis/WebDAV/) are pretty good (crazy for an API, right?), I just wanted to have some quick one liners to use with cURL.
### Downloading files
This is theoretically an easy one, but how to actually download  the file, took me a second to figure out. Since, without the "--output" flag, you just simply read the contents of the file.
The "-X GET" isn't necessary, since cURL sends GET requests by default, but I'd still use it, just for overall compatibility. <br>
```curl -X GET -u user:password  https://url-here.wtf/remote.php/dav/files/user/optional/path/filename.file --output filename.file```
### Basic uploading and removing of files and folders
So this obviously needs account verification, I made a second account for it, but you can also just use your normal user. <br>
- Uploading files<br>
```curl -X PUT -u user:password -T filename.file https://url-here.wtf/remote.php/dav/files/user/optional/path```
- Creating folders <br>
```curl -X MKCOL -u user:password https://url-here.wtf/remote.php/dav/files/user/optional/path```
- Removing files/folders <br>
```curl -X DELETE -u user:password https://url-here.wtf/remote.php/dav/files/user/optional/path```
### Moving and copying files or folders
So yeah, I'm not sure why, but it straight up doesn't work. I don't know if it worked before, and they broke it with the new update, like with the cron jobs, or my web server is configured wrong. You may refer to the documentation for [moving](https://docs.nextcloud.com/server/latest/developer_manual/client_apis/WebDAV/basic.html#moving-files-and-folders-rfc4918) or [copying](https://docs.nextcloud.com/server/latest/developer_manual/client_apis/WebDAV/basic.html#moving-files-and-folders-rfc4918). I might try it again as soon as there's a new version/docker image, and update the blog if needed. 


I hope I could still help you, and have a great rest of your day!

_If this article helped you, consider [donating](https://blog.shruubo.ml/about)._

###### Sources:
<font size="1">
https://docs.nextcloud.com/server/latest/developer_manual/client_apis/WebDAV/basic.html#copying-files-and-folders-rfc4918 - overall documentation
</font>