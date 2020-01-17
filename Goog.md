https://leetcode.com/discuss/interview-experience/421341/Google-or-L5-or-Nov-2019
https://leetcode.com/discuss/interview-experience/303008/Google-or-L4L5-or-Mountain-View-Reject


Round 3
Data Structure Design + Coding
Implement a transactional iterator for a blob of data which is loaded into memory from a 1TB file. The maximum memory for holding the data is in the order of 100 MBs. Let's say you are already given a structure where you have a chunk of data held in memory but you have to design an iterator for that structure which supports following APIs-

public boolean hasNext() - returns true if there's another blob of data to read
public Object next() - returns the contents of the next blob of data
public void commit() - Commits or creates a checkpoint for all the data until that given memory block.
public void rollback() - Rolls back from the current state to the last commited/checkpointed state
The problem definition was very vague and I had to clarify to figure out what exactly was required to be done.

Round 4
System Design
Design a system to handle aggegration of stats for various entities like users, docs, ads and present those real time stats on a user dashboard. How would you reduce latency ? How would you scale the system ? What are the different trade offs in your design ? How would you make it fault tolerant ?

Round 5
Coding

Given a 2-D grid with bombs placed at various coordinates and diffusers placed at another set of coordinates. Multiple bombs could exist at the same coodinate in the 2-D space but diffusers would be unique per coordinate. Using any distance criteria like manhattan distance. The number of diffusers could be less than the number of bombs in which case some bombs might be left unassigned to diffuse.

Find the assignment of diffusers to bombs. (Similar to campus bikes leetcode problem but with a slight modification).
If every bomb has a certain "ttl" to diffuse, and each diffuser has a certain capability to diffuse a bomb in x amounts of time. Find an assignment such that maximum bombs could be diffused in the fastest way. It could be the case that a diffuser assigned to a bomb difuses it and can select another bomb to diffuse it within it's ttl and capability.
Example - Bomb1 should be diffused in 2 seconds while diffuser1 takes 3 seconds to diffuse a bomb. Thus diffuser1 cannot be assigned to Bomb1. While if diffuser2 takes 1 second to diffuse a bomb, he can be assigned to diffuse Bomb1. Here since diffuser2 saved 1 second in diffusing Bomb1, diffuser2 can be assigned to another Bomb having a ttl of more than 1 second.
Example: Bombs : [[1,0,2], [1,1,1], [2,1,3]] Diffusers: [[2,0,3] , [ 1,-1,1]]
Bombs are present at coordinates (1,0) with a ttl of 2 seconds , (1,1) with ttl of 1 second, (2,1) with ttl of 3 seconds.
Diffusers are present at (2,0) with diffusing capability of 3 seconds and at (1,-1) with diffusing capability of 1 second.
Since ttl of bomb3 is 3 seconds, we can assign any of the diffusers to diffuse it but we want to diffuse max number of bombs in fastest possible fashion. That means, you want to assign a diffuser with least diffusing capability max number of times possible and the one with highest diffusing capability to only those bombs where the diffuser with lesser diffusing capability has already been assigned. Hence you would want to assign diffuser at (1,-1) to bomb at (1,0) and then at (1,1). While the diffuser at (2,0) gets assigned to bomb at (2,1). Total time taken in this situation to diffuse would be 1+1+3 = 5 seconds. (Sort of a greedy approach)
