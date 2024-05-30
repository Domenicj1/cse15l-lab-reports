# Lab Report 4: VIM (week 8)
---
## Practicing Vim expertise:
1. Step 4 - Log into ieng6
   - Result of ```ssh djernigan@ieng6.ucsd.edu```: ![Image](Screenshot 2024-05-29 146692334.png)
      - cd with no arg;
      - Absolute path to working directory: ```/Users/jerni```;
      - Executing the ```cd``` command without an argument did nothing as it doesn't know what  folder/directory/file path to enter into;
   - Result of ```cd cse15l-lab-reports```: ![Image](Screenshot 2024-04-08 114758.png)
      - cd with with path to directory/folder as arg
      - Absolute path to working directory: ```/Users/jerni```;
      - Executing the ```cd``` command with an existing subfolder path as its argument effectivley enters into that directory or folder from the working directory without error
   - Result of ```cd lab-report-01.md```: ![Image](Screenshot 2024-04-08 115641.png)
      - cd with path to file as arg
      - Absolute path to working directory: ```/Users/jerni/cse15l-lab-reports```;
      - Executing the ```cd``` command with an existing subfile path as its argument from the working directory threw an error (ItemNotFoundException) as I attempted to "change directory" into a file of the working directory

---
