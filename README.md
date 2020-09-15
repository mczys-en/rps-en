
# * Front-end Android APP development instructions
## 1 Front-end development includes code and logic development.

## 2 This is the simplest online guessing game android mobile app, excluding ios and pc. At present, I have edited the layout page xml, UI interface and simple page jump logic function. Please download the code details from my GitHub: mczys/Rpsj.

## 3 Please use Kotlin for coding, which can reduce the amount of code and facilitate maintenance. If you use java to write the program, please convert to kotlin and verify that the debugging is passed. It is recommended to use jetpack components such as ViewModel, DataBinding+ViewBinding, etc. Resources such as strings are centrally stored and managed in the resource. I used ViewBinding when writing the front-end layout. FindViewById is no longer in the jump process, which reduces a lot of unnecessary null pointer logic verification, greatly reduces the amount of code, and is easy to maintain. At the same time, it improves the running speed and reduces various accidental conflicts. Bug.

## 4 For front-end development, please adhere to the principles of concise code, stable operation, and safety protection, and try to use automated operation and maintenance programs.

# * front-end Android APP development content
## 1 Registration and login function (activiti_main)
### 1-1 To make the registration and login function (the only method), please use the Biometric biometric (fingerprint) verification encryption solution after android 4.0 version.

### 1-2 Save fingerprint registration login verification function (client and server)

### 1-3 Set the default save automatic login function. That is, you can log in automatically without fingerprint verification. If you cancel the default function, you need to log in with fingerprint verification every time.

## 2 Set the user list function (bplayer)
### 2-1 Set the function of displaying the information on the first line of the user list after the user logs in. Click the "Yes" button on the far right, it will become "No" unclickable state

### 2-2 Set the function of displaying all user information in the user list, and the data comes from the database. Click the "Yes" button on the far right to apply for the game function to the user individually.

### 2-3 Realize the single selection box function of the game room (9D-1D) and realize the long-term storage function. The user can set any level lower than the number of gold coins of the user, but it cannot be higher than the number of gold coins of the user. If the user’s “gold coins” decrease below the set level, the user’s level will be automatically reduced to adapt to the actual “gold coins” quantity. If the number of "gold coins" increases, the set level remains unchanged.

## 3 Invite game function (bplayer)
### 3-1 Set up the function of automatically inviting games: Click the button "auto apply" under (bplayer), it will automatically apply for games with users of the same level in the game room (9D-1D) set by this user, and display the text The box "Applying to other users for matchmaking". Each applicant has a 20-second opportunity to choose. If they agree, both parties will enter the same game table (cgame). If they choose not to agree or have no choice, they will automatically apply to the next user after 20 seconds. If all users do not choose to agree, the text "Automatic application end" is returned.

### 3-2 Set up the function of individually inviting the game: In (bplayer), the user can click the button that shows "yes" in the user list item "Apply" to apply to the user individually. The other party will have 20 seconds to choose the time, and the other party will click to agree Button, both sides enter the same game table (cgame), if the other side does not respond, it will display "application end".

## 4 Realize the game function (cgame)
### 4-1 After both sides enter the game table (page c), they can click the button "your start" on their side, the button will turn green, and the game table on the opponent's mobile phone will also be displayed in green simultaneously, so that the opponent is Know that the user has started the game. If the opponent also clicks the "Start" button, the user's "Opponent Start" button will also turn green simultaneously, and the countdown numbers of both sides of the game will start to count down and display 20, 19,. . . . . . 2, 1, 0. During this period, both parties should choose to click on one of the 3 guessing images as their own punch. After the timer is over, the two $-shaped images in the middle will become the punch images of both sides, and the number will be displayed in the countdown. The text "wins" and "loses" results. The punching pattern of the "winning" side turns gold, and the punching pattern of the "losing" side turns gray; if it is a tie, the countdown numbers for both sides display the text "Tie is void", and the punching patterns of both sides turn gray: if in If one party does not click on the guessing image during the countdown, the system will select the user's default guessing image to calculate the outcome. If the user does not select the default guessing image, it will be judged by the system.

### 4-2 The "Gold Coins" of the "winning" side will be awarded "nDx98%", and the other "nDx2%" will be automatically collected by the guessing team. At the same time, the “winning” value of the winner’s item will add “1” points. Others remain unchanged. The item "gold coin" of the "failed" side will be deducted "nD" points, and the value of the "failed" item of the negative side will be increased by "1". Others remain unchanged. If it is a tie, the game will be invalid, and the client and database of both parties will not save any data.

### 4-3 "Time and Date" is set to Greenwich International Standard Time. The time will be fixed after the game is over, and the result of the game page will be synchronized and saved on the server, and the clients of both parties.

### 4-4 The small radio button to the left of the button "your start", click it will pop up 3 guessing radio buttons, choosing one of them will be the default punch selection. Please realize the long-term preservation function.

### 4-5 The current countdown performance is unstable, please adjust or replace it. And realize that after the countdown ends, it becomes the letter "Win" or "Fail".

### 4-6 If both parties continue to choose "Start", they will enter the next game; if one party chooses to withdraw, the game will end and return to the (bplayer) page.

### 4-7 After the game is over, realize the synchronization and save the result on both client side. 7 User history function (ehistory) and 8 Actual game page (cgame) and server side.

### 4-8 For the logical judgment of both sides of the game, please go to GitHub or online to search for many open source code for guessing games.

## 5 Setting function (dsetting)
### 5-1, 5-2 Realized by the backend: 8 Make user transfer function

### 5-3 Display user account information information Set to display the user name, mobile phone number (account), and fingerprint identification information of the user.

### 5-4 User History Click the button to jump to the following: 7 User history function (ehistory)

### 5-5 User feedback. Set the function for users to send feedback to the server to receive

### 5-6,5-7 without editing

## 6 User history function (ehistory)
Set long-term preservation of each game record in the client and database. Click on this historical game record to jump to its fixed game page (cgame).

## 7 Fixed game page (cgame)
Set the permanent save of each fixed game page (cgame) in the client and database.
