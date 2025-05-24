# Windows-basic-commands-batchscript
Ex08-Windows-basic-commands-batchscript

# AIM:
To execute Windows basic commands and batch scripting

# DESIGN STEPS:

### Step 1:

Navigate to any Windows environment installed on the system or installed inside a virtual environment like virtual box/vmware 

### Step 2:

Write the Windows commands / batch file . Save each script in a file with a .bat extension. Ensure you have the necessary permissions to perform the operations. Adapt paths as needed based on your system configuration.
### Step 3:

Execute the necessary commands/batch file for the desired output. 




# WINDOWS COMMANDS:
## Exercise 1: Basic Directory and File Operations
Create a directory named "my-folder"

## COMMAND AND OUTPUT
```
mkdir my-folder
```
![image](https://github.com/user-attachments/assets/d8479fc2-b968-4d43-b6e7-3391a673804a)

Remove the directory "my-folder"

## COMMAND AND OUTPUT
```
rmdir my-folder
```
![image](https://github.com/user-attachments/assets/b5851341-a48d-48f7-8b98-4c4fd581c6db)

Create the file Rose.txt

## COMMAND AND OUTPUT
```
COPY CON Rose.txt
A clock in a office can never get stolen
Too many employees watch it all the time
^Z
1 file(s) copied
dir Rose.txt

```
![image](https://github.com/user-attachments/assets/07b1d059-ae7f-4d23-9e82-a29cb8d756c2)

Create the file hello.txt using echo and redirection

## COMMAND AND OUTPUT
```
echo “hello world” > hello.txt
type hello.txt

```
![image](https://github.com/user-attachments/assets/8fe945d6-da0f-465f-817f-ac2046ab2580)

Copy the file hello.txt into the file hello1.txt

## COMMAND AND OUTPUT
```
copy hello.txt hello1.txt
```
![image](https://github.com/user-attachments/assets/78e33f3c-9033-4cf9-9d95-666d1a2ec81f)

Remove the file hello1.txt

## COMMAND AND OUTPUT
```
del hello1.txt
```
![image](https://github.com/user-attachments/assets/f7135c27-1f18-4a1a-baab-d133d6746cab)

List out the file hello1.txt in the current directory

## COMMAND AND OUTPUT
```
dir hello1.txt
```
![image](https://github.com/user-attachments/assets/5e2ed2ca-45a5-432c-be44-3c88862c2a5d)

List out all the associated file extensions 

## COMMAND AND OUTPUT
```
assoc | more
```
![image](https://github.com/user-attachments/assets/4316a4f9-16f6-4c7d-8af8-d5a9673f02f3)

Compare the file hello.txt and rose.txt

## COMMAND AND OUTPUT
```
fc hello.txt Rose.txt
```
![image](https://github.com/user-attachments/assets/fa366558-1df7-475c-8098-8429ecbfe5f7)

## Exercise 2: Advanced Batch Scripting
Create a batch file named on the desktop. The batch file need to have a variable assigned with a desired name for ex. name="John" and display as "Hello, John".
```
@echo off
set name=John
echo Hello, %name%!
pause

```
## OUTPUT


![image](https://github.com/user-attachments/assets/5714c7d3-60a9-4e59-a812-7375d5c7a9cc)


Create a batch file  on the desktop that checks whether a user-input number is odd or not. The script should:
Prompt the user to enter a number.
Calculate the remainder when the number is divided by 2.
Display whether the number is odd or not.
Ask the user if they want to check another number.
Repeat the process if the user enters Y, and exit with a thank-you message if the user enters N.
Handle invalid inputs for the continuation prompt (Y/N) gracefully.
```
@echo off
:main
set /p number=Enter a number: 
rem Calculate remainder when divided by 2
set /a remainder=%number% %% 2
if %remainder%==1 (
    echo %number% is an odd number.
) else (
    echo %number% is not an odd number.
)
:choice
set /p continue=Do you want to check another number? (Y/N): 
if /i "%continue%"=="Y" goto main
if /i "%continue%"=="N" goto end
echo Invalid choice, please enter Y or N.
goto choice
:end
echo Thank you for using the odd number checker!
pause

```


## OUTPUT



![image](https://github.com/user-attachments/assets/f0482258-7158-4c98-b3c7-76a4c87b22e9)


Write a batch file that uses a FOR loop to iterate over a sequence of numbers (1 to 5) and displays each number with the label Number:. The output should pause at the end.
```
@echo off
for %%i in (1 2 3 4 5) do (
    echo Number: %%i
)
pause

```



## OUTPUT


![image](https://github.com/user-attachments/assets/7ec23478-e5f8-4f71-b89b-d2e6ee841d54)



Write a batch script to check whether a file named sample.txt exists in the current directory. If the file exists, display the message sample.txt exists. Otherwise, display sample.txt does not exist. Pause the script at the end to view the result.

Instructions:
Use the IF EXIST conditional statement.
Make sure the script works for files located in the same directory as the batch file.
Use pause to keep the command window open after displaying the message.
Expected Output (if the file exists):
```
@echo off
if exist sample.txt (
    echo sample.txt exists.
) else (
    echo sample.txt does not exist.
)
pause

```

## OUTPUT

![image](https://github.com/user-attachments/assets/9964ea8a-6292-4099-a4b8-4e93d0783d20)


Write a batch script that displays a simple menu with three options:
Say Hello – Displays the message Hello, World!
Create a File – Creates a file named newfile.txt with the content This is a new file
Exit – Exits the script with a goodbye message
The script should repeatedly display the menu until the user chooses to exit. Use goto statements to handle menu navigation.
```
@echo off
:menu
echo 1. Say Hello
echo 2. Create a File
echo 3. Exit
set /p choice=Choose an option: 
if "%choice%"=="1" goto hello
if "%choice%"=="2" goto createfile
if "%choice%"=="3" goto end

:hello
echo Hello, World!
goto menu

:createfile
echo Creating a file...
echo This is a new file > newfile.txt
goto menu
:end
echo Goodbye!
pause

```


## OUTPUT


![image](https://github.com/user-attachments/assets/48e79620-7e18-457d-8b56-8f72c68dbcc4)


# RESULT:
The commands/batch files are executed successfully.

