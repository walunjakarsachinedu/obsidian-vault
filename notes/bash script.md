variable:
```bash
value="hello world"
echo $value # to reference value we prefix variable with "$" symbol
```

if-else:
```bash
if [ 1 == 2 ]; 
then 
	echo "body of if-block executed"
else 
	echo "body of else-block executed"
fi
```

for loop:
```bash
for file in $folder
do
	echo file
done
```

function:
```bash
welcome() {
	echo "welcome $1"
}
welcome "sachin"   # outputs: welcome sachin
```