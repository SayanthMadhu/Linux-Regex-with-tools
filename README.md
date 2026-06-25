# Linux-Regex-with-tools
## Regular Expressions in Linux with grep, sed, and awk

INTRODUCTION :
Regular Expressions (Regex) are special patterns used to search, match, and manipulate text. In Linux, regex is widely used with commands such as grep, sed, and awk. These tools help users find information quickly, edit text automatically, and process data efficiently.
Regex is very important for system administrators, DevOps engineers, programmers, and anyone who works with text files, log files, or large amounts of data.
What is a Regular Expression?
A Regular Expression is a sequence of characters that defines a search pattern. Instead of searching for exact text only, regex allows us to search for complex patterns.

For example:-
Search all email addresses in a file.
Find phone numbers in a document.
Extract IP addresses from log files.
Replace specific words automatically.
Regex makes text processing faster and more accurate.

## Common Regex Symbols
SymbolMeaning.Matches any single character*Matches zero or more occurrences+Matches one or more occurrences?Matches zero or one occurrence^Matches the beginning of a line$Matches the end of a line[ ]Matches any character inside brackets[^ ]Matches characters not inside brackets{n,m}Matches a specific number of occurrences 

Examples
a* → matches "", "a", "aa", "aaa"
a+ → matches "a", "aa", "aaa"
[0-9] → matches any digit from 0 to 9
^Linux → matches lines starting with "Linux"
Linux$ → matches lines ending with "Linux"
Using Regex with grep
The grep command is used to search for patterns in files.
Syntax
grep "pattern" filename 

Examples
1. Search for a word
grep "linux" file.txt 
This command displays all lines containing the word "linux".

3. Ignore case sensitivity
grep -i "linux" file.txt 
Matches Linux, LINUX, linux, etc.

5. Display lines not containing a word
grep -v "windows" file.txt 
Shows all lines except those containing "windows".

7. Find IP Addresses
grep -E "\b([0-9]{1,3}\.){3}[0-9]{1,3}\b" file.txt 
This command searches for IP addresses in a file.

. Applications of grep
.Searching log files
Finding errors in system logs
Filtering command output
Searching configuration files
Using Regex with sed
The sed (Stream Editor) command is used for editing and replacing text automatically.
Syntax
sed 's/old/new/' file.txt 
Examples
1. Replace a word
sed 's/linux/Linux/' file.txt 
Changes "linux" to "Linux".
2. Replace all occurrences
sed 's/old-text/new-text/g' file.txt 
The g means global replacement.
3. Remove comments
sed '/^#/d' file.txt 
Deletes lines beginning with #.
4. Remove extra spaces
sed 's/ */ /g' file.txt 
Converts multiple spaces into a single space.
5. Insert a line at the beginning
sed '1i\This is the first line.' file.txt 
Adds a new line at the top of the file.
Applications of sed
Automated text editing
Configuration file modifications
Data cleaning
Batch text processing
Using Regex with awk
The awk command is mainly used for data extraction and report generation.
Syntax
awk 'pattern {action}' file 
Examples
1. Print the second column
awk -F, '{print $2}' file.csv 
Displays the second column from a CSV file.
2. Sum values in a column
awk -F, '{sum+=$3} END {print sum}' file.csv 
Calculates the total of the third column.
3. Print long lines
awk 'length > 10' file.txt 
Shows lines having more than 10 characters.
4. Calculate total from first column
awk '{sum += $1} END {print sum}' file.txt 
Adds all values in the first column.
Applications of awk
Data extraction
Report generation
CSV file processing
Log analysis
Data transformation
Difference Between grep, sed, and awk
ToolPurposegrepSearch and filter textsedEdit and replace textawkProcess and analyze structured data 
Example
Suppose a file contains student data.
Use grep to find a particular student.
Use sed to correct a spelling mistake.
Use awk to calculate average marks.

Advantages of Regular Expressions
Fast text searching.
Reduces manual work.
Automates text processing tasks.
Works with large files efficiently.
Useful in programming, DevOps, and system administration.
Conclusion
Regular Expressions are powerful tools for pattern matching and text manipulation in Linux. Commands like grep, sed, and awk use regex to search, edit, and process data efficiently. Learning regex improves productivity and makes text processing tasks easier. Regular expressions are an essential skill for Linux users, programmers, system administrators, and DevOps engineers.
