<h1>Linux Commands to File Permissions</h1>

 ### 

<h2>Project Description</h2>
The research team at my organization needs to update the file permissions for certain files and directories within the <i>projects</i> directory. The permissions do not currently reflect the level of authorization that should be given. Checking and updating these permissions will help keep their system secure. To complete this task, I performed the following tasks<br />


<h2>Languages and Utilities Used</h2>

- <b>Linux</b>
- <b>Bash</b>

<h2>Project Walk-Through:</h2>

<p align="center">
<b>Check file and directory details:</b>
<br/> The following code demonstrates how I used Linux commands to determine the existing permissions set for a specific directory in the file system. <br/>
<br/> <img src="https://i.imgur.com/00iC154.png" height="80%" width="80%" alt=/>
<br/> The first line of the screenshot displays the command I entered, and the other lines display the output. The code lists all contents of the <i>projects</i> directory. I used the <i>ls</i> command with the <i>-la</i> option to display a detailed listing of the file contents that also returned hidden files. The output of my command indicates that there is one directory named drafts, one hidden file named <i>.project_x.txt</i>, and five other project files. The 10-character string in the first column represents the permissions set on each file or directory.
 <br/>
 <br/>
<b>Describe the permissions string:</b> <br/>
The 10-character string can be deconstructed to determine who is authorized to access the file and their specific permissions. The characters and what they represent are as follows:
<ul>
<li>1st character: This character is either a d or hyphen (-) and indicates the file type. If it’s a d, it’s a directory. If it’s a hyphen (-), it’s a regular file.</li>
<li>2nd-4th characters: These characters indicate the read (r), write (w), and execute (x) permissions for the user. When one of these characters is a hyphen (-) instead, it indicates that this permission is not granted to the user.</li>
<li>5th-7th characters: These characters indicate the read (r), write (w), and execute (x) permissions for the group. When one of these characters is a hyphen (-) instead, it indicates that this permission is not granted for the group.</li>
<li>8th-10th characters: These characters indicate the read (r), write (w), and execute (x) permissions for other. This owner type consists of all other users on the system apart from the user and the group. When one of these characters is a hyphen (-) instead, that indicates that this permission is not granted for other.</li>
</ul>
For example, the file permissions for <i>project_t.txt</i> are <i>-rw-rw-r--</i>. Since the first character is a hyphen (-), this indicates that <i>project_t.txt</i> is a file, not a directory. The second, fifth, and eighth characters are all r, which indicates that user, group, and other all have read permissions. The third and sixth characters are w, which indicates that only the user and group have write permissions. No one has execute permissions for <i>project_t.txt</i>.
<br />
<br />
<p align="center">
<b> Change file permissions:</b> <br/>
The organization determined that other shouldn't have write access to any of their files. To comply with this, I referred to the file permissions that I previously returned. I determined <i>project_k.txt</i> must have the write access removed for other. 
 <br/>
The following code demonstrates how I used Linux commands to do this:<br />
<br />
<img src="https://i.imgur.com/Mp9xtVy.png" height="80%" width="80%"alt=/><br />
The first two lines of the screenshot display the commands I entered, and the other lines display the output of the second command. The chmod command changes the permissions on files and directories. The first argument indicates what permissions should be changed, and the second argument specifies the file or directory. In this example, I removed write permissions from other for the <i>project_k.txt</i> file. After this, I used <i>ls -la</i> to review the updates I made.<br/>
<br/>
<b>Change file permissions on a hidden file:</b>  
 <br/>
The research team at my organization recently archived <i>project_x.txt</i>. They do not want anyone to have write access to this project, but the user and group should have read access. 
<br/>
The following code demonstrates how I used Linux commands to change the permissions:
<br/>
<br/>
<img src="https://i.imgur.com/9cbXAuN.png" height="80%" width="80%" alt=/>
<br />
 The first two lines of the screenshot display the commands I entered, and the other lines display the output of the second command. I know <i>.project_x.txt</i> is a hidden file because it starts with a period (.). In this example, I removed write permissions from the user and group, and added read permissions to the group. I removed write permissions from the user with <i>u-w</i>. Then, I removed write permissions from the group with <i>g-w</i>, and added read permissions to the group with <i>g+r</i>. 
 <br />
 <br />
<b>Change directory permissions:</b>  
<br/>
 My organization only wants the <i>researcher2</i> user to have access to the drafts directory and its contents. This means that no one other than <i>researcher2</i> should have execute permissions.
<br/>
The following code demonstrates how I used Linux commands to change the permissions:
<br/>
<img src="https://i.imgur.com/7xOud2x.png" height="80%" width="80%" alt=/>
<br />
 The first two lines of the screenshot display the commands I entered, and the other lines display the output of the second command. I previously determined that the group had execute permissions, so I used the <i>chmod</i> command to remove them. The <i>researcher2</i> user already had execute permissions, so they did not need to be added.
 <br />
 <br />
<b>Summary:</b>  <br/>
I changed multiple permissions to match the level of authorization the organization wanted for files and directories in the <i>projects</i> directory. The first step in this was using <i>ls -la</i> to check the permissions for the directory. This informed my decisions in the following steps. I then used the <i>chmod</i> command multiple times to change the permissions on files and directories.<br />
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
