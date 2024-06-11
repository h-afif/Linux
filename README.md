# Ninja Skills

Answer the questions about the following files:

8V2L
bny0
c4ZX
D8B3
FHl1
oiMO
PFbD
rmfX
SRSq
uqyw
v2Vb
X1Uy

The aim is to answer the questions as efficiently as possible.

## Which of the above files are owned by the best-group group(enter the answer separated by spaces in alphabetical order)

first lats find where the file located
we creat bash script script.sh

```
cat filelist.txt | \
    while read FILENAME
    do
    find / -name "$FILENAME" -type f 2>/dev/null >> filelocations.txt;
    done
```
The result:
```
/etc/8V2L
/mnt/c4ZX
/mnt/D8B3
/var/FHl1
/opt/oiMO
/opt/PFbD
/media/rmfX
/etc/ssh/SRSq
/var/log/uqyw
/home/v2Vb
/X1Uy
```
now lats find Which of the above files are owned by the best-group group:
```
cat filelocation.txt | \
    while read FILENAME
    do
    stat -c "filename= %n, groupname= %G" "$FILENAME";
    done
```

run the script you get the result 
the answer is: 	D8B3, v2Vb


--------------------------------------------------------------------------------------------------------------------------------------------------------

## Which of these files contain an IP address?
```
cat filelocation.txt | \
    while read FILENAME
    do
    grep -oE '[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}' "$FILENAME";
    echo "$FILENAME";
    done
```
run the script this is the results:
```
/etc/8V2L
/mnt/c4ZX
/mnt/D8B3
/var/FHl1
1.1.1.1
/opt/oiMO
/opt/PFbD
/media/rmfX
/etc/ssh/SRSq
/var/log/uqyw
/home/v2Vb
/X1Uy
```
now you now what file contain if address


--------------------------------------------------------------------------------------------------------------------------------------------------------

## Which file has the SHA1 hash of 9d54da7584015647ba052173b84d45e8007eba94
```
cat filelocation.txt | \
    while read FILENAME
    do
    sha1sum "$FILENAME"
    done
```
run the script this is the results:
```
0323e62f06b29ddbbe18f30a89cc123ae479a346  /etc/8V2L
9d54da7584015647ba052173b84d45e8007eba94  /mnt/c4ZX
2c8de970ff0701c8fd6c55db8a5315e5615a9575  /mnt/D8B3
d5a35473a856ea30bfec5bf67b8b6e1fe96475b3  /var/FHl1
5b34294b3caa59c1006854fa0901352bf6476a8c  /opt/oiMO
256933c34f1b42522298282ce5df3642be9a2dc9  /opt/PFbD
4ef4c2df08bc60139c29e222f537b6bea7e4d6fa  /media/rmfX
acbbbce6c56feb7e351f866b806427403b7b103d  /etc/ssh/SRSq
57226b5f4f1d5ca128f606581d7ca9bd6c45ca13  /var/log/uqyw
7324353e3cd047b8150e0c95edf12e28be7c55d3  /home/v2Vb
59840c46fb64a4faeabb37da0744a46967d87e57  /X1Uy
```
but you can run the script like this to get just what you want
```
./script.sh | grep 9d54da7584015647ba052173b84d45e8007eba94
```
you get the result like this: 9d54da7584015647ba052173b84d45e8007eba94  /mnt/c4ZX


--------------------------------------------------------------------------------------------------------------------------------------------------------


## Which file contains 230 lines?
```
cat filelocation.txt | \
    while read FILENAME
    do
    wc "$FILENAME";
    done
```
run the script we see the result:
```
209   209 13545 /etc/8V2L
209   209 13545 /mnt/c4ZX
209   209 13545 /mnt/D8B3
209   209 13545 /var/FHl1
209   209 13545 /opt/oiMO
209   209 13545 /opt/PFbD
209   209 13545 /media/rmfX
209   209 13545 /etc/ssh/SRSq
209   209 13545 /var/log/uqyw
209   209 13545 /home/v2Vb
209   209 13545 /X1Uy
```
all file 209 but we want 230 line we see that the file "bny0" that is mean is him


--------------------------------------------------------------------------------------------------------------------------------------------------------

## Which file's owner has an ID of 502?

```
cat filelocation.txt | \
    while read FILENAME
    do
    ls -la "$FILENAME";
    done
```
The files all have "new-user" as the owner. Except for one: "X1Uy". It has "newer-user" as it's owner.

so lats see id of the newer-user with command
```
id -u newer-user
```
we get the result: 502


--------------------------------------------------------------------------------------------------------------------------------------------------------


## Which file is executable by everyone?
```
cat filelocation.txt | \
    while read FILENAME
    do
    ls -la "$FILENAME";
    done
```
the same script if you run him you get 
```
-rwxrwxr-x 1 new-user new-user 13545 Oct 23  2019 /etc/8V2L
-rw-rw-r-- 1 new-user new-user 13545 Oct 23  2019 /mnt/c4ZX
-rw-rw-r-- 1 new-user best-group 13545 Oct 23  2019 /mnt/D8B3
-rw-rw-r-- 1 new-user new-user 13545 Oct 23  2019 /var/FHl1
-rw-rw-r-- 1 new-user new-user 13545 Oct 23  2019 /opt/oiMO
-rw-rw-r-- 1 new-user new-user 13545 Oct 23  2019 /opt/PFbD
-rw-rw-r-- 1 new-user new-user 13545 Oct 23  2019 /media/rmfX
-rw-rw-r-- 1 new-user new-user 13545 Oct 23  2019 /etc/ssh/SRSq
-rw-rw-r-- 1 new-user new-user 13545 Oct 23  2019 /var/log/uqyw
-rw-rw-r-- 1 new-user best-group 13545 Oct 23  2019 /home/v2Vb
-rw-rw-r-- 1 newer-user new-user 13545 Oct 23  2019 /X1Uy
```
as you can see -rwxrwxr-x 1 new-user new-user 13545 Oct 23  2019 /etc/8V2L\
hase the x for all the users  "x=executable  r=read  w=write"





