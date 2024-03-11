<h1>JustSimplestDB</h1>
<h2>Author: Jakub Aleksander Michalski</h2>
<h2>Author's mail: jakub.michalski.aleksander@gmail.com</h2>
<h3>A python DBMS libary, solving complexity problem of most DBMSes(DataBase Management System), it's simple to learn and use.<br>
But it have a flaw, database file is not ciphered.</h3>
<h2>Documentation:</h2>
<h3><b>FOR YOUR INFORMATION, this libary is still developed and may have some bugs, mail me if you find one!</b></h3>
<h3>INFO ABOUT SETTING UP LIBARY FOR ALPHA USERS!</h3>
<p>To use this libary alpha, download it from github, then put zipfile into your project's directory and unpack it.<br>
Put all unpacked files into project's directory.<br>
Now, make sure your project's file is in the same directory as unpacked libary files.<br>
</p>
<h3>How to import and initialize JustSimplestDB?</h3>
<p>If you wanna initialize JustSimplestDB, you need to create an instance.</p>
<p>Instance is occurence of object with specific values, like <code>x = Human("John", "Doe")</code> and <code>y = Human("Joanna", "Doe")</code>, <br>
both are Human class occurence, but what make them different, is given values to them.<br>
That's what make them object instance.<br>
Object is a variable assigned to class with specific values, class is like blueprint, but instance of class is implemented blueprint, which is object.</p>
<p>Now, because you know what is instance, create variable in your project.py file, assigned to <code>JustSimplestDB.Instance(filename)</code>.<br>
Filename placeholder is filename(MUST BE A STRING WITHOUT EXTENTION), that'll be used to read ".txt" file or create "database_filename.py" file,<br>
program automatically adds needed extention to this files, that's the reason why you DON'T put filename with any extention.<br>
<br>
For example, you want to read data from "workers.txt", you create variable,<br>
example: <code>db = JustSimplestDB.Instance("workers") # db stands for database</code>.<br>
Now, on created variable you perform a method called <code>db.read_it_like_db()</code> without arguments.<br>
Method <code>db.read_it_like_db()</code>(database equivalent: <code>db.read_db()</code>) is method converting found content in ".txt" file into database-like format(IF IT EXISTS) and returning it into assigned variable, for performing read-only operations.<br>
<br>
<code>import JustSimplestDB
db = JustSimplestDB.Instance("workers")
workers_txt_to_db = db.read_it_like_db()
</code>
<br>
<br>
You can't actually modify this list or original ".txt" file using provided methods, but what you can do, is adding into braces "do_save_as_db=True".<br>
This is gonna convert ".txt" file into database-like format AND save it as JustSimplestDB-database format.<br>
<code>import JustSimplestDB
db = JustSimplestDB.Instance("workers", do_save_as_db=True) # creates database file based on data in .txt file.
</code>
<br>
That's gonna create database, on which you can perform CRUD operations(Create Read Update Delete), database file is called "database_filename.py".<br>
</p>
<h3>JustSimplestDB Shell</h3>
JustSimplestDB shell is program allowing you to perform database operations directly, without writing python script.<br>
Libary automatically creates <code>shell_filename.py</code> when you run your project's script with JustSimplestDB instance.<br>
I would recommend to create standalone database file using this shell, just to don't write excess code which you will must to delete or create try-except block for it.<br>
EVERY method available in this libary can be performed in this shell.</p>
<h3>Different methods, the same functionality.</h3>
<p>".txt" format have slightly different method naming than ".py".<br>
Splitted group of methods is caused by the fact, that first group of method is dedicated to ".txt" file, caused of them READ-ONLY,<br>
and the second group of methods is dedicated to perform CRUD operations on database file.<br>
This means, that naming method for both method group is different, for example, group of "get_" methods have both "get_txt_method_name" and "get_db_method_name" methods.<br>
Every method containing "db" in their names is dedicated to perform operation on database file, likewise ".txt" files.<br>
All ".txt" methods have their equivalent in database methods,<br>
it doesn't work likewise ".txt", because them are READ-ONLY files for this libary.
</p>

<h3>Accessing to database instance attributes.</h3>
<p>If for some reason your program needs to know about database file existence or txt existence,<br>
or when you will need to check if database is new, just use this vars:
<br>
<br>
<code>db.is_txt_exists # checks ".txt: file existence
db.is_db_exists # checks database file existence
db.is_new_db # checks if created database where even used
</code>
<br>
<br>
</p>

<h3>JustSimplestDB keys.</h3>
<p>Short info, each record in database file or database-like list have numerical id, which is unchangable.<br>
Keys can have spaces in their names, but they can't contain TABs, and provided key can't be "id" name.<br>
If for some reason you will have to reasign ids for all record, you can use method called <code>db.reindex_database()</code>.<br>
This method assigns new id for each record, starting from 0.
</p>

<h3>Creating independent database.</h3>
<p>To create standalone database,<br>
you can use method <code>db.create_standalone_db(keys) # which is gonna raise error if database file exists</code>.<br>
Into keys placeholder you provide ALL keys for database(must be a string), separated by ","(comma), example:
<br>
<br>
<code>import JustSimplestDB
db = JustSimplestDB.Instance("workers")
# this is gonna create database_workers.py, if this file exists, libary will raise JustSimplestDBAccessDenied error.
db.create_standalone_db("name", "surname", "job position")
</code>
<br>
<br>
</p>
