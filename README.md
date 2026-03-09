Build and run Instructions:
  Clone the reposiory: git clone https://github.com/JaylanL/Monopoly-Board.git
cd Monopoly-Board

  Compile in the terminal: g++ -std=c++17 monopoly_board_S26_template_v2.cpp -o monopoly_board

  Run: ./monopoly_board
  
  
Data Structures Used:
  To simulate the round like turn based game of Monopoly, a circular linked list was used. 

List of functions:
  addSpace: adds one space to the tail, cannot add any more when there are 40 or more spaces
  addMany: adds spaces until you reach the max amount of spaces (40)
  movePlayer: moves the player by an inputted number of steps. Also keeps track of the number of times the user passess GO.
  getPassGoCount: returns the number of times the user has passed GO
  printFromPlayer: Ouptus the number of spaces inputted by the user from the players space.
  removeByName: Removes the first instance of a Space the user inputs starting from their space and onwards.
  findByColor: Outputs all the spaces and their descripitons with a color inputted by the user
  countSpaces: Outputs the number of spaces on the board.
  clear: Clears all the spaces on the board.

Traversal and Movement Logic: Because we are using a circular linked, we are using a playerNode that can only move from node to node. We cannot instantenously pop into one space due to the non-continuous memory of linked lists. As well, the last space wraps back around to the first space like a ring. GO is detected on the first space of the baord when crossing from the last space on the board to the first.

Board Limit: This monopoly board has a strict limit of 40 spaces. Once there are 40 spaces, you will be rejected from adding any more spaces!
