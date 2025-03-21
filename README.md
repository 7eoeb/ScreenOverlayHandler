# ScreenOverlayHandler

I’ve made a ModuleScript that you can use to make a screen overlay and have a function happen in the background. I figured since I probably wasn’t going to use it, that I’d share it here for anyone to use for free. The :Create() function of the ModuleScript takes in a function that is executed after the screen is completely covered. This is good for things like teleportations and cutscenes. There is also a textLabel that is made which can display input text (inputting text is optional). If you don’t input a function, it wont error and the text and all will still run. But why would you not input a function-- that is the entire point of this model: to cover up the screen while stuff happens in the background.

It's also cool that in the script that you calling it from (LocalScript), you can input a function within a function and set that fucntion as the function to be executed and it stills works! 
