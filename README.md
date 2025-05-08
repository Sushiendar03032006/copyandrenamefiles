# Aim:
To copy all .csv and .xlsx files from a source folder to a destination folder and rename them by appending the current timestamp to each file name using UiPath.

# Software Required:
```
1.UiPath Studio (Community or Enterprise Edition)
2. .NET Framework (automatically handled by UiPath)
3. A Windows PC with file system access
```

# Procedure:
```
1.Open UiPath Studio and create a new Process.
2.Create Variables: sourceFolder (String) → Path of the source folder.
                    destinationFolder (String) → Path of the destination folder.
3.Use an Assign activity to set:
   sourceFolder = "C:\Users\YourName\Desktop\source"
   destinationFolder = "C:\Users\YourName\Desktop\destination"
4.Drag in a For Each File in Folder activity:\
5.Inside the loop, add an Assign activity to create a timestamped filename: newFileName = Path.GetFileNameWithoutExtension(File.Name) + "_" + Now.ToString("yyyyMMdd_HHmmss") + File.Extension
6..Add another Assign activity to create the full destination path:  destFilePath = Path.Combine(destinationFolder, newFileName)
7.Use a Copy File activity:
    From: File.FullName
    To: destFilePath
8.Run the workflow. All matching files will be copied to the destination folder with the current timestamp appended.
```
# Workflow:

# Output:

# Result:
Each file from the source folder (with .csv or .xlsx extension) will be copied to the destination folder with a timestamp appended to its name.
