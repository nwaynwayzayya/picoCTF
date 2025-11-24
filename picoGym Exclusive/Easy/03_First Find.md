# First Find

### Objective:

Unzip this archive and find the file named 'uber-secret.txt'
`Download zip file`

### Commands / Steps:

```bash
# Step 1: Get the file from the link, 'file'.
wget https://artifacts.picoctf.net/c/502/files.zip

# Step 2: Unzip the file.
unzip files.zip
# Output:
# Archive:  files.zip
#    creating: files/
#    creating: files/satisfactory_books/
#    creating: files/satisfactory_books/more_books/
#   inflating: files/satisfactory_books/more_books/37121.txt.utf-8  
#   inflating: files/satisfactory_books/23765.txt.utf-8  
#   inflating: files/satisfactory_books/16021.txt.utf-8  
#   inflating: files/13771.txt.utf-8   
#    creating: files/adequate_books/
#    creating: files/adequate_books/more_books/
#    creating: files/adequate_books/more_books/.secret/
#    creating: files/adequate_books/more_books/.secret/deeper_secrets/
#    creating: files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/
#  extracting: files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/uber-secret.txt  
#   inflating: files/adequate_books/more_books/1023.txt.utf-8  
#   inflating: files/adequate_books/46804-0.txt  
#   inflating: files/adequate_books/44578.txt.utf-8  
#    creating: files/acceptable_books/
#    creating: files/acceptable_books/more_books/
#   inflating: files/acceptable_books/more_books/40723.txt.utf-8  
#   inflating: files/acceptable_books/17880.txt.utf-8  
#   inflating: files/acceptable_books/17879.txt.utf-8  
#   inflating: files/14789.txt.utf-8

# Step 3: Navigate to the directory containing 'uber-secret.txt'.
cd files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/

# Step 4: We view the contents of the file.
cat uber-secret.txt
```

### Flag:

> picoCTF{f1nd_15_f457_ab443fd1}

### Notes / Tips

- `wget <url>` → Downloads a file from a given URL.
- `unzip <file>` → Extracts the contents of a .zip archive.
- `cd <dir>` → Change directory.
- `cat <file>` → Displays file contents.

- Alternative:
    - `find files -name "uber-secret.txt"` - Search for a file named 'uber-secret.txt' inside the 'files' directory.
    - `grep -R "picoCTF{" files/` - This will search all files recursively in files/ and print any line containing the flag.



