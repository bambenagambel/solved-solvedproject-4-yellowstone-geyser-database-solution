Download Link: https://assignmentchef.com/product/solved-solvedproject-4-yellowstone-geyser-database-solution
<br>
Before Starting the Project

· Read sections 8.1 – 8.5 about ArrayLists

· Read this entire project description before starting

Learning Objectives

After completing this project, you should be able to:

· use ArrayLists to maintain and process collections of objects

· use for-each loops

· read data from external text files

Yellowstone National Park Geysers

Yellowstone National Park is home to the most geysers in the world. Hundreds of geysers erupt on a regular basis with Old Faithful being the most famous. Thousands of tourists gather during the summer months to watch it erupt about every ninety minutes. Park rangers have recorded geyser names, eruption times and dates for over one hundred years. You will create a database of information recorded in 2010. We simplified and cleaned up the data but there are still over 12,000 entries!

Step 1: Create a New BlueJ Project

Step 2: Download Data File

· Download the “GeyserData.txt” file and save it in the folder that BlueJ created for this new project. There are over 12,000 entries! You will not see the file within BlueJ but you can see it from within the Windows Explorer.

Step 3: Create a class called Eruption (5 pts)

This simple class stores information about a single geyser eruption: month, day and year of the eruption (integers), hour and minute of the eruption (24 hour clock) and the geyser name.

· Provide appropriate names and data types for each of the six instance variables.

· public Eruption (String info) – a constructor that initializes all of the instance variables to appropriate values given a single String. Read the background information about parsing Strings provided later in this document.

· provide get methods for each of the six instance variables.

· provide matching set methods for each instance variable. Although set methods are not used for this project it is good practice to provide them for most classes.

· public String toString( ) – return a formatted String. For example,

Great Fountain on 6/23/2010 at 23:59

· public static void main(String [] args) – thoroughly test each of the methods in this class.

Step 4: Create a class called Geyser (5 pts)

This simple class allows a different perspective of the eruption list. It stores information about an individual geyser and its total number of eruptions.

· Provide appropriate names and data types for the geyser name and number of eruptions.

· public Geyser (String name) – a constructor that initializes the geyser name.

· public void increment () – add one to the number of eruptions.

· public String getName () – return geyser name.

· public int getNumEruptions () – return number of eruptions.

· public static void main(String [] args) – thoroughly test each of the methods in this class.

Step 5: Create a class called GeyserDatabase (40 pts)

Create a class that maintains an unlimited number of geyser eruptions. Use the elegant for-each loop to search the ArrayList.

Class Fields

· Define an instance variable that holds an ArrayList of Eruption. Information is read from a text file.

· Define an instance variable that holds an ArrayList of Geyser. Information is created after reading the eruption data.

Constructor

A constructor is a special method with the same name as the class and generally initializes the fields to appropriate starting values. Refer to section 3.7.

· public GeyserDatabase ( ) – instantiate empty ArrayLists for eruptions and for geysers. No items are inserted yet. This method will be two lines of code.

Mutator Methods

A mutator method performs tasks that may modify class fields. Methods which simply set a field with the parameter value often begin with the prefix ‘set’. Refer to section 3.6.

· public void readGeyserData(String filename) – open the provided filename and read all the data. There are several thousand entries in “GeyserInfo.txt”. A sample solution is provided in the background section later in this document. Also, you will eventually invoke the helper method createGeyserList() but it will not be written until later.

· public void addEruption (Eruption e) – add the eruption to the ArrayList. This method contains one line of code.

Accessor Methods

An accessor method does not modify class fields. The names for these methods, which simply return the current value of a field, often begin with the prefix ‘get’. Refer to section 3.6.

· public ArrayList

· public ArrayList

· public int getNumEruptions ( ) – return the number of items in the eruption ArrayList with one line of code.

· public int getNumEruptions (int m, int d, int y) – this overloaded method has an identical name as the previous method but returns the number of eruptions for the specified day. Note, the correct number could be zero.

