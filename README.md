bash-cheatsheet
===============

My bash cheatsheet


# String Processing

substring
```bash
${string:0:1}
```

read file
```bash
# line by line
while read line
do
    name=$line
    echo "Text read from file - $name"
done < filename
```


variable
```bash
# exists
[ -z $varname ]  
```
