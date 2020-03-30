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