· public Eruption getLateNightEruption ( ) – return the latest occurring eruption regardless of day. For example, the latest eruption during the year might occur at 11:30 at night which would be stored as (23:30).

· public ArrayList

· public String findDayWithMostEruptions(int y) – return a String that contains the date with the most eruptions in the requested year. This should work even if the year has no eruptions. Refer to sample results later in this document to see results for 2010 and 2012 as examples.

Hint: invoke countEruptions(m,d,y) for each day of the year. Here is some code to get you started.

for(int m = 1; m&lt;=12; m++){

for(int d=1; d&lt;=31; d++){

int count = getNumEruptions(m,d,y);

// update month. Day and year if new maximum is found

}

}

Step 6: Add methods about Geysers (10 pts)

It is sometime useful to store and view data from a different perspective. We can use the list of eruptions to create a new ArrayList that contains information about each unique geyser. A geyser object, created in step #4, contains the name and number of eruptions.

· Extracting unique geyser names from the eruption list is challenging so we are providing the full method for you. However, you will probably need to adapt it for your variable names. Important: invoke this method at the end of the readGeyserData() after the eruption list has been filled.

private void createGeyserList(){

ArrayList

// create temporary list of unique geyser names

for(Eruption e:eruptions){

if(!nameList.contains(e.getName())){

nameList.add(e.getName());

}

}

// create a list of geysers

for(String s:nameList){

Geyser g = new Geyser(s);

// count number of eruptions for current geyser name

for(Eruption e:eruptions){

if(e.getName().equals(g.getName()))

g.increment();

}

geyserList.add(g);

}

}

· public int getNumGeysers ( ) – return the number of items in the geyser list with one line of code.

· public Geyser findMostActiveGeyser() – search the geyser list and return the geyser with the most eruptions.

· public Geyser findLeastActiveGeyser() – search the geyser list and return the geyser with the fewest eruptions.

Coding Style (10 pts)

Good programming practice includes writing elegant source code for the human reader. Follow the GVSU Java Style Guide.

Sample ResultsResults from the GUI with the text file properly read should yield the following results.Result from selecting menu item Count

12780 eruptions

25 geysersResult of a search by name “pink”

some output removed from this example

Pink Cone on 10/3/2010 at 7:00

Pink Cone on 10/17/2010 at 12:43

Pink Cone on 11/1/2010 at 10:04

Pink Cone on 11/2/2010 at 11:00

Pink Cone on 11/4/2010 at 9:45

Pink Cone on 11/5/2010 at 17:18

37 eruptions for Pink

Result of a search by date “4/20/2010”

25 eruptions on 4/20/2010Result of a search for most active geyser

Most Active Geyser

Old Faithful had 2,447 eruptionsResult of a search for most eruptions in 2012

Day with most eruptions in 2012

no eruptions in 2012

Result of a search for most eruptions in 2010

Day with most eruptions in 2010

118 eruptions on 7/24/2010

Step 7: Software Testing (10 pts)

Software developers must plan from the start that their solution is correct. BlueJ allows you to instantiate objects and invoke individual methods. You can carefully check each method and compare actual results with expected results. However, this gets tedious. Another approach is to write a main method that calls all the other methods.

a) Create a sample text file

You do not know the correct answers for the provided data. Instead, you should create your own small text file with 5-10 eruptions. Use NotePad. TextPad or similar basic text editor and save the file as plain text (.txt). Give careful thought to the eruptions you create to test all of your database methods. Your file should have more eruptions than the following.

1/15/2010,Scott,16:43

1/15/2010,Nancy,6:15

4/15/2010,Scott,20:35

9/1/2010,Scott,12:19b) Create a new class called GeyserTest with a main method.

Testing a class can be done by creating a special program, sometimes known as a testbench, whose job is to thoroughly test the class. The process of creating and running a program that tests a specific class (or “unit”), is known as unit testing. (see section 4.11)

