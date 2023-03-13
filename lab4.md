# Github and Login Command-Line Setup

## 1. Setup
![image](https://user-images.githubusercontent.com/86742001/224608602-381f4e6a-a841-4219-91b0-a3d0e3703294.png)
- Go to `Setting` -> Under `Danger Zone`, click `Delete this repository`
## 2. Setup
![image](https://user-images.githubusercontent.com/86742001/224608720-0fedc9f5-2608-4710-9984-807d789b0ed4.png)
- Click `Fork` to fork the repository
## 3. The real deal
![image](https://user-images.githubusercontent.com/86742001/224608755-b7f5c6a2-cf2e-4cef-a4e9-377d60a8f2c6.png)
- Start the timer
## 4. Log into ieng6
![image](https://user-images.githubusercontent.com/86742001/224613658-6ba4b0af-69a9-4a29-998c-a5adcada6fde.png)
- `ssh cs15lwi23ast@ieng6.ucsd.edu<enter>`
## 5. Clone your fork of the repository from your Github account
![image](https://user-images.githubusercontent.com/86742001/224614016-8e8cc357-8f41-4db5-8a94-86d3212dd784.png)
- `git clone git@github.com:ucsd-cse15l-w23/lab7.git<enter>`
- Keys pressed: `git clone <Ctrl-v><enter>`
## 6. Run the tests, demonstrating that they fail
![image](https://user-images.githubusercontent.com/86742001/224614478-1415030f-7fc6-4918-b50d-7ac0d8ab5d73.png)
- Change the directory into lab7 -> `cd lab7`
- Run the test using JUnit
- Keys pressed: `cd lab7<enter>`
                `<Ctrl-v><enter>`
                `<Ctrl-v>L<tab>Tests<enter>`
- I copied JUnit command from 15l Week3 - `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java`, and
`java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore`. I use `L<tab>` to auto pintout "ListExamples" 
## 7. Edit the code file to fix the failing test
![image](https://user-images.githubusercontent.com/86742001/224614907-0aec15bc-3baa-41b9-a652-437957a85402.png)
- `nano +43 ListExamples.java` -> in line 43, change `index1` to `index2`
- Keys pressed: `nano +43 L<tab>.java<enter>`
                `<Ctr-o><enter>`
                `<Ctrl-x>`
- I use `L<tab>` to auto pintout "ListExamples", save file with `<Ctr-o>`, and exit the nano editor with `<Ctrl-x>`
## 8. Run the tests, demonstrating that they now succeed
![image](https://user-images.githubusercontent.com/86742001/224616519-98602d9c-0400-4599-a304-cb5492a678ca.png)
- Keys pressed: `<up><up><up><enter>`
                `<up><up><up><enter>` 
- I use  `<up><up><up>` to find the JUnit command that in step 6
## 9. Commit and push the resulting change to your Github account
![image](https://user-images.githubusercontent.com/86742001/224620478-6d466517-1bfd-4a36-b5ea-65a207efef96.png)
- Add the updated file -> `git add ListExamples.java<enter>`
- Enter message -> `git commit -m "updated"<enter>`
- Keys pressed: `git add L<tab>.java<enter>`
                `git commit -m "updated"<enter>`
- I use `L<tab>` to auto pintout "ListExamples"
![image](https://user-images.githubusercontent.com/86742001/224617624-1cd5db80-2128-4049-b963-5a56256dd666.png)
- Push new change to repository -> `git push<enter>`
