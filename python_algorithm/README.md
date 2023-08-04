<h2><span style="font-size:11pt"><span style="font-family:Arial,sans-serif"><span style="color:#000000"><strong>Algorithm for File Updates in Python</strong></span></span></span></h2>

<p>&nbsp;</p>

<p><span style="font-size:11pt"><span style="font-family:Arial,sans-serif"><span style="color:#000000"><strong>Project description</strong></span></span></span><br />
<span style="font-size:12pt"><span style="font-family:Roboto,sans-serif"><span style="color:#374151"><span style="background-color:#f7f7f8">In this assignment, my task was to develop a new algorithm that efficiently processes a file containing IP addresses authorized to access restricted content. The algorithm should remove addresses that no longer have access as well as&nbsp; ensuring optimal security and resource management. In doing this,&nbsp; I hope to enhance access control mechanisms and streamline the process of maintaining up-to-date records of authorized entities.</span></span></span></span></p>

<p>&nbsp;</p>

<p><span style="font-size:11pt"><span style="font-family:Arial,sans-serif"><span style="color:#000000"><strong>Open the file that contains the allow list:</strong></span></span></span></p>

<code> #Assign `import_file` to the name of the file 
import_file = "data/allow_list.txt"
#Assign `remove_list` to a list of IP addresses that are no longer allowed to access restricted information. 
remove_list = ["192.168.97.225", "192.168.158.170", "192.168.201.40", "192.168.58.57"]
#Display `import_file`
print(import_file)
#Display `remove_list`
print(remove_list) </code>

<p><span style="font-size:11pt"><span style="font-family:Arial,sans-serif"><span style="color:#000000"><strong>Read the file contents</strong></span></span></span></p>

<code># Assign `import_file` to the name of the file 
import_file = "data/allow_list.txt"
#Assign `remove_list` to a list of IP addresses that are no longer allowed to access restricted information. 
remove_list = ["192.168.97.225", "192.168.158.170", "192.168.201.40", "192.168.58.57"]
#Build `with` statement to read in the initial contents of the file
with open(import_file, "r") as file:
    #Use `.read()` to read the imported file and store it in a variable named `ip_addresses`
    ip_addresses = file.read()
#Display `ip_addresses`
print(ip_addresses)</code>

<p><span style="font-size:11pt"><span style="font-family:Arial,sans-serif"><span style="color:#000000"><strong>Convert the string into a list</strong></span></span></span></p>
<code>#Assign `import_file` to the name of the file 
import_file = "data/allow_list.txt"
#Assign `remove_list` to a list of IP addresses that are no longer allowed to access restricted information. 
remove_list = ["192.168.97.225", "192.168.158.170", "192.168.201.40", "192.168.58.57"]
#Build `with` statement to read in the initial contents of the file
with open(import_file, "r") as file:
    #Use `.read()` to read the imported file and store it in a variable named `ip_addresses`
    ip_addresses = file.read()
#Use `.split()` to convert `ip_addresses` from a string to a list
ip_addresses = ip_addresses.split()
#Display `ip_addresses`
print(ip_addresses)   
</code>
<br>
<p><span style="font-size:11pt"><span style="font-family:Arial,sans-serif"><span style="color:#000000"><strong>Iterate through the remove list</strong></span></span></span></p>
<code>#Assign `import_file` to the name of the file
import_file = "data/allow_list.txt"
#Assign `remove_list` to a list of IP addresses that are no longer allowed to access restricted information.
remove_list = ['192.168.97.225', '192.168.158.170', '192.168.201.40', '192.168.58.57']
#Build `with` statement to read in the initial contents of the file
with open(import_file, "r") as file:
    #Use `.read()` to read the imported file and store it in a variable named `ip_addresses`
    ip_addresses = file.read()
#Use `.split()` to convert `ip_addresses` from a string to a list
ip_addresses = ip_addresses.split()
#Build iterative statement
#Name loop variable `element`
#Loop through `remove_list`
for element in remove_list:
    # Create conditional statement to evaluate if `element` is in `ip_addresses`
    if element in ip_addresses:
        # use the `.remove()` method to remove

        # elements from `ip_addresses`
        ip_addresses.remove(element)
#Display `ip_addresses`
print(ip_addresses)
</code>