For this project, write a main method in a new class called GeyserTest that instantiates a geyser database and invokes each of the methods with a variety of parameters. Provide multiple if statements to test each method along with error messages as needed. It takes careful consideration to anticipate and test every possibility. This is an incomplete example. Your solution should be longer with at least 12 tests.public static void main(String args[]){

GeyserDatabase db = new GeyserDatabase();// read small data file created just for testing

db.readGeyserData(“mySampleData.txt”);// check number of eruptions and geysers

if(db.getNumEruptions() != 4){

System.out.println(“Error: Number of eruptions should be 4”);

}

if(db.getNumGeysers() != 2){

System.out.println(“Error: Number of geysers should be 2”);

}

// check late night eruption

Eruption e = db.getLateNightEruption();

if(e.getHour() != 20 &amp;&amp; e.getMinute() != 35){

System.out.println(“Error: Latest eruption should be at 20:35”);

}System.out.println(“Scanning complete.”);

}

Step 8: Adapt the provided GeyserGUI class (17 pts)

Now that you have the basic application working within its own class it is time to create a more interesting graphical user interface for the user.

· Download the provided “GeyserGUI.java” and save it in the project folder.

· The central JTextArea, called resultsArea, is provided for you and spans ten rows and five columns to make room for the buttons and textfields.

· Several menu items are created for you.

· The Month label and textfield are provided for you.

Instance Fields

· Define instance variables for a GeyserDatabase object, JTextFields and JButtons as needed to match the sample screenshot (Figure 1).

In GUI Constructor

· instantiate a GeyserDatabase.

db = new GeyserDatabase();

· Define local variables for JLabels. Note, labels can be local variables since they are not accessed from anywhere else in the class.

· Instantiate and display the remaining labels, text fields and buttons to match Figure 1.

· Look for FIX ME comments for clues of what to add.

Figure 1. GUI Screenshot

In actionPerformed ( )

· Add if statements for each of the buttons and menu items. Look for FIX ME comments for clues of what to add. Here are two samples to get you started.

if (e.getSource() == quitItem){

System.exit(1);

}

if(e.getSource() == latestEruption){

Eruption item = db.getLateNightEruption();

resultsArea.setText(“Latest Eruption
” + item.toString());

}

Additional Helper Methods (private)

· private void displayEruptions (ArrayList

rseultsArea.setText(“”);

for(Eruption e : list){

resultsArea.append(“
” + e.getString());

}

Preventing User Errors

Unless you make special preparation, your code will crash if the user does not provide the requested information in each of the text fields depending on the action. You can test the contents of a text field and display an error message if it is empty.

Add code within the actionPerformed() method to test for:

· Max eruptions if no year is provided

· List eruptions if no geyser name is provided

· Number of eruptions if no month, day or year is provided

Here is a sample to get you started:

if(geyser.getText().length() == 0){

JOptionPane.showMessageDialog(this, “Provide a geyser name”);

}else{

// display all eruptions for the requested geyser

}

Step 9: Refactoring (3 pts)

Refactoring is a software development strategy of revising working code to make it more efficient and elegant. When your GUI is complete you may notice the constructor has redundant code for each GUI element. Several redundant statements are needed to create a constraint with an X Y position and other characteristics. A more elegant solution would be to generalize the redundant code in a helper method that can be invoked to position an element. We wrote a helper method called makeConstraints()and provided it at the bottom of GeyserGUI.

· shorten your GUI constructor code by refactoring the placement of each GUI element.Before refactoring

position = new GridBagConstraints();

position.gridx = 0;

position.gridy = 11;

position.gridwidth = 1;

position.gridheight = 1;

position.anchor = GridBagConstraints.LINE_START;

position.insets = new Insets(0,20,0,0);

month = new JTextField(2);

add(month, position);

After refactoring

position = makeConstraints(1,11,1,1,GridBagConstraints.LINE_START);

position.insets = new Insets(0,20,0,0);

month = new JTextField(2);

add(month, position);

Background Information: Parsing Strings

Data can be stored in a long string with values separated by commas or other special symbols. You can write use a Scanner to divide the String into smaller pieces. 1) Instantiate the Scanner with the String to be processed (instead of System.io). 2) indicate which characters will be used for dividers, i.e. delimiters. 3) Use the next() and nextInt() methods to read the data. Consider one line of eruption data that includes a date, geyser name and eruption time. Here is sample code you will need to adapt. It is only reads the first two items.

