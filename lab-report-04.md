# Lab Report 4: Vim (week 8)
---
## Practicing Vim expertise:

1. Step 4 - Log into ieng6
   - Result of ```ssh djernigan@ieng6.ucsd.edu```: ![Image](https://github.com/Domenicj1/cse15l-lab-reports/assets/146692334/0142e3a4-017c-4855-bd8c-ebba952bcd13)
   - Keystroke sequence: ```ssh<space>djernigan@ieng6.ucsd.edu<enter>```
   - Summary: I ran the `ssh` command with my ieng6 credentials which is the Secure Shell program that creates a "tunnnel" from my personal machine to the remote ieng6 server.
---
 
2. Step 5 - Cloning my fork of the lab7 repository (using the SSH URL)
   - Result of ```git clone git@github.com:Domenicj1/lab7.git```: ![Image](https://github.com/Domenicj1/cse15l-lab-reports/assets/146692334/82d7fcac-a660-4332-9e7f-acc631c937d9)
   - Keystroke sequence: ```git<space>clone<space>git@github.com:Domenicj1/lab7.git<enter>```
   - Summary: I ran the ```git clone``` command with the SSH URL to my forked repository, essentially downloading the repository to the machine via termial as if directly from the ieng6 terminal.
---

3. Step 6 - Running the tests, ensuring failure
   - Result of ```cd ./lab7; bash test.sh```: ![Image](https://github.com/Domenicj1/cse15l-lab-reports/assets/146692334/e105ce1c-3a45-4e59-88f8-2b92eb5cb723)
   - Keystroke sequence: ```cd<space>./lab7;<space>bash<space>test.sh<enter>```
   - Summary: I ran the `cd` command to first enter my terminal from the home directory to the newly downloaded lab7 folder. From there I ran the `bash` script to compile and run all the neccesary java files and packages.
---

4. Step 7 - Editing the code in terminal with Vim to fix the bug
   - Result of ```vim ListExamples.java; <:44> --> <:s/1/2> --> <:wq> : ![Image](https://github.com/Domenicj1/cse15l-lab-reports/assets/146692334/af748f68-6828-41a4-8275-dd841623bdd7)
   - Keystroke sequence: ```vim<space>ListExamples.java``` then ```<:44><enter><:s/1/2><enter><:wq><enter>```
   - Summary: I ran the `vim` command with the name of the java file `ListExamples.java` to edit the file fixing the bug which the error feedback highlighted now that my terminal was under the appropriate directory. Then, I navigated to the 44th line with `<:44>` to quickly fix the indicated bug, used ```<:s/1/2>``` to substitute the first occurence of the number `1` to the number `2`, then used `<:wq>` to safley write the changes to the file, save them, and exit.
---
  
5. Step 8 - Running the tests again, verifying succesful debugging and Vim usage
   - Result of ```bash test.sh``` ![Image](https://github.com/Domenicj1/cse15l-lab-reports/assets/146692334/c14882ef-56f6-4b0d-87b1-1f44cd5586c5)
   - Keystroke sequence: ```bash<space>test.sh<enter>```
   - Summary: I ran the `bash` script again to re-run the JUnit tests, ensuring my alterations to the buggy methods through Vim actually worked.
---

6. Step 9 - Add, Commit, then Push the changes to my version of the forked repository GitHub account
   - Result of ```git add .``` then ```git commit -m "step 6"``` then ```git push``` ![Image]("https://github.com/Domenicj1/cse15l-lab-reports/assets/146692334/19953d3d-b6c4-4b25-a8b7-0a2e149b6233)
   - Keystroke sequence: ```git<space>add<space>.``` then ```git<space>commit<space>-m<space>"step<space>6"``` then ```git<space>push```
   - Summary: First, I had to `add` the changes to the staging area, then to actually `commit` them to the repository I used the neccessary `git commit` command with a succinct commit message usuing the `-m` option to avoid having to write out a commit message from a prompted editor. Lastly, I `push`ed these changes to GitHub so they can actually be visible there.
