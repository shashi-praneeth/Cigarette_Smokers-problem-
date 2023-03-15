# Cigarette_Smokers-problem-

 In this cigarette smokers problem there are three smokers , one Agent. Agent acts like an Operating System and manages the resources.
 
 For making a cigarette  a smoker requires three ingredients , tobacco , matches and paper. A smoker can only make a cigarette and smoke if he/she has all the three ingredients with them. There will be three smokers will be sitting around a table each with an infinite supply of one of the ingredients . A non smoking Agent seperately , will be providing i.e will keep randomly two of the ingredients on the table.The smoker who has the third ingredient should remove the two items from the table,and using them (along with their own ingredient) to make a cigarette, which they smoke for a while. Once the smoker has finished his cigarette, the agent places two new random ingredients on the table. This process continues forever.
 
For a generalized n smokers problem their will be n ingredients and n-1 items will kept on the table.
 
#Approach for generalised n smokers:

First create n threads for each smoker. And also a thread for the Agent.I defined two functions semwait and semsignal which works as V and P operations.

I used two functions to create and join threads.

pthread_create() - is a function used to create threads.
It requires four parameters: 
pthread_create(pthread_t *thread, const pthread_attr_t *attr, void *(*start_routine) (void *), void *arg);


pthread_join(): is also a function that shall suspend execution of the calling thread until the target thread terminates, unless the target thread has already terminated.
 pthread_join(pthread_t thread, void **value_ptr);
 
 
 I defined an array of n ingredients with initial value 0 in all . And a variable agentsem and smoke_complete which acts as semaphores  for signalling to agent to provide ingredients and signal that smoke is complete.
 
Two void pointer functions for smoker and agent.

Basically the approach is that,
the smoker with the ingredient which is not present on the tabke should pick up all the items . so remaining smokers shoul wait untill this smoker pickups all items and make the cigarette and signal the agent to again keep the items on the table.
so in the array of ingredients , the ingredient which is not present on table is set to 1.
And the smoker with this index takes all the items and smoke and again that ingredient is set to 0 .



 

 
 
 
