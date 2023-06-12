<h1><span style="font-size:16px"><span style="font-family:Arial,Helvetica,sans-serif">File Permissions In Linux</span></span></h1>

<h3><span style="font-size:16px"><span style="font-family:Arial,Helvetica,sans-serif">Project Description</span></span></h3>

<p><span style="font-size:14px"><span style="font-family:Arial,Helvetica,sans-serif">You are a security professional at a large organization. You mainly work with their research team. Part of your job is to ensure users on this team are authorized with the appropriate permissions. This helps keep the system secure.&nbsp;</span></span></p>

<p><span style="font-size:14px"><span style="font-family:Arial,Helvetica,sans-serif">Your task is to examine existing permissions on the file system. You&rsquo;ll need to determine if the permissions match the authorization that should be given. If they do not match, you&rsquo;ll need to modify the permissions to authorize the appropriate users and remove any unauthorized access.</span></span></p>

<h3><br />
<span style="font-size:16px"><span style="font-family:Arial,Helvetica,sans-serif">Check File and Directory Details</span></span></h3>

<p><strong><span style="font-size:14px"><span style="font-family:Arial,Helvetica,sans-serif">Check the permissions set for files and subdirectories in the projects directory. Make sure you display all permissions, including hidden files.</span></span></strong></p>

<p><strong><span style="font-size:14px"><span style="font-family:Arial,Helvetica,sans-serif">(Click the Following Link to View Screenshot of the Change)</span></span></strong><br />
<a href="https://www.dropbox.com/s/6crc63ax4m59b5w/Screen%20Shot%201.png?dl=0">https://www.dropbox.com/s/6crc63ax4m59b5w/Screen%20Shot%201.png?dl=0</a></p>

<h3><br />
<span style="font-size:16px"><span style="font-family:Arial,Helvetica,sans-serif">Describe The Permissions String</span></span></h3>

<p><span style="font-size:14px"><span style="font-family:Arial,Helvetica,sans-serif">The 10-character permission string in the example <code>drwxr-xr-x 3 researcher2 research_team 4096 Jun 12 00:24 .</code> represents the permissions assigned to a directory. Each character in the string represents a specific permission or attribute.</span></span></p>

<p><span style="font-size:14px"><span style="font-family:Arial,Helvetica,sans-serif">The first character, <code>d</code>, indicates that the entry is a directory. If it were a regular file, this character would be replaced with a <code>-</code>.</span></span></p>

<p><span style="font-size:14px"><span style="font-family:Arial,Helvetica,sans-serif">The next three characters, <code>rwx</code>, represent the permissions for the owner of the directory. <code>r</code> stands for read permission, <code>w</code> stands for write permission, and <code>x</code> stands for execute permission. In this case, the owner has read, write, and execute permissions.</span></span></p>

<p><span style="font-size:14px"><span style="font-family:Arial,Helvetica,sans-serif">The following three characters, <code>r-x</code>, represent the permissions for the group assigned to the directory. Similar to the owner&#39;s permissions, <code>r</code> stands for read, <code>x</code> stands for execute, but there is no write permission indicated by a <code>-</code>.</span></span></p>

<p><span style="font-size:14px"><span style="font-family:Arial,Helvetica,sans-serif">The last three characters, <code>r-x</code>, represent the permissions for other users or the world. Again, <code>r</code> stands for read, <code>x</code> stands for execute, and there is no write permission indicated.</span></span></p>

<p><span style="font-size:14px"><span style="font-family:Arial,Helvetica,sans-serif">In summary, the 10-character permission string represents the permissions for the directory, indicating who can read, write, and execute the directory.</span></span></p>

<p><span style="font-size:14px"><span style="font-family:Arial,Helvetica,sans-serif">The command I used to check permisisions was <code>ls -l</code> or <code>ls -la</code></span></span></p>

<h3><br />
<span style="font-size:16px"><span style="font-family:Arial,Helvetica,sans-serif">Change File Permissions</span></span></h3>

