---
layout: post
title:  "Defender: mGBA Game"
date:   2022-4-03 00:00:00
categories: Class-Project C
---

In my computer organization and programming course, for homework we were tasked with designing and creating a Gameboy Advance game using a GBA emulator and C. I chose to create a game that is different from the 1981 Defender arcade game, but similar in plot. The object of the game is to defend the center monument from an advancing enemy that is randomly spawned from either side. The game is won once the player kills (touches/collides with) atleast 10 enemies, but the game can be lost if the monument health reaches zero. This game really taught me a lot about not only game design and refresh rates of screens but also about structs and general C programming.


<h4>  The Game </h4>
<img src="{{'/assets/images/defender-mgba.gif' | relative_url}}" />


The actual underlying source code is a basic state machine of: START, INITPLAY, PLAY, WIN, LOSE. 

    The Start phase consists of drawing the home screen and checking if the player has pressed the select button (Enter Key) to switch to the INITPLAY state

    The InitPlay phase consists of a single cycle where the game background is drawn, the inital player position is initialized, drawn, and saved and then switching to the PLAY state

    The Play phase is the meat of the game where the program first checks for collisions between the enemy and the player and the player and the side of the screen. If there is a collision between the player and the enemy, then the enemy is "killed."
        then, the enemy is checked to see if it is at the monument. If so, it is "killed." Then the logic checks to see if the enemy was killed in this cycle and sets up a new enemy with position and speed to be drawn.
        Finally, the game buttons are checked to see if the knight's x,y coordinates should change. 
        Total kills and health are also checked to see if there should be a change of state to WIN/LOSE.

        Once all the game logic is over, the code waits for a new drawing period to update the enemy image, player image, and kill/health counter text.
    
    The WIN phase is just the undrawing of the previous game text and drawing of a new "You win!" text in the center screen.
    The LOSE phase is just the undrawing of the previous game text and drawing of a new "You lose :(" text in the center screen.

    All phases also check if the backspace button was just pressed, to restart the game at any point in time.


