# Developer Log (DEVLOG.md)
## Monopoly Board Simulator (Spring 2026)

Minimum **6 entries** required.

Each entry must document learning and reasoning. Fabricated bugs are not expected.

---

## Allowed Entry Types
Each entry may be one of the following:

1) **Bug Fix Entry**
- The issue encountered.
- Error messages or symptoms.
- Attempts made.
- Final resolution.

2) **Edge Case / Testing Entry**
- A failure discovered through testing.
- The specific input/state that caused it.
- The change you made to handle it correctly.

3) **Engineering Decision Entry (up to 2 allowed)**
- A design decision you made.
- An alternative approach you considered.
- Why you chose one approach over another (tradeoffs).

---

### Entry 1
**Date:** 2026-03-08  
**Entry Type:** Engineering Decision Entry
**Task worked on:**  Creating the Board in main()
**Issue or decision:**  I had trouble deciding how I wanted to program the spaces of the monopoloy board.
**Error message / symptom (if applicable):**   N/A
**What I tried:**  I considered creating a separate file that would copntian the spaces so that my main code will look a lot prettier.
**Fix / resolution (or final decision):**  I just decdied to hard code all of my spaces and added the descritions found in a typical original monopoly board. While the code may look harder to read, it was easier to see the desciripitions all in one file.
**Commit(s):**  Added Monopoly spaces to main

---

### Entry 2
**Date:** 2026-03-08  
**Entry Type:** Engineering Decision Entry
**Task worked on:** Deciding how many characters could play on the Monopoly Board. 
**Issue or decision:**  I was deciding based on the original monopoly board how users were able to pick their figures. This allowed for the monopoly board to have multiople users at the same time to move throughout the board. However, what I found trouble with was if the user wanted to adjust the board, how would that affect the various players on the board. If spaces were dleeted on the board, how would we account for the various playerNodes or if they were sharing a node. 
**Error message / symptom (if applicable):**  N/A
**What I tried:**  I tried to create various nodes naming them shoe, trash, and hat to see if I could try to find a way to make the monopoly game multiplier rather than single player. But I still had trouble with how editing the board would ulitmately affect the expereince of users.
**Fix / resolution (or final decision):**  I decided to just continue opting to a single player monopoly game to have the user traverse through the board by themselves. That way it was easier to teast the various funcitons in this programming assignment. 
**Commit(s):**  Finished movePlayer, ensured thatempty list hare handled and passGo is accounted for

---

### Entry 3
**Date:** 2026-03-08  
**Entry Type:** Bug Fix 
**Task worked on:**  Issues with printFromPlayer function
**Issue or decision:**  printing memory addresses instead of the space data
**Error message / symptom (if applicable):**  When outputting the spaces of where the playerNode was at, it kept printing the mmeory address..
**What I tried:**  I tried cout the currentNode that the player was on. I was confused because I though that the * symbol indicated that I was looking for the memory address. I tried comparing the printing of with and without a * for the spaces.
**Fix / resolution (or final decision):**  I realized that these were template classes and required for me to associated "data" with the node to output the actual data I am expectinf from the nodes.
**Commit(s):**  Implemented printFromPlayer that handles empty lists

---

### Entry 4
**Date:** 2026-03-08  
**Entry Type:**  Edge Case 
**Task worked on:**  removeByName
**Issue or decision:** After removing the only node in a single linked list, I was confused of what had happened to headNode, tailNode, and playerNode.
**Error message / symptom (if applicable):**  I tried outputting th eheadNode, tailNode, and playerNode after deleting them but still received an error. I was still confused on what happened to them.
**What I tried:**  I tried to look online for the behaviors of nodes after deleting and not cleanly dealing with where they are now pointing. I learned that they are called dangling pointers that point ot the same memory address where their node had been deleted. So they aren't really pointing to anything useful.
**Fix / resolution (or final decision):** What I saw was a good practice was to set headNode, tailNode, and playerNode as null pointers. 
**Commit(s):**  Integrated Advance Option A (Level 1): removeByName

---

### Entry 5
**Date:** 2026-03-08
**Entry Type:** Bug Fix 
**Task worked on:**  Implemented test case correctly for removeByName()
**Issue or decision:**  The problem I was facing was that the test case that I was trying to remove from the monopoly board kept showing up even after I deleted it. I had a test case of removeByName("Baltic Avenue") that kept appearing after being deleted.
**Error message / symptom (if applicable):**  No crashes, just "Baltic Avenue" Space kept appearing after I deleted it.
**What I tried:**  I tried chekcing if removeByName() was the issue and tested throuhg print statements of mock linked lists to see if it was just the funciton not removing something. It was removing correclty. 
**Fix / resolution (or final decision):**  I noticed that my test case was occuring after the game was being played and tested. That meant that the display was happening before I even tested it. I moved the funciton test to the beginning of the game.
**Commit(s):**  Integrated Advance Option A (Level 1): removeByName

---

### Entry 6
**Date:** 2026-03-08  
**Entry Type:** Edge Case 
**Task worked on:**  countSpaces
**Issue or decision:**  The number of nodes I counted were less than the actual number of nodes in the board
**Error message / symptom (if applicable):**  When I was printing the numebr of spaces in my test cases, I was receiving 31 than my expected spaces of 32.
**What I tried:**  I tried to switch the order of when the nodes were code in my while loop.
**Fix / resolution (or final decision):**  I needed to add one more to the node counter after the while loop because I i was itterating to the tail and I didn't account that I didn't update the node counter at tail.
**Commit(s):**  Implemented countSpaces with O(n) time complexity. Also, adjusted exampoles to show findByColor