<p><strong><span style="font-size:14px"><span style="font-family:Arial,Helvetica,sans-serif">The organization does not allow other to have write access to any files. Based on the permissions established in Step 3, identify which file needs to have its permissions modified. Use a Linux command to modify these permissions.</span></span></strong></p>

<p><span style="font-size:14px"><span style="font-family:Arial,Helvetica,sans-serif">The</span>&nbsp;<code>project_k.txt</code>&nbsp;<span style="font-family:Arial,Helvetica,sans-serif">file has write permissions for other users and those permissions should be changed.</span></span></p>

<p><strong><span style="font-size:14px"><span style="font-family:Arial,Helvetica,sans-serif">(Click the Following Link to View Screenshot of the Change)</span></span></strong><br />
<a href="https://www.dropbox.com/s/ziwz835f0nlpsvh/Screen%20Shot%202023-06-11%20at%2010.17.36%20PM.png?dl=0">https://www.dropbox.com/s/ziwz835f0nlpsvh/Screen%20Shot%202023-06-11%20at%2010.17.36%20PM.png?dl=0</a></p>

<h3><br />
<span style="font-family:Arial,Helvetica,sans-serif">Change File Permissions on a Hidden File</span></h3>

<p><strong><span style="font-size:14px"><span style="font-family:Arial,Helvetica,sans-serif">The research team has archived</span></span></strong> <code>.project_x.txt</code><strong>, which is why it&rsquo;s a hidden file. This file should not have write permissions for anyone, but the user and group should be able to read the file. Use a Linux command to assign .project_x.txt the appropriate authorization.</strong></p>

<p><span style="font-family:Arial,Helvetica,sans-serif"><span style="font-size:14px">Both the user and the group have the incorrect write permissions....</span></span></p>

<p><strong><span style="font-size:14px"><span style="font-family:Arial,Helvetica,sans-serif">(Click the Following Link to View Screenshot of the Change)</span></span></strong><br />
<a href="https://www.dropbox.com/s/fox7i5eoz3bmmbx/Screen%20Shot%202023-06-11%20at%2010.33.15%20PM.png?dl=0">https://www.dropbox.com/s/fox7i5eoz3bmmbx/Screen%20Shot%202023-06-11%20at%2010.33.15%20PM.png?dl=0</a></p>

<h3><br />
<span style="font-family:Arial,Helvetica,sans-serif">Change Directory Permissions</span></h3>

<p><span style="font-size:14px"><span style="font-family:Arial,Helvetica,sans-serif">The files and directories in the projects directory belong to the researcher2 user. Only researcher2 should be allowed to access the drafts directory and its contents. Use a Linux command to modify the permissions accordingly.</span></span></p>

<p><span style="font-size:14px"><span style="font-family:Arial,Helvetica,sans-serif">I removed the execute permission for the group from the&nbsp;<code>drafts</code>&nbsp;directory using the following command to complete this step:&nbsp; <code>chmod g-x drafts</code></span></span><br />
<a href="https://www.dropbox.com/s/8sfdwg36yhmx5fw/Screen%20Shot%202023-06-11%20at%2010.39.11%20PM.png?dl=0">https://www.dropbox.com/s/8sfdwg36yhmx5fw/Screen%20Shot%202023-06-11%20at%2010.39.11%20PM.png?dl=0</a></p>

<h3><br />
<span style="font-family:Arial,Helvetica,sans-serif">Summary</span></h3>

<p><span style="font-family:Arial,Helvetica,sans-serif"><span style="font-size:14px">Throughout the tasks, I demonstrated proficiency in managing files and directories using Linux. I successfully checked the details of files and directories, including permissions, using commands like <code>ls</code> and <code>ls -l</code>. I was able to change file permissions using the <code>chmod</code> command, which allowed me to control who can read, write, and execute the files. Additionally, I learned how to change the permissions of hidden files, which are files that start with a dot, using the same <code>chmod</code> command. Furthermore, I acquired the skills to modify directory permissions, enabling me to control access and actions within directories. Overall, I showcased my competence in navigating and managing files and directories, as well as understanding and manipulating their permissions using Linux commands.</span></span></p>

<p>&nbsp;</p>
