bash-cheatsheet
===============

My bash cheatsheet


# String Processing

substring
```bash
${string:0:1}
```

read input
```bash
read VARNAME
echo $VARNAME
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

read password
```bash
# turn off user input echoing
stty -echo
read PASSWORD
# $PASSWORD contains the password
# turn on user input echoing
stty echo

# or in bash simply
# -p for prompt -s for save (I guess)
read -s PASSWORD -p "Put your password:"
$echo $PASSWORD

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

loops
```bash
for i in seq 10 25; do
    echo heh index: $i
done

```
```bash
#for item
for item in ${array[@]}; do
    echo ${item} or $item
done
#for index
for idx in ${!array[@]}; do
   ehco $idx ${array[idx]}
done
```

variable
```bash
# exists
[ -z $varname ]  
```

get script path
via http://stackoverflow.com/questions/59895/can-a-bash-script-tell-what-directory-its-stored-in
```bash
DIR="$( cd "$( dirname "${BASH_SOURCE[0]}" )" && pwd )"
```

