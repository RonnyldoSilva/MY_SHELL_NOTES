# MY SHELL NOTES
 
## CSV
### Split file by number of lines:
#### split -l 'number of lines' 'file'
```shell
split -l 1000000 empresas.csv 
```

### Remove null bytes from CSV:
```shell
sed -i 's/\x0//g' file.csv
```

### Rename files by incrementing a number within the filename
```shell
#!/bin/bash

NEWFILE=$1

for file in `ls|sort -g -r`
do
    filename=$(basename "$file")
    extension=${filename##*.}
    filename=${filename%.*}

    if [ $filename -ge $NEWFILE ]
    then
        mv "$file" "$(($filename + 1))".$extension
    fi
done
```
