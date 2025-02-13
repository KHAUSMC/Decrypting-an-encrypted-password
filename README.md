# 🔐 Decrypting an Encrypted Password  
## **Linux Decryption Challenge – Breaking the Caesar Cipher**  

All the files in my home directory have been encrypted, and it's up to me to break the encryption and recover my data. Using **Linux commands**, I’ll work through the challenge step by step, uncovering hidden messages along the way.

### **🔎 What’s the Plan?**  
1. **Explore my home directory** to find any accessible files.  
2. **Locate a hidden file** that contains encoded instructions.  
3. **Break the Caesar cipher (shift 3)** to reveal the next steps.  
4. **Follow the decryption instructions** to recover my lost files.  
5. **Use OpenSSL** to decrypt the final encrypted file.  

This challenge will test my ability to **navigate Linux, manipulate text, and apply basic cryptographic techniques**. Time to put my skills to the test and decrypt these messages! 🚀  

---

# 🔐 **Linux Decryption Challenge: Breaking the Cipher**  
In this challenge, all of my data has been encrypted, and I need to decrypt it by solving a **Caesar cipher** and using Linux commands. My goal is to recover the encrypted file by following the given clues.

---

## 📸 **Overview of the Entire Process**  
![Linux Decryption Challenge](https://i.imgur.com/PSqbMFO.png)  

---

## 🛠️ **Step 1: Listing Files in the Home Directory**  
The challenge starts in my home directory (`/home/analyst`). To see what files are available, I ran:  

'ls'

### 📂 **Output:**
- 🔒 **Q1.encrypted** → The encrypted file that needs to be decrypted.  
- 📜 **README.txt** → Contains crucial instructions for recovering my data.  
- 📁 **caesar** → A directory that may contain hidden files or clues.

## 📖 Step 2: Reading the `README.txt` File  

To check for instructions, I used the following command:  
<br>cat README.txt</br>

Which listed:
All of your data has been encrypted.
To recover your data, you will need to solve a cipher.
To get started, look for a hidden file in the caesar subdirectory.

This message confirms that my next step is to navigate to the caesar directory and locate a hidden file that holds the key to decryption. 🔎

## 🔎 Step 3: Finding and Decrypting the Hidden File  

In this task, I need to locate a **hidden file** in my home directory and **decrypt the Caesar cipher** it contains. Successfully completing this step will provide the necessary instructions to move forward in the challenge.

### 📂 **Navigating to the Hidden File**  
To begin, I need to switch to the `caesar` subdirectory inside my home directory using the following command:  

**cd caesar**

![Hidden File Search](https://i.imgur.com/6XGHtNY.png)

## 📂 Step 4: Listing All Files, Including Hidden Files  

To locate the **hidden file** needed for decryption, I used the following command:

***ls -a***

![Listing Hidden Files](https://i.imgur.com/UgJALuG.png)

## 🔐 Step 5: Viewing and Understanding the Encrypted File  

Now that I have found the hidden file `.leftShift3`, I need to check its contents to understand what information it holds. To do this, I used the following command:

***cat .leftShift3***

![Encrypted File Output](https://i.imgur.com/Od7i3LQ.png)

### 📂 **Expected Output (Scrambled Text):**
***Lq rughu wr uhfryhu brxu ilohv brx zloo qhhg wr hqwhu wkh iroorzlqj frppdqg:
...***

At first glance, the text appears scrambled. This is because it has been encrypted using a Caesar cipher.

## 🔓 Step 6: Decrypting the `.leftShift3` File  

Now that I have identified that the `.leftShift3` file is encrypted using a **Caesar cipher with a shift of 3**, I can use the `tr` (translate) command to **decrypt** it.

### 🛠️ **Decryption Command**  
To shift all letters **backward by 3 places**, I used the following command:

***cat .leftShift3 | tr "d-za-cD-ZA-C" "a-zA-Z"***

![Decryption Command in Action](https://i.imgur.com/orREwsH.png)

🔎 Breaking Down the Command:
- **`cat .leftShift3`** → Displays the contents of the file.
- **`|` (Pipe Operator)** → Passes the output from `cat` to `tr` for processing.
- **`tr "d-za-cD-ZA-C" "a-zA-Z"`** → Translates the shifted text back to its original form by replacing:
  - **`"d-za-c"`** → (Shifted lowercase letters) with **`"a-z"`** (Original lowercase letters).
  - **`"D-ZA-C"`** → (Shifted uppercase letters) with **`"A-Z"`** (Original uppercase letters).

## 🔄 Step 7: Returning to the Home Directory  

Before moving on to the next task, I need to **return to my home directory**.  
To do this, I use the following command:

cd ~

![Decryption Process](https://i.imgur.com/TAMJ2jn.png)

# 🔓 Step 8: Decrypting the Encrypted File  

Now that I have successfully **solved the Caesar cipher**, I have obtained the **decryption command** from the `.leftShift3` file.  
In this step, I will use **OpenSSL** to decrypt the `Q1.encrypted` file and recover my lost data.

---

## 🛠️ **Command Used for Decryption**
To decrypt the encrypted file and recover its contents, I ran the following command:

***openssl aes-256-cbc -pbkdf2 -a -d -in Q1.encrypted -out Q1.recovered -k ettubrute***

## 🔎 Breaking Down the Command  

| Command Component   | Explanation  |
|---------------------|-------------|
| `openssl`          | Calls the **OpenSSL** encryption/decryption tool. |
| `aes-256-cbc`      | Specifies the **AES-256 CBC encryption algorithm**. |
| `-pbkdf2`          | Uses **Password-Based Key Derivation Function 2 (PBKDF2)** for stronger security. |
| `-a`               | Tells OpenSSL that the input file is **Base64 encoded**. |
| `-d`               | Specifies **decryption mode** (instead of encryption). |
| `-in Q1.encrypted` | Defines the **input file** (`Q1.encrypted`), which is the file to decrypt. |
| `-out Q1.recovered`| Defines the **output file** (`Q1.recovered`), which will contain the decrypted data. |
| `-k ettubrute`     | Uses `"ettubrute"` as the **decryption key**. |

## 📂 Step 9: Verifying the Decrypted File  

Now that I have successfully decrypted the `Q1.encrypted` file, I need to **confirm that the new decrypted file (`Q1.recovered`) has been created**.  

To do this, I will **list the contents of my current working directory** using the following command:

***ls***

![Directory Listing After Decryption](https://i.imgur.com/cvrkukK.png)

### 🔎 **Why Use `ls` Again?**
- ✅ **Checks if `Q1.recovered` exists** after running the OpenSSL decryption command.  
- ✅ **Verifies that the decryption process was successful** by ensuring a new output file was generated.  
- ✅ **Confirms the current directory's contents** before proceeding to read the recovered file.  







































