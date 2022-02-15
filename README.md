# Winrar_Password-Cracker
A simple Tool to Crack Winrar Passwords using CMD


# About
This Tool will Brute Force a Winrar protected Zip File 

# Screenshot 
![p](https://user-images.githubusercontent.com/97392345/154112275-4dcf5be3-f75f-4708-a4fc-797b0ed7ff8d.PNG)


# Installation 
1. Presss Win+r and thype Notepad there. Press enter

3. After that Copy the following Code into youre Notepad:

@echo off

title Rar Password Cracker

mode con: cols=47 lines=20

copy "C:\Program Files\WinRAR\Unrar.exe"

SET PSWD=0

SET DEST=%TEMP%\%RANDOM%

MD %DEST%

: RAR

cls

Echo----------------------------------------------

echo GET DETAIL

Echo----------------------------------------------

Echo.

SET/P "NAME=Enter File Name: "

IF "%NAME%"=="" goto NERROR

goto GPATH

:NERROR

Echo----------------------------------------------

echo ERROR

Echo----------------------------------------------

Echo Sorry you can't leave it blank.

pause

goto RAR

: GPATH

SET/P "PATH=Enter Full Path : "

IF "%PATH%"=="" goto PERROR

goto NEXT

: PERROR

Echo----------------------------------------------

echo ERROR

Echo----------------------------------------------

Echo Sorry you can't leave it blank.

pause

goto RAR

: NEXT

IF EXIST "%PATH%\%NAME%" GOTO START

goto PATH

: PATH

cls

Echo----------------------------------------------

echo RROR

Echo----------------------------------------------

Echo Opppss File does not Exist.

pause

goto RAR

: START

SET /A PSWD=%PSWD%+1

UNRAR E -INUL -P%PSWD% "%PATH%\%NAME%" "%DEST%."

IF /I %ERRORLEVEL% EQU 0 GOTO FINISH

GOTO START

: FINISH

RD %DEST% /Q /S

Del "Unrar.exe"

cls

Echo----------------------------------------------

echo CRACKED

Echo----------------------------------------------

Echo.

Echo PASSWORD FOUND!

echo FILE = %NAME%

echo CRACKED PASSWORD = %PSWD%

pause>NUL

exit

REM

# Warning
1. dont forget to remove the spaces of the code when u are in the notepad, otherwise it wont work


# Usage 
1. Thype the Full Name of the file along with extension and press enter.
2. Input the location (view property of the RAR file to know the location) and press enter to proceed.
3. Now it will Brute Force the File. It will take some time, so grab some Coffee and wait
