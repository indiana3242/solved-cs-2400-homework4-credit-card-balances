Download Link: https://assignmentchef.com/product/solved-cs-2400-homework4-credit-card-balances
<br>
A credit card company keeps track of its customers’ data in a text file. The file is supplied by another department within the company and is generated every day. The generated file includes a customer ID, first name, last name, current balance, and the number of days before the balance is due.  The bank would like to generate reports about the customers stored in this daily file. For example, how many customers have a due date within the next five days?




Write a C++ program to process the data file. Each line in the file contains the following data and each item is separated by at least one space:




&lt;id&gt; &lt;first&gt; &lt;last&gt; &lt;balance&gt; &lt;days to due date&gt;




Examples:

12340 Jimmy Carter 3500.23 4

22345 Richard Nixon 5600.21 0




The program should process the file and output all the customers that match a given criteria into an output file. The criteria will be specified using command line arguments as follows:




<ul>

 <li>&lt;balance&gt; &lt;input file&gt; &lt;output file&gt;</li>

</ul>

All the customers with a balance equal or higher than a specified balance

Example: ./a.out -a 2000 data.txt output.txt




<ul>

 <li>&lt;balance&gt; &lt;input file&gt; &lt;output file&gt;</li>

</ul>

All the customers with a balance equal or below the specified balance

Example: ./a.out -b 2000 data.txt output.txt




-d &lt;number of days&gt; &lt;input file&gt; &lt;output file&gt;

All the customers with a balance due within the number of days specified. Customers with zero balance should not be reported.

Example: ./a.out -d 5 data.txt output.txt




-A &lt;input file&gt; &lt;output file&gt;

Display all the records with the average balance and the total of all balances




All data must be stored in the output file in a nicely formatted table.




Display error messages if any of the following occurs:

<ul>

 <li>The number of options is incorrect (show a usage message)</li>

 <li>The wrong option is used (show a usage message)</li>

 <li>Any of the files fail to open</li>

</ul>




<strong>             </strong>

<strong>Required Functions: </strong>

<ul>

 <li>bool isValidOption(string option); returns true if the option is valid, false otherwise</li>

 <li>void processBalance(string option, double balance,</li>

</ul>

ifstream &amp;inStream, ofstream &amp;outStream);

Reads from the input stream and outputs a report to the output stream based on the option provided (-a, -b).




<ul>

 <li>void processBalanceDue(int numDays,</li>

</ul>

ifstream &amp;inStream, ofstream &amp;outStream);

Reads from the input stream and outputs a report to the output stream (option -d).




<ul>

 <li>void outputSummary(ifstream &amp;inStream, ofstream &amp;outStream);</li>

</ul>

Output all the customer’ data, average balance, and total of all balances (option -A).







<strong>Parsing command line arguments </strong>

<strong> </strong>

In C++ you can input data (strings) into your program on the command line (command line arguments).  You can capture these data by adding two parameters to your main program as follows:

int main (int argc, char *argv[])

argc:  (argument count) number of arguments on the line, including the name of the program argv:  (argument vector) list of c-style strings that represent all the arguments including the name of the program (two dimensional array of characters).




For example, executing the command:

./a.out -A data.txt output.txt

Assigns:

argc = 3

argv[0] will “./a.out” argv[1] will be “-A” argv[2] will be “data.txt” argv[3] will be “output.txt”







To capture the argv data items in your program, just assign them to strings as follows:

string option = argv[1];     string inputFileName = argv[2];     string outputFileName = argv[3]; You can convert a string to a an int or double using the functions stoi and stod (section 8.4 of your textbook). You may have to include the compiler option “-std=c++11”. For example:

double x = stod(“23.45”); // assigns 23.45 to x


