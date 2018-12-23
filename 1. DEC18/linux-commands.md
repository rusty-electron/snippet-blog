* redo last command as super user

```bash
nano /etc/hosts
# make change in file and save
# Access Denied!

sudo !!
# run the last command as super user
```

* cd inside the last created dir
```bash
mkdir -p folder1/folder2/folder3/folder4

cd !$
# you get inside the folder4
```
* run several commands by typing in editor
```bash
# press ctrl+x+e, editor opens, write commands

ls -al
cat /etc/hosts
# save and exit, the commands are executed
```

* create a super fast ram-disk

You can use your `RAM` as a temporary disk drive that will be capable of delivering `read/write` speeds much higher than your ordinary disk drives. But the information stored in it will be gone once the drive is unmounted.

> comparison between drive-disk and ram-disk

```bash
# drive-disk
mkdir store-disk
cd store-disk/

# run benchmark with 8GB file 
dd if=/dev/zero of=test.iso bs=1M count=8000

8000+0 records in
8000+0 records out
8388608000 bytes (8.4 GB, 7.8 GiB) copied, 25.7227 s, 326 MB/s
# I am running an SSD
rm test.iso
```

```bash
# ram-disk
mount -t tmpfs tmpfs /mnt/ram -o size=8192M

cd ram/

dd if=/dev/zero of=test.iso bs=1M count=8000

8000+0 records in
8000+0 records out
8388608000 bytes (8.4 GB, 7.8 GiB) copied, 2.59548 s, 3.2 GB/s

rm test.iso
```

* run a command without leaving a trace in `history`
```bash
# add a leading space
 ls
# as opposed to
ls

# check command history 
history
```
* fix a long command that you typed on the terminal

```bash
# rather than pressing up and editing the command, type

fc

# editor opens up, edit the command as per your requirement and save
```

* tunnel with ssh (local port 3337 -> remote host's 127.0.0.1 on port 6379)

```bash
ssh -L 3337:127.0.0.1:6379 root@machine -N
```

* quickly create folders

```bash
mkdir -p folder/{sub1,sub2}/{sub1,sub2,sub3}

mkdir -p folder/{1..100}/{1..100}
```
* intercept stdout and log to file

```bash
cat file.txt | tee -a log.txt | cat > /dev/null
cat log.txt
```

* exit terminal but leave all processes running
```bash
disown -a && exit

# demonstration
sleep 123
bg
disown -a && exit

ps aux | grep sleep
```