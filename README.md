## How to use it

Add my PGP key to the pacman keyring

```
sudo pacman-key --recv-keys 95453E765FE509F4
```

Check fingerprint

```
pacman-key --finger 95453E765FE509F4
```

It should be something like this

```
pub   rsa4096 2018-01-23 [SC]
      D220 00D5 4BD3 92A4 FE92  E183 9545 3E76 5FE5 09F4
uid           [  full  ] Vlad Zagorodniy <vladzzag@gmail.com>
sub   rsa4096 2018-01-23 [E]
sub   rsa4096 2018-01-23 [S] [expires: 2019-01-23]
```

Finally, locally sign the imported key

```
sudo pacman-key --lsign-key 95453E765FE509F4
```

Add the `zzag` repo to the `pacman.conf`

```
[zzag]
Server = https://zzag.github.io/PKGBUILD/
```

Update package/files database

```
sudo pacman -Sy
sudo pacman -Fy
```