String info = “1/15/2010,Old Faithful,16:43”;

Scanner scnr = new Scanner(info);

scnr.useDelimiter(“/|,|:”);

int month = scnr.nextInt();

int day = scnr.nextInt();

Background Information: Reading From a Text File

The data file contains actual geyser eruptions at Yellowstone National Park from 2010. A sample line is shown below. Items are separated by commas, slashes and colons. The readGeyserData() method reads one line at a time and passes the text to the Eruption class constructor.

1/15/2010,Old Faithful,16:43

The following method reads from a text data file one line at a time and prints to the screen. The solution is a bit more complex than an example in section 11.5 but similar to Figure 15.4.1 in section 15.4. You will have to modify this code to create Customers and insert into the database.

Sample Code

public void readGeyserData(String filename){

// Attempt to read the complete set of data from a text file

try{

// open the text file and use a Scanner to read the text

File f = new File(filename);

Scanner sc = new Scanner(f);

String text;

// keep reading as long as there is more data

while(sc.hasNext()) {

text = sc.nextLine();

// FIX ME: remove this print statement after method works

System.out.println(text);

// FIX ME: instantiate a new Eruption and add to database

// this should take two lines of code

}

sc.close();

}

catch(IOException e) {

System.out.println(“Failed to read the data file: ” + filename);

}

}

• Source code – a printout of your elegant source code for:

Eruption.java

Geyser.java

GeyserDatabase.java

GeyserGUI.java

· Upload the FOUR .java files on Blackboard.

Learning Objectives

After completing this project, you should be able to:

· use ArrayLists to maintain and process collections of objects

· use for-each loops

· read data from external text files

Yellowstone National Park Geysers

Yellowstone National Park is home to the most geysers in the world. Hundreds of geysers erupt on a regular basis with Old Faithful being the most famous. Thousands of tourists gather during the summer months to watch it erupt about every ninety minutes. Park rangers have recorded geyser names, eruption times and dates for over one hundred years. You will create a database of information recorded in 2010. We simplified and cleaned up the data but there are still over 12,000 entries!Step 1: Create a New BlueJ ProjectStep 2: Download Data File

· Download the “GeyserData.txt” file and save it in the folder that BlueJ created for this new project. There are over 12,000 entries! You will not see the file within BlueJ but you can see it from within the Windows Explorer.

Step 3: Create a class called Eruption (5 pts)

This simple class stores information about a single geyser eruption: month, day and year of the eruption (integers), hour and minute of the eruption (24 hour clock) and the geyser name.

· Provide appropriate names and data types for each of the six instance variables.

· public Eruption (String info) – a constructor that initializes all of the instance variables to appropriate values given a single String. Read the background information about parsing Strings provided later in this document.

· provide get methods for each of the six instance variables.

· provide matching set methods for each instance variable. Although set methods are not used for this project it is good practice to provide them for most classes.

· public String toString( ) – return a formatted String. For example,

Great Fountain on 6/23/2010 at 23:59

· public static void main(String [] args) – thoroughly test each of the methods in this class.

Step 4: Create a class called Geyser (5 pts)

This simple class allows a different perspective of the eruption list. It stores information about an individual geyser and its total number of eruptions.

· Provide appropriate names and data types for the geyser name and number of eruptions.

