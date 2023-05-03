Download Link: https://assignmentchef.com/product/solved-cs342-operating-systems-project-4-disk-scheduling
<br>
You will do this project individually. You have to program in C and Linux. You are recommended to use the following distribution of Linux: <strong>Ubuntu 16.04 – 64 bit</strong>.




<h1>Part A: Processes [80 points]</h1>

<em><u>Objective</u></em><em>: Practice mass storage, C programming, statistics knowledge.  </em>

<em> </em>

In this project, you will write a program (diskschedule.c) that implements the following disk scheduling algorithms.  a) FCFS;    b) SSTF;   c) SCAN;   d) C-SCAN;    e) LOOK;    f) C-LOOK.

Your program will service a disk with 5000 cylinders numbered 0 to 4999.  It will service 1000 requests according to each of the algorithms listed above. The program will be passed the initial position of the disk head (as a parameter on the command line) and report the total amount of head movement required by each algorithm. The workload (requests) will be given in two ways: 1) will be randomly  generated in your program;  2) will be read from an input file. Which one to use will be specified at the command line.  The program will be invoked as follows:




<strong>diskschedule</strong> &lt;headpos&gt; &lt;inputfile&gt;




The name of the program will be <strong>diskschedule</strong>. &lt;headpos&gt; is the initial head position. Assume the initial direction (when required) is always towards right (to bigger cylinder numbers).  If &lt;inputfile&gt; is not given, then the requests will be generated randomly. The format of the input file (ascii text file) is given in the example below. Each line is for a different request. A line contains a request number and a cylinder number.




<ul>

 <li>4000</li>

 <li>2000</li>

 <li>4500</li>

 <li>1450</li>

 <li>6534</li>

</ul>

…

1000 452




An example invocation of the program can be:




diskschedule 1230 in.txt




The output file be in the following example format:




FCFS: 15000

SSTF: 15000

SCAN: 15000

1          C-SCAN: 15000

LOOK: 15000

C-LOOK: 15000




<h1>Part B: Experiments [20 points]</h1>

<em><u>Objective</u></em><em>: Practice designing and conducting experiments and applying knowledge and skills acquired in the Probability and Statistics course.  </em>




Run the program 100 different times with random input (random requests and random initial head position). At the end, for each algorithm, find out the <em>average</em> total movement and <em>standard</em> <em>deviation</em> of the total movement. Report the results in a table.




<h1>Submission</h1>

Put all your files into a project directory named with your ID (one of the IDs of team members),  tar the directory (using <strong>tar xvf</strong>), zip it (using <strong>gzip</strong>) and upload it to Moodle.  For example, a student with ID 20140013 will create a directory named 20140013, will put the files there, tar and gzip the directory and  upload the file. The uploaded file will be  20140013.tar.gz. Include a <strong>README.txt</strong> file as part of your upload. It will have the name and ID of the student, at least. Include also a <strong>Makefile</strong> to compile your program. We want to type just <strong>make</strong> and obtain the executables.  Do not forget to put your report  (PDF form) into your project directory.




<h1>Additional Information and Clarifications</h1>

<ul>

 <li>Additional clarifications can be posted in piazza or on the course website besides project specification.</li>

 <li>All requests arrive at the same time; time 0.</li>

 <li>LOOK and C-LOOK algorithms behave as follows when given head position is outside of the lowest and highest value range of requests. For example for a request list 98,183,37,122,14,124,65,67, if the head position starts at 190 or 2,   it is outside if request interval. In such a case, just start outside the  interval and then never go outside again.  For the above example, in LOOK,   if we  started at 2: go to 14, then 37, …;  if we started at 190: go to 183, then to 124, … (this is what we would do if we had started on 183 as well – change direction immediately).  In C-LOOK, go in the initial direction always. In this case (according to project spec), that means we need to go to 14, if we start at 190.  If we start at 2,  we need to go to 14, again.</li>

 <li>In LOOK algorithms, while not serving requests in a direction, count that movement as well in total head movement .</li>

 <li>Stop when the last request is served. You don’t need to move the head any further.</li>

</ul>

2