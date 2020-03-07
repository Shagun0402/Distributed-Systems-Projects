Implementation Details:
I have created two files namely Daemon1 and Process1 where Daemon1 acts as Master that polls Process1 which acts as a slave. 
As mentioned in the project deliverables, this code handles only 3 nodes/slaves. 
I have implemented Berkeley’s Algorithm by creating a class DaemonThread that ramdomly initialized a count value for the master on which the computation is done and the count is updated for each slave.


Learning Outcome:
1)	Berkeley’s Algorithm
This algorithm is used to synchronize clock in a distributed computing environment where it is assumed that no machine or node has an accurate time source. In Berkeley’s algorithm, the server process is termed as master that is used to periodically poll other slave processes.
Below is the summarization for Berkeley’s Algorithm:
i)	A master is chosen using an election process.
ii)	The chosen master then polls other slaves (i.e. other nodes).
iii)	Slaves then reply with their timestamp to their master.
iv)	Master then computes their local times using round-trip times (RTT) of the messages and then computes the timestamp for each slave and its own.
v)	The master then averages the clock times. Also, the master is used to ignore all the values that it receives that are far outside the values when compared with others.
vi)	The master then sends out the amount (be it positive or negative) that each slave must use to adjust its clock rather than sending the updated current timestamp which is good because it helps in avoiding any uncertainty caused due to round-trip time that takes place at the slave processes.

References:
1)	Berkeley’s Algorithm: http://www2.cs.man.ac.uk/~raym8/comp28112/main/node108.html
2)	Berkeley’s Algorithm: https://en.wikipedia.org/wiki/Berkeley_algorithm
