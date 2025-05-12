# UiPath-Experiment-6
# Date:12/05/2025
# Register No.:212224040302
# Name: S Sesha Raghavan
# AIM:
Copy all files from a source folder to a destination folder and rename them by appending a timestamp to the file names.

# Requirements:
1.) Laptop

2.) Internet

3.) UiPath Studio

# Process:
Step 1: Define Variables

sourceFolder (String) → Path to source folder

destinationFolder (String) → Path to destination folder

files (Array of String) → Holds list of file paths

timestamp (String) → Holds current timestamp

Step 2: Get File List
Use Assign:
```
files = Directory.GetFiles(sourceFolder)
```
Step 3: Generate Timestamp
Use Assign:
```
timestamp = DateTime.Now.ToString("yyyyMMdd_HHmmss")
```
Step 4: For Each File
Use a For Each activity to loop through files:
TypeArgument: String
Inside the loop:
a. Assign original file name:
```
fileName = Path.GetFileNameWithoutExtension(item)
```
b. Assign file extension:
```
extension = Path.GetExtension(item)
```
c. Assign new file name:
```
newFileName = fileName + "_" + timestamp + extension
```
d. Assign new full path:
```
destinationPath = Path.Combine(destinationFolder, newFileName)
```
e. Use Copy File activity:

From: item

To: destinationPath

# Workflow Process Image:
![WhatsApp Image 2025-05-12 at 09 16 38_f6483ccb](https://github.com/user-attachments/assets/f4be9bda-4dda-40e8-8a6c-fb44c0eb15fd)
![WhatsApp Image 2025-05-12 at 09 16 43_36b1ad9d](https://github.com/user-attachments/assets/11cfc5f2-4aba-4597-9b64-fbcc80c8d0c7)
![WhatsApp Image 2025-05-12 at 09 17 07_7b788952](https://github.com/user-attachments/assets/f77060e4-82e2-4ba8-9665-85711a2de074)
![WhatsApp Image 2025-05-12 at 09 17 31_6d386454](https://github.com/user-attachments/assets/629c7c1f-08be-49a0-938b-3805e0f1cc3f)

