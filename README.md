# Digital-Imaging-Process-Project

**The King of Bounces Game**

The popular ball game soccer is widespread. When children spend most of their time on soccer fields worldwid. One way to improve in the game is by enhancing ball control skills by bouncing ball. Many children find it difficult to count bounces simultaneously while performing them. Therefore, we created a competition that encourages players to improve dramatically in the bouncing game while making the counting accessible to the user in the most convenient way.

The King of Bounces competition works as follows: First, the player enters their full name into the system, and after launching, they bounce the ball until they are disqualified. Disqualification is defined as one of the following three possibilities:

a. The ball falls to the floor.
b. The ball goes out of the game boundaries (camera's field of view).
c. The player touches the ball with their hand.

The number of bounces is counted automatically, and when the player is disqualified in one of the ways described above, the algorithm disqualifies the player, displays the number of bounces achieved, describes the reason for disqualification, and shows their position in the table relative to other participants.
________________________________________________________________________________________________

In this project we will use **CV2** package to split the video to frames for easier analyze and to analyze objects in the game and delay between frames , **PyGame** package to create the User experience , **numpy** to analyze each frame as matrix with 3 (with color) or 2 (without color) dimension and kernel filters , **time** package to control time in the game , **sys** package to end python after the player disqualified , **Math** for matematical operations , **pandas** and **pandastable** for score table in the game and organization of it , **tkinter** to create gui for the game controller.

________________________________________________________________________________________________

**Algoritem for each part of the game**

**detect ball** - We chose to detect the red ball using a color filter matching the ball's color in the HSV palette and then applied morphological masks for noise reduction. Within the `cv2` library, there is a function for finding the center of the ball and drawing a surrounding circle according to adjustable parameters.

**bouncing counter** - In each frame, we calculate the position of the center of the ball and compute the difference in distances traveled by the ball's center over three frames. A bounce is a situation where the ball moves down and then up in reality, but in the image, the top row is the starting index. Therefore, we want the first difference to be positive and then negative. Additionally, a bounce will cause a rapid change in the ball's movement, so we calculate the ball's speed in each axis of the image between two frames, and the difference in speeds will be the directional acceleration. To find the absolute value, we perform a calculation a=sqrt(ax^2+ay^2)

**detect the ball touch the ground** -  The assumption is that the floor does not move because the video camera is fixed in place. Therefore, calculating the differences between frames was a good solution for separating the floor from the player and the ball, which move between frames. Additionally, we defined a line below which we want to detect the floor only. The big problem was to distinguish between the ball touch the floor or the ball just in the low part of the frame. the solution to that was to create a donut that circle the ball we already detect in each frame and to check if the leg of the player is close to the ball and he bounce it.

**detect toching hand** - we use **CSRT** algotitem to follow an object between the frames,we define at the beggining of the game (the host mark the hands of the player) 