· public Geyser (String name) – a constructor that initializes the geyser name.

· public void increment () – add one to the number of eruptions.

· public String getName () – return geyser name.

· public int getNumEruptions () – return number of eruptions.

· public static void main(String [] args) – thoroughly test each of the methods in this class.

Step 5: Create a class called GeyserDatabase (40 pts)

Create a class that maintains an unlimited number of geyser eruptions. Use the elegant for-each loop to search the ArrayList.

Class Fields

· Define an instance variable that holds an ArrayList of Eruption. Information is read from a text file.

· Define an instance variable that holds an ArrayList of Geyser. Information is created after reading the eruption data.

Constructor

A constructor is a special method with the same name as the class and generally initializes the fields to appropriate starting values. Refer to section 3.7.

· public GeyserDatabase ( ) – instantiate empty ArrayLists for eruptions and for geysers. No items are inserted yet. This method will be two lines of code.

Mutator Methods

A mutator method performs tasks that may modify class fields. Methods which simply set a field with the parameter value often begin with the prefix ‘set’. Refer to section 3.6.

· public void readGeyserData(String filename) – open the provided filename and read all the data. There are several thousand entries in “GeyserInfo.txt”. A sample solution is provided in the background section later in this document. Also, you will eventually invoke the helper method createGeyserList() but it will not be written until later.

· public void addEruption (Eruption e) – add the eruption to the ArrayList. This method contains one line of code.

Accessor Methods

An accessor method does not modify class fields. The names for these methods, which simply return the current value of a field, often begin with the prefix ‘get’. Refer to section 3.6.

· public ArrayList

· public ArrayList

· public int getNumEruptions ( ) – return the number of items in the eruption ArrayList with one line of code.

· public int getNumEruptions (int m, int d, int y) – this overloaded method has an identical name as the previous method but returns the number of eruptions for the specified day. Note, the correct number could be zero.

· public Eruption getLateNightEruption ( ) – return the latest occurring eruption regardless of day. For example, the latest eruption during the year might occur at 11:30 at night which would be stored as (23:30).

· public ArrayList

· public String findDayWithMostEruptions(int y) – return a String that contains the date with the most eruptions in the requested year. This should work even if the year has no eruptions. Refer to sample results later in this document to see results for 2010 and 2012 as examples.Hint: invoke countEruptions(m,d,y) for each day of the year. Here is some code to get you started.

for(int m = 1; m&lt;=12; m++){

for(int d=1; d&lt;=31; d++){

int count = getNumEruptions(m,d,y);

// update month. Day and year if new maximum is found

}

}

Step 6: Add methods about Geysers (10 pts)

It is sometime useful to store and view data from a different perspective. We can use the list of eruptions to create a new ArrayList that contains information about each unique geyser. A geyser object, created in step #4, contains the name and number of eruptions.

·Extracting unique geyser names from the eruption list is challenging so we are providing the full method for you. However, you will probably need to adapt it for your variable names. Important: invoke this method at the end of the readGeyserData() after the eruption list has been filled.private void createGeyserList(){

ArrayList

// create temporary list of unique geyser names

for(Eruption e:eruptions){

if(!nameList.contains(e.getName())){

nameList.add(e.getName());

}

}

// create a list of geysers

for(String s:nameList){

Geyser g = new Geyser(s);

// count number of eruptions for current geyser name

for(Eruption e:eruptions){

if(e.getName().equals(g.getName()))

g.increment();

}

geyserList.add(g);

}

}

· public int getNumGeysers ( ) – return the number of items in the geyser list with one line of code.

· public Geyser findMostActiveGeyser() – search the geyser list and return the geyser with the most eruptions.

· public Geyser findLeastActiveGeyser() – search the geyser list and return the geyser with the fewest eruptions.

Coding Style (10 pts)

