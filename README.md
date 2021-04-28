# ChatBlocks Counter by Ellenary
## README
ChatBlocks Counter is a ChatBlock that adds a command to count swears (or other items) using Instafluff's ChatBlocks. It can count single items, multiple items, and even subtract items using one command. There is an additional optional command to check the counter without adding to it. It looks scary if you're not a programmer, but I promise it's really not that bad! I'm not a programmer and I made it (with the help of many lovely people mentioned in the thank you portion of this readme!)
## Example Files
### Basic Counter
ellenary_counter_basic.cbs shows a basic counter. 
### Multiple Commands, One Counter
ellenary_multiple_commands_one_counter.cbs shows how to use multiple commands for one counter.
### Multiple Counters
ellenary_multiple_counters.cbs shows how to use chatblocks to create multiple counters.
## IMPORTANT: INITIAL SET UP
Create your storage bin and put its URL in the "counterBinURL" block area. I made my bin at https://www.npoint.io/ 
You take the npoint.io/docs/string-of-letters-and-numbers and put the the letters and numbers at the end of https://api.npoint.io/ 

Keep that link secret for only you and trusted mods to keep people from deleting it.

### COMMON SET UP BUGS
If you don't put in a bin then it won't work. If it's locked then it won't work. If it's private then it won't work. It needs to be public so that ChatBlocks has access to editing it for you. This is what makes your counter vulnerable to being hacked / deleted, so keep your bin private to only you and trusted mods! 
### SET UP CUSTOMIZATION
The counterNumericURL bin is locked so that it can't be broken/deleted. If you change the numeric bin to something lighter or more robust, that's up to you! The default is set to 100 since there have been instances where Twitch was being wonky so we streamed on Discord and needed to add 90 swears at the end of a stream. I don't think with average swear usage you'll need more than 1-15, really.
## IMPORTANT: WHAT GOES IN YOUR BIN
>{"counter":0}

Put the above into your bin. "counter" is the name of the JSON key and 0 is the count.
### CUSTOMIZATION
#### Multiple Counters
If you have multiple counters, then you need to make a key for each of them in your bin. E.g. {"counter":0,"counter2":0,"counter3":0}

#### **COMMON BUG: NON-NUMERIC**
If you put quotations around 0 it won't read it as a number. 
#### **COMMON BUG: IT WON'T COUNT BEYOND NaN!**
*"We've counted NaN things!"* 

If you do not set your bin to 0, then it'll set to null and it won't count. If you already have a counter, then you can set it to what your old counter's total was.
## EXAMPLE USAGE
>**!counter**
>Default command. Adds one item to the total count.
>
>**!counter 0**
Checks the current total count.
>
>**!counter 2**
>Adds 2 to the total count. Can be used for 1-100 with the default locked bin included in the blocks under "counterNumericURL".
>
>**!counter -1**
>Removes one item from the total count using the properties of mathematics so you don't need a separate subtraction function.
>
>**!counter -2**
>Removes 2  from the total count. Can be used for -100 to -1 with the default locked bin included in the blocks under "counterNumericURL".
>
>**!checkcount**
Optional, removable command to check the current total count. You can remove this to use !counter 0 instead. 

## IMPORTANT: Customization
### Editing the Command
It's as simple as changing "counter" to "ah" or "swearjar" or "death" or whatever else you can think of. You don't need to put the ! in front as that will be added by default.
### Editing the Message 
The counter is formatted as "We've counted something " # " time!" in a create text with block. You can edit the text however you'd like. 

#### **COMMON BUG : Weird Word Spacing Issues**
When you edit it, be sure to add a space at the end of the first part before getting the value, and a space at the beginning of the part after getting the value as needed. Without doing that you'll end up with something like: "That's $1for the swear jar" instead of "That's $1 for the swear jar", "Jakey has gotten in trouble2times!" instead of "Jakey has gotten in trouble 2 times!" 
### Changing the Command's Permissions

The first "if" statement in the counter allows for the command to be used only by the broadcaster and moderators. This prevents the counter from being artificially inflated by trolls or ne'er-do-wells. You can remove it, change it to include VIPs, or even make it so the broadcaster can't change the count! 

I recommend keeping the permissions as-is because there have been instances of people using the counter to troll the streamer in the past. 

### !checkcount Command
Really lame command name, but it's a small block that allows you to check the command without adding to it. It's entirely optional. You can move the "say" blocks to a function to save on space if that makes it easier for you to use. If your blocks get overly large they can start to lag.
### Customizing !checkcount
The check counter command can be modified to !check and check the chat message for the name of the command you want so that you have one command to check all the counters you may be using.
#### Example
In Micromuffin's channel, she can check how many times she's died in a game as well as many times she's sworn by using the !check command. You'd simply use if/else statements to "check if chat message contains ah", "check if chat message contains death", etc to set it up this way. Then you would have it get the value at the corresponding key for each counter. e.g. **!check ah** will check the "ah" key for her swear jar, **!check death** will check the "death" key for her death counter.
### Multiple Commands Can Point to One Counter

You can use multiple commands that point to the same counter. You just need to make separate commands that point to the same JSON key. Duplicate the blocks exactly as they are and give them a new command.
#### **COMMON BUG** 
For some reason you cannot put the "guts" of the counter in a function. I have tried removing the permissions to see if that'd help but it doesn't. So if you use multiple commands for one counter then you'll need to repeat those blocks.

#### Example of custom command usage
EverydaygamerM has a Cyrillic command for a mod who frequently switch between English and Russian on their keyboard and might forget to switch back to English before using the command.

## Contact
You can continue to make this block more and more complicated as you wish. Instafluff has made something truly special with ChatBlocks. If you need help, please feel free to ping me **@ellenary#6457** in Instafluff's #chatblocks channel on Discord (Time zone: MST, GMT/UTC-7 year round no DST). Frankly, others there may be able to help you better than I could!
## Thank You
The ChatBlocks Counter has been an ongoing labor of love from August 2020 to April 2021. I would like to say thanks to **Instafluff** for making ChatBlocks, Kari (**Micromuffin**) for inspiring the subtraction feature, Alec (**Gemini_24**) for inspiring condensing the blocks down since the original multiple counter featured hundreds of blocks, Mon (**EverydayGamerM**) for inspiring the counter and its ability to have multiple commands on one counter, **InformaTheMusic** for helping me figure out how to use the JSON blocks and work out initial counter bugs, and **JupiterZky** for inspiring the method that finally worked for counting multiple things. Without them this counter would not exist or have the functionality it does.
