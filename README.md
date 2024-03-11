<h1>JustSimplestDB</h1>
<h2>Author: Jakub Aleksander Michalski</h2>
<h3>A python DBMS libary, solving complexity problem of other DBMS(DataBase Management System), it's simple to learn and use.<br>
But it have a flaw, database file is not ciphered.</h3>
<h2>Documentation:</h2>
<h3>How to import and initialize JustSimplestDB?</h3>
<p>If you wanna initialize JustSimplestDB, you need to create an instance.</p>
<p>Instance is occurence of object with specific values, like <code>x = Human("John", "Doe")</code> and <code>y = Human("Joanna", "Doe")</code>, <br>
  both are Human class occurence, but what make them different, is given values to them.<br>
  That's what make them object instance, object is occurence of class with specific values.</p>
<p>Now, because you know what is instance, create variable in your .py file, assigned to JustSimplestDB.Instance(filename).<br>
Filename placeholder is filename(MUST TO BE A STRING), that'll be used to read ".txt" file or create "database_filename.py" file,<br>
program automatically adds needed extention to this files, that's the reason why you don't put filename with any extention.<br>
<br>
For example, you want to read data from "workers.txt", you create variable, for example <code> db = JustSimplestDB.Instance("workers")</code>.<br>
Now, on created variable you perform a method called "read_it_like_db()" without arguments.<br>
Method "read_it_like_db()" is method converting found content in ".txt" file into database-like format(IF IT EXISTS) and returning it into assigned variable, for performing read-only operations.<br>
<code>
  import JustSimplestDB
  db = JustSimplestDB.Instance("workers")
  workers_txt_to_db = db.read_it_like_db()
</code>
You can't actually modify this list or original ".txt" file using provided methods, but what you can do, is adding into braces "do_save_as_db=True".<br>
This is gonna convert ".txt" file into database-like format AND save it as JustSimplestDB-database format.
<code>
  import JustSimplestDB
  db = JustSimplestDB.Instance("workers", do_save_as_db=True) # creates database file based on data in .txt file.
</code>
That's gonna create database, on which you can perform CRUD operations(Create Read Update Delete) database file is called "database_filename.py".<br>
</p>

<h3>Different methods, the same functionality.</h3>
<p>".txt" format have slightly different method naming than ".py"<br>
Splited groups of methods is caused by the fact, that first group of method is dedicated to ".txt" file, cause of them READ-ONLY property,<br>
and the second group of methods which is dedicated to perform CRUD operations on database file.
This means, that naming method for both method group is different, for example, group of "get_" methods have both "get_txt_method_name" and "get_db_method_name" methods.<br>
</p>

<h3>Accessing to database instance attributes.</h3>
<p>If for some reason your program needs to know about database file existence or txt existence,<br>
or when you will need to check if database is new, just use this vars:
<code>
  db.is_txt_exists # checks ".txt: file existence
  db.is_db_exists # checks database file existence
  db.is_new_db # checks if created database where even used
</code>
</p>
