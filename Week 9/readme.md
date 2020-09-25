# Week 9
Unfortunately this week I wasn’t able to make it to class but I have started working on my final project. What have I come up with so far? Well this is a lot harder to start than I imagined but now that I have started it gets easier and easier, that is until I hit another roadblock. Anyways I have uploaded the current progress here and I will talk about what progress I’ve made and what challenges I have overcome/faced.

* Loading multiple songs and having the mouse press pick a random song
	* The initial problem was that I couldn’t get it to pick a random song, it worked with a single song but as soon as I added two more it would only play one. Eventually I figured this out by putting all the songs in an array and having the random element on the array, so each mouse press will pick a random song from the array.
* Getting the draw function to only work on a mouse press
	* So I spent an incredibly long time on this and went through multiple processes before I finally got it to work. I wanted the draw function (the bit that actually draws the generative artwork) to only turn on when the mouse was pressed and the song started playing, and on that I wanted it to stop when the mouse pressed again just like the song did. I tried putting all the draw functions into another function but that didn’t work. I tried making the draw function turn on and off through a button but that didn’t work. Eventually after some research I found out that the draw function cannot be called upon like a normal function, it either loops or it doesn’t. So I fixed this by making the function that controls the mouse press either loop or unloop the draw based on if it was already running or not.
* Having the rectangle move based on the volume
	* This one was a bit tricky. I wanted the rectangle to move from the bottom to the top of the screen in a constant fashion but I wanted it to move along the x-axis based on the volume of the song. It wasn’t hard to extract the volume but it was hard to implement it into drawing the rectangle. I first tried using the map element and remapping what the volume gave me (since it gives it in a number between 0 and 1) and turning it into a pixel value somewhere on the screen. I gave up doing this and instead made x and y coordinate values update and added a multiplication of volume to the x coordinate. This is actually better because now I can change how much it’s multiplied by and change how intense the volume change is.