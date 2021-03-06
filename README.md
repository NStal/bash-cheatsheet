bash-cheatsheet
===============

My bash cheatsheet

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
#for item
declare -a names=(a b c)
for name in ${names[@]};do
    echo $name
done

#for index
for idx in ${!array[@]}; do
	ehco $idx ${array[idx]}
done

```

loops
```bash
for i in seq 10 25; do
	echo heh index: $i
done

```

variable
```bash
# exists
[ -z $varname ]  
# to use a variable globally
export globalVar="value"
# to check if a variable is number
if echo $var | egrep -q '^[0-9]+$'; then
	echo $var is number
fi
```

conditions
```bash
#check if contains
string='My long string';
if [[ $string == *"My long"* ]]; then
	echo "It's there!";
fi
```

get script path
via http://stackoverflow.com/questions/59895/can-a-bash-script-tell-what-directory-its-stored-in
```bash
DIR="$( cd "$( dirname "${BASH_SOURCE[0]}" )" && pwd )"
#another method (works when using symbolic link to)
DIR=$(dirname $(readlink -f $0))
```

catch Ctrl_c signal
```bash
#function name can be something else
ctrl_c(){
	echo 'aborted by Ctrl_c'
}
trap ctrl_c INT
```
arguments
```bash
declare -a args=($*)
#to get the last arguments (there might be a better way then this）
lastArg=${args[$#-1]}
#to slice argumentse and pass it to another script
anotherScript ${args[@]:1}

#to loop throw arguments contains space
#see http://stackoverflow.com/questions/905891/passing-argument-containing-space-in-shell-script
for a in "$@"; do #put $@ input quotes
	echo "$a"
done

```
