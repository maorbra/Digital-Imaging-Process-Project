# Digital-Imaging-Process-Project

**The King of Bounces Game**

The popular ball game soccer is widespread. When children spend most of their time on soccer fields worldwid. One way to improve in the game is by enhancing ball control skills by bouncing ball. Many children find it difficult to count bounces simultaneously while performing them. Therefore, we created a competition that encourages players to improve dramatically in the bouncing game while making the counting accessible to the user in the most convenient way.

The King of Bounces competition works as follows: First, the player enters their full name into the system, and after launching, they bounce the ball until they are disqualified. Disqualification is defined as one of the following three possibilities:

a. The ball falls to the floor.
b. The ball goes out of the game boundaries (camera's field of view).
c. The player touches the ball with their hand.

The number of bounces is counted automatically, and when the player is disqualified in one of the ways described above, the algorithm disqualifies the player, displays the number of bounces achieved, describes the reason for disqualification, and shows their position in the table relative to other participants.
_________________________________________________________________________________________________

In this project we will use **CV2** package to split the video to frames for easier analyze and to analyze objects in the game and delay between frames , **PyGame** package to create the User experience , **numpy** to analyze each frame as matrix with 3 (with color) or 2 (without color) dimension and kernel filters , **time** package to control time in the game , **sys** package to end python after the player disqualified , **Math** for matematical operations , **pandas** and **pandastable** for score table in the game and organization of it , **tkinter** to create gui for the game controller.
