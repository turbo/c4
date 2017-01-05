# c4

c4 is a plain-text list of stream URLs of about 30k open IP cameras in IPv4, which is a representative amount.

### Querying the list

###### Download

```sh
wget git.io/c4
```

###### View a random camera

`open` should be configured to open URLs with your browser.

Unix:

```sh
open $(curl -Ls git.io/c4 | shuf | head -n1)
```

macOS:

```sh
open $(curl -Ls git.io/c4 | gshuf | head -n1)
```

###### Open the admin panel

This will open the admin panel of cameras which are probably enabled to be controlled remotely (i.e. you can move them around). You might be asked for a pasword, just enter admin and leave password empty. Sometimes you are logged in automatically. Either way, after logging in, select the "Server Push Mode", sometimes also called "Firefox", "Chrome" or "videostream" mode.

Unix:

```sh
open http://admin:@$(curl -Ls git.io/c4 | grep videostream | shuf | head -n1 | cut -d "/" -f3)
```

macOS:

```sh
open http://admin:@$(curl -Ls git.io/c4 | grep videostream | gshuf | head -n1 | cut -d "/" -f3)
```