Good programming practice includes writing elegant source code for the human reader. Follow the GVSU Java Style Guide.Sample ResultsResults from the GUI with the text file properly read should yield the following results.Result from selecting menu item Count

12780 eruptions

25 geysersResult of a search by name “pink”

some output removed from this example

Pink Cone on 10/3/2010 at 7:00

Pink Cone on 10/17/2010 at 12:43

Pink Cone on 11/1/2010 at 10:04

Pink Cone on 11/2/2010 at 11:00

Pink Cone on 11/4/2010 at 9:45

Pink Cone on 11/5/2010 at 17:18

37 eruptions for PinkResult of a search by date “4/20/2010”

25 eruptions on 4/20/2010Result of a search for most active geyser

Most Active Geyser

Old Faithful had 2,447 eruptionsResult of a search for most eruptions in 2012

Day with most eruptions in 2012

no eruptions in 2012Result of a search for most eruptions in 2010

Day with most eruptions in 2010

118 eruptions on 7/24/2010

Step 7: Software Testing (10 pts)

Software developers must plan from the start that their solution is correct. BlueJ allows you to instantiate objects and invoke individual methods. You can carefully check each method and compare actual results with expected results. However, this gets tedious. Another approach is to write a main method that calls all the other methods.

a) Create a sample text file

You do not know the correct answers for the provided data. Instead, you should create your own small text file with 5-10 eruptions. Use NotePad. TextPad or similar basic text editor and save the file as plain text (.txt). Give careful thought to the eruptions you create to test all of your database methods. Your file should have more eruptions than the following.

1/15/2010,Scott,16:43

1/15/2010,Nancy,6:15

4/15/2010,Scott,20:35

9/1/2010,Scott,12:19

b) Create a new class called GeyserTest with a main method.

Testing a class can be done by creating a special program, sometimes known as a testbench, whose job is to thoroughly test the class. The process of creating and running a program that tests a specific class (or “unit”), is known as unit testing. (see section 4.11)

For this project, write a main method in a new class called GeyserTest that instantiates a geyser database and invokes each of the methods with a variety of parameters. Provide multiple if statements to test each method along with error messages as needed. It takes careful consideration to anticipate and test every possibility. This is an incomplete example. Your solution should be longer with at least 12 tests.

public static void main(String args[]){

GeyserDatabase db = new GeyserDatabase();// read small data file created just for testing

db.readGeyserData(“mySampleData.txt”);

// check number of eruptions and geysers

if(db.getNumEruptions() != 4){

System.out.println(“Error: Number of eruptions should be 4”);

}

if(db.getNumGeysers() != 2){

System.out.println(“Error: Number of geysers should be 2”);

}// check late night eruption

Eruption e = db.getLateNightEruption();

if(e.getHour() != 20 &amp;&amp; e.getMinute() != 35){

System.out.println(“Error: Latest eruption should be at 20:35”);

}

System.out.println(“Scanning complete.”);

}

Step 8: Adapt the provided GeyserGUI class (17 pts)

Now that you have the basic application working within its own class it is time to create a more interesting graphical user interface for the user.

· Download the provided “GeyserGUI.java” and save it in the project folder.

· The central JTextArea, called resultsArea, is provided for you and spans ten rows and five columns to make room for the buttons and textfields.

· Several menu items are created for you.

· The Month label and textfield are provided for you.

Instance Fields

· Define instance variables for a GeyserDatabase object, JTextFields and JButtons as needed to match the sample screenshot (Figure 1).

In GUI Constructor

· instantiate a GeyserDatabase.

db = new GeyserDatabase();

· Define local variables for JLabels. Note, labels can be local variables since they are not accessed from anywhere else in the class.

· Instantiate and display the remaining labels, text fields and buttons to match Figure 1.

· Look for FIX ME comments for clues of what to add.

Figure 1. GUI Screenshot

In actionPerformed ( )

· Add if statements for each of the buttons and menu items. Look for FIX ME comments for clues of what to add. Here are two samples to get you started.

