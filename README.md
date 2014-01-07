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
#declare a array
declare -a arrayname=(element1 element2 element3)
#or like js
Unix[0]='Debian'
Unix[1]='Red hat'
Unix[2]='Ubuntu'
Unix[3]='Suse'

#traverse
declare -a names=(a b c)
for name in ${names[@]};do
    echo $name
done

```


variable
```bash
# exists
[ -z $varname ]  
```
