# Terminal

## Count files in the folder:
```bash
ls | wc -l
```

## "You don't have write permissions for the /Library/Ruby/Gems/2.6.0 directory." Fix:
```bash
sudo gem install bundler
```


## Copy file via scp

```bash
scp archive.zip root@HOST_IP:~/Downloads
```

## Check who is using specified port
```bash
lsof -nP -iTCP:$PORT | grep LISTEN
```