if (e.getSource() == quitItem){

System.exit(1);

}

if(e.getSource() == latestEruption){

Eruption item = db.getLateNightEruption();

resultsArea.setText(“Latest Eruption
” + item.toString());

}

Additional Helper Methods (private)

· private void displayEruptions (ArrayList rseultsArea.setText(“”);

for(Eruption e : list){

resultsArea.append(“
” + e.getString());

}

Preventing User Errors

Unless you make special preparation, your code will crash if the user does not provide the requested information in each of the text fields depending on the action. You can test the contents of a text field and display an error message if it is empty.

Add code within the actionPerformed() method to test for:

· Max eruptions if no year is provided

· List eruptions if no geyser name is provided

· Number of eruptions if no month, day or year is provided

Here is a sample to get you started:

if(geyser.getText().length() == 0){

JOptionPane.showMessageDialog(this, “Provide a geyser name”);

}else{

// display all eruptions for the requested geyser

}

Step 9: Refactoring (3 pts)

Refactoring is a software development strategy of revising working code to make it more efficient and elegant. When your GUI is complete you may notice the constructor has redundant code for each GUI element. Several redundant statements are needed to create a constraint with an X Y position and other characteristics. A more elegant solution would be to generalize the redundant code in a helper method that can be invoked to position an element. We wrote a helper method called makeConstraints()and provided it at the bottom of GeyserGUI.

· shorten your GUI constructor code by refactoring the placement of each GUI element.

Before refactoring

position = new GridBagConstraints();

position.gridx = 0;

position.gridy = 11;

position.gridwidth = 1;

position.gridheight = 1;

position.anchor = GridBagConstraints.LINE_START;

position.insets = new Insets(0,20,0,0);

month = new JTextField(2);

add(month, position);

After refactoring

position = makeConstraints(1,11,1,1,GridBagConstraints.LINE_START);

position.insets = new Insets(0,20,0,0);

month = new JTextField(2);

add(month, position);

Background Information: Parsing Strings

Data can be stored in a long string with values separated by commas or other special symbols. You can write use a Scanner to divide the String into smaller pieces. 1) Instantiate the Scanner with the String to be processed (instead of System.io). 2) indicate which characters will be used for dividers, i.e. delimiters. 3) Use the next() and nextInt() methods to read the data. Consider one line of eruption data that includes a date, geyser name and eruption time. Here is sample code you will need to adapt. It is only reads the first two items.

String info = “1/15/2010,Old Faithful,16:43”;

Scanner scnr = new Scanner(info);

scnr.useDelimiter(“/|,|:”);

int month = scnr.nextInt();

int day = scnr.nextInt();

Background Information: Reading From a Text File

The data file contains actual geyser eruptions at Yellowstone National Park from 2010. A sample line is shown below. Items are separated by commas, slashes and colons. The readGeyserData() method reads one line at a time and passes the text to the Eruption class constructor.

1/15/2010,Old Faithful,16:43The following method reads from a text data file one line at a time and prints to the screen. The solution is a bit more complex than an example in section 11.5 but similar to Figure 15.4.1 in section 15.4. You will have to modify this code to create Customers and insert into the database.

Sample Code

public void readGeyserData(String filename){

// Attempt to read the complete set of data from a text file

try{

// open the text file and use a Scanner to read the text

File f = new File(filename);

Scanner sc = new Scanner(f);

String text;

// keep reading as long as there is more data

while(sc.hasNext()) {

text = sc.nextLine();

// FIX ME: remove this print statement after method works

System.out.println(text);

// FIX ME: instantiate a new Eruption and add to database

// this should take two lines of code

}

sc.close();

}

catch(IOException e) {

System.out.println(“Failed to read the data file: ” + filename);

}

}

• Source code – a printout of your elegant source code for:

Eruption.java

Geyser.java

GeyserDatabase.java

GeyserGUI.java