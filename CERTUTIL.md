### Encoding:
$ certutil -encode file.txt enceded.txt
### Decoding:
$ certutil -decode enceded.txt decoded.txt
### Hashing:
$ certuril -hashfile ".\file.txt" md5
$ certutil -hashfile ". \file.txt" sha1
$ certutil -hashfile ".\file.txt" sha256
### Downloading:
$ certuril -f -urlcache -split http://7-zip.org/a/7z1604-x64.exe