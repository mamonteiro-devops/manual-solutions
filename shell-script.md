Default behavior of Awk: By default Awk prints every line of data from the specified file.  
```
awk '{print}' employee.txt
```

Print the lines which match the given pattern. 
```
awk '/manager/ {print}' employee.txt 
```

Splitting a Line Into Fields
```
awk '{print $1,$4}' employee.txt 
```

References: https://www.geeksforgeeks.org/awk-command-unixlinux-examples/

