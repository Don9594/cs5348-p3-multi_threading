# cs5348-p3-multi_threading

**Seeking Tutor Problem**
The computer science department runs a mentoring center (csmc) to help undergraduate students with their programming assignments. The lab has a coordinator and several tutors to assist the students. The waiting area of the center has several chairs. Initially, all the chairs are empty. The coordinator is waiting for the students to arrive. The tutors are either waiting for the coordinator to notify that there are students waiting or they are busy tutoring. The tutoring area is separate from the waiting area.
A student while programming for his project, decides to go to csmc to get help from a tutor. After arriving at the center, the student sits in an empty chair in the waiting area and waits to be called for tutoring. If no chairs are available, the student will go back to programming and come back to the center later. Once a student arrives, the coordinator queues the student based on the student’s priority (details on the priority discussed below), and then the coordinator notifies an idle tutor. A tutor, once woken up, finds the student with the highest priority and begins tutoring. A tutor after helping a student, waits for the next student. A student, after receiving help from a tutor goes back to programming.
The priority of a student is based on the number of times the student has visited the tutoring center. A student visiting the center for the first time gets the highest priority. In general, a student visiting for the ith time has a priority higher than the priority of the student visiting for the kth time for any k > i. If two students have the same priority, then the student who came first has a higher priority.
  
Using POSIX threads, mutex locks, and semaphores implement a solution that synchronizes the activities of the coordinator, tutors, and the students. Some hints to implement this project are provided later in the description.
The total number of students, the number of tutors, the number of chairs, and the number of times a student seeks a tutor’s help are passed as command line arguments as shown below (csmc is the name of the executable):
     csmc #students #tutors #chairs #help
     csmc 10 3 4 5
     csmc 2000 10 20 4
Once a student thread takes the required number of helps from the tutors, it should terminate. Once all the student threads are terminated, the tutor threads, the coordinator thread, and the main program should be terminated.