<p><span style="font-size:11pt"><span style="font-family:Arial,sans-serif"><span style="color:#000000"><strong>Remove IP addresses that are on the remove list</strong></span></span></span></p>
<code>#Define a function named `update_file` that takes in two parameters: `import_file` and `remove_list`
#and combines the steps you've written in this lab leading up to this
def update_file(import_file, remove_list):
    #Build `with` statement to read in the initial contents of the file
    with open(import_file, "r") as file:
        #Use `.read()` to read the imported file and store it in a variable named `ip_addresses`
        ip_addresses = file.read()
    #Use `.split()` to convert `ip_addresses` from a string to a list
    ip_addresses = ip_addresses.split()
    #Build iterative statement
    #Name loop variable `element`
    #Loop through `remove_list`
    for element in remove_list:
        # Create conditional statement to evaluate if `element` is in `ip_addresses`
        if element in ip_addresses:
            #use the `.remove()` method to remove
            #elements from `ip_addresses`
            ip_addresses.remove(element)
    #Convert `ip_addresses` back to a string so that it can be written into the text file
    ip_addresses = "\n".join(ip_addresses)
    #Build `with` statement to rewrite the original file
    with open(import_file, "w") as file:
        #Rewrite the file, replacing its contents with `ip_addresses`
        file.write(ip_addresses)
</code>
<br>
<p><span style="font-size:11pt"><span style="font-family:Arial,sans-serif"><span style="color:#000000"><strong>Update the file with the revised list of IP addresses</strong></span></span></span></p>
<code>#Define a function named `update_file` that takes in two parameters: `import_file` and `remove_list`
#and combines the steps you've written in this lab leading up to this
def update_file(import_file, remove_list):
    #Build `with` statement to read in the initial contents of the file
    with open(import_file, "r") as file:
        #Use `.read()` to read the imported file and store it in a variable named `ip_addresses`
        ip_addresses = file.read()
    #Use `.split()` to convert `ip_addresses` from a string to a list
    ip_addresses = ip_addresses.split()
    #Build iterative statement
    #Name loop variable `element`
    #Loop through `remove_list`
    for element in remove_list:
        #Create conditional statement to evaluate if `element` is in `ip_addresses`
        if element in ip_addresses:
            #use the `.remove()` method to remove
            #elements from `ip_addresses`
            ip_addresses.remove(element)
    #Convert `ip_addresses` back to a string so that it can be written into the text file
    ip_addresses = "\n".join(ip_addresses)
    #Build `with` statement to rewrite the original file
    with open(import_file, "w") as file:
        #Rewrite the file, replacing its contents with `ip_addresses`
        file.write(ip_addresses)
#Call `update_file()` and pass in "allow_list.txt" and a list of IP addresses to be removed
update_file("data/allow_list.txt", ["192.168.25.60", "192.168.90.124", "192.168.60.153"])
#Build `with` statement to read in the updated file
with open("data/allow_list.txt", "r") as file:
    #Read in the updated file and store the contents in `text`
    text = file.read()
#Display the contents of `text`
print(text) 
</code>
<br>
<p><span style="font-size:11pt"><span style="font-family:Arial,sans-serif"><span style="color:#000000"><strong>Summary</strong></span></span></span></p>

<ul>
	<li style="list-style-type:disc"><span style="font-size:12pt"><span style="font-family:Roboto,sans-serif"><span style="color:#374151">In Python, we have special tools to work with text files easily.</span></span></span></li>
	<li style="list-style-type:disc"><span style="font-size:12pt"><span style="font-family:Roboto,sans-serif"><span style="color:#374151">The &quot;with&quot; statement helps us handle files more efficiently.</span></span></span></li>
	<li style="list-style-type:disc"><span style="font-size:12pt"><span style="font-family:Roboto,sans-serif"><span style="color:#374151">To read a file, we use the &quot;open()&quot; function, and we say if we want to read or write the file.</span></span></span></li>
	<li style="list-style-type:disc"><span style="font-size:12pt"><span style="font-family:Roboto,sans-serif"><span style="color:#374151">We can read the contents of a file using the &quot;.read()&quot; method.</span></span></span></li>
	<li style="list-style-type:disc"><span style="font-size:12pt"><span style="font-family:Roboto,sans-serif"><span style="color:#374151">To separate a sentence into a list of words, we can use the &quot;.split()&quot; method.</span></span></span></li>
	<li style="list-style-type:disc"><span style="font-size:12pt"><span style="font-family:Roboto,sans-serif"><span style="color:#374151">With a &quot;for&quot; loop, we can go through each item in a list one by one.</span></span></span></li>
	<li style="list-style-type:disc"><span style="font-size:12pt"><span style="font-family:Roboto,sans-serif"><span style="color:#374151">We can check if something is in a list using a &quot;if&quot; statement.</span></span></span></li>
	<li style="list-style-type:disc"><span style="font-size:12pt"><span style="font-family:Roboto,sans-serif"><span style="color:#374151">Python lets us compare what&#39;s in a file with the items in a list.</span></span></span></li>
	<li style="list-style-type:disc"><span style="font-size:12pt"><span style="font-family:Roboto,sans-serif"><span style="color:#374151">We can create special sets of instructions called algorithms to solve problems in Python. We put those instructions inside functions that perform specific tasks.</span></span></span></li>
</ul>
