## 1. Create files and check permissions

```copy
touch test1.txt
ls -l test1.txt
stat -c "%a %A" test1.txt
```

## 2. Practice chmod (numeric)

```
chmod 755 test1.txt && ls -l test1.txt
chmod 644 test1.txt && ls -l test1.txt
chmod 700 test1.txt && ls -l test1.txt
```

## 3. Practice chmod (symbolic)

```
chmod u+x test1.txt && ls -l test1.txt
chmod go-r test1.txt && ls -l test1.txt
chmod a+r test1.txt && ls -l test1.txt
```

## 4. Test umask

```
umask
umask 077
touch private_test.txt
ls -l private_test.txt
umask 022 # reset to default
```

## 5. Create a script and make it executable

```
echo '#!/bin/bash' > myscript.sh
echo 'echo "Hello World"' >> myscript.sh
chmod +x myscript.sh
./myscript.sh
```
