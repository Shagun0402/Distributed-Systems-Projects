Instructions:
I have created two files namely Daemon2 and Process2 where Daemon2 act as a server and Process2 acts as a client which sends and receives messages.
I have created a Synchronization thread that deals with synchronization of messages and communication between the 3 clients. 
Also, SendMessage() and ReceiveMessage() is used to practically depict the request for critical section in a Lamport’s Algorithm.
Again, as mentioned in project deliverables, this code handles only 3 nodes/clients.

Learning Outcome:
Lamport’s Algorithm
This algorithm is used to order the events in a distributed system environment. It also helps in practically ordering events of a process by creating minimum amount of overheads.
i.	It pushes its own request along with others that are ordered by timestamps in its queue.
ii.	It then sends request to every node.
iii.	It then waits for replies from all the nodes.
iv.	After receiving all replies from other nodes, If its own request is at the head of its queues then it enters the critical section. 
v.	When the process exits the critical section, it sends the release message to every other node.
vi.	After receiving a request for critical section by another node, the node pushes the request into its own queue that is again ordered by timestamps and it replies with its own timestamp message.
vii.	After receiving the release request, it removes the corresponding release message from its own queue.
viii.	If its own request is at head of queue even after receiving all the replies are received from other nodes, then we enter critical section.
This process goes on until the messages for request for critical section is received from various nodes.

According to the deliverables mentioned in the project, we are supposed to represent totally ordered multicasting of messages between n-nodes. 
Here, we assume that this project is limited to creating only 3 nodes.
