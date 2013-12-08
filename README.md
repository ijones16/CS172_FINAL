CS172_FINAL
===========

RPG game for final project

Program notes

1 - 	editing any of the descriptions for the different areas,can be accessed under the Implementation.cpp file.
	Under each of the prepRoom() functions, the description is defined when the room object is declared.

2 - 	Fights can be edited and you can also edit the stats of the player and the monsters.  The values
	for the player are declared at the beginning of the Driver.cpp file.  Changing the max health of the player would be done by
	changing a line of code in the Player::Heal(int amount) function because this function checks to see if the player's health
	has gone over 100, and will reset it to 100 if so.
	The stats for the monsters are also under the prepRoom() functions in the Implemntation.cpp file.

3 -	The major elements of subclassing are with the Player and various Item classes.
	The major elements of polymorphism are declaring Item pointers and creating new Item subclass objects.
		- This can be found in the prepRoom() functions where a pointer to an Item object is created dynamically.
	The major vector elements are with the player's inventory vector, and each room's enemies and loot vector.
		-this can be found in the vector of pointers to item objects that functions as the players inventory
		-this can be seen specifically in the combatroom class where a vector of pointers to enemy organism objects and a vector of
		pointers to Item objects are memeber variables of the combat room class.

4 - 	expanding on any of the fights like adding more enemies can be done by declaring a new enemy in the appropriate
	prepRoom() function and adding to the enemies list.  Adding items would require declaring a new subclass of Item.

5 - 	The lacking features of the program were a functional purpose for the race property of the player, and an implementation of a speed
	statistic. If we had more time we could have had a high speed say, allow you to drink a potion and attack in the same turn.But
	this type of feature would complicate combat significantly and unforunately we didn't have enough time.

6 - 	the only errors are entering a non-integer value as a choice in one of the menus. The reason for the one header file is because
	each base class uses an instance of at least one of the other base classes.

7 -	the main driver of the program initializes neccessary elements for the player object, defines a dynamic player object, defines the 
	different areas of the game with each room object, and most importantly uses if statements and switch statements paired with while 
	loops and for loops to control the flow of the game for the player.

8 -	The hardest part was figuring out how to get the player object and the enemy objects to interact. The room class was created for this
	sole purpose and served as a medium in which the player object can interact with enemy and item objects that live in their respective 
	vectors which are in fact member variables of the combatroom class object. Methods combat() and lootRoom() allow for the player object 
	to fight enemy objects and pick up items in the room, thus solving the problem of how to get the player object to interact with Item 
	and Organism objects.

9-	The cool factor of our game is how the dynamically created player object can interact with each room object via the combat() and 
	lootRoom() methods. The combat() method takes a pointer to a player and manages the attacks for each organism in the room, player and
	enemy. Updates health accordingly and also checks for deaths, the returns true if the player has survived combat. 
	Another cool factor is how the preproom() room methods define all the fields for each room object out in main, thus allowing for the 
	dynamically created player to be able to interact with each room and proceed through the gameplay.
	
A few notes on playing

1 - 	If you want to wield a new weapon you find (always recommended) you need to go to Use Item and select the weapon.  This will
	permanently increase your strength value.

2 - 	We highly recommend using the defense potion before entering the final room - just a suggestion :)

