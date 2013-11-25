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


array
```bash
IFS=', ' read -a array <<< "word1, word2"
echo ${array[0]} #word1
```

variable
```bash
# exists
[ -z $varname ]  
```
