# CraftBoard README

## Control panel:
The control panel should be fairly intuitive.

## Subbar:
If you want to add a new text to display you have to fill both text boxes. Be aware that 
the time interval is defined in seconds.

## Score:
The score can be any integer and empty in case you don't want to display a score.

## Names:
The names will be colorized in the same color you selected. Also they get colorized in the 
text box it's not given that they will be colorized on your scoreboard. This depends on your 
settings.

## Colors:
The colors at the control panel can get changed in the settings. It's not possible to add 
more colors to your control panel. If you want to hide some color buttons on the control
panel since you only need for example 4 colors, just define the other 7 colors as the same 
color as your last color and the tool will automatically hide them.

## Sounds:
Scoreboard and Subbar can have slide-in and slide-out sounds. Right now only .wav is 
supported. Be also carefull that the codec for this file is 'Microsoft Wave Soundformat'.

## Races:
Races can be added in the settings and will automatically be displayed with the description 
text in the race drop down.

## Creating a new design:
If you want to create a new design either overwrite a old design or use the 'Save As' button
in the settings form. The application contains a standard config file named 'default.xml' 
it's recommended to load this one and adjust it to your hearts content and save it as a 
different config file afterwards.

Please be aware that you shouldn't leave any text fields empty such as positions and colors. 
Fields which can be empty are already empty in the default config file, so please don't 
edit the .xml files directly and change values if you don't know what you're doing.

## Image files:
You can select files from everywhere on your harddisk but it's recommended to create an 
own folder in 'images/' for your new layout images in order to keep it nice and clean. 
If you don't do this the application will copy the selected images to the 'images/' folder 
which can turn out to be a little bit nasty if you have many images with the same name. So 
please create your own layout folder and import them afterwards.
It's also strongly recommended to create your images with 72dpi.

## Fonts:
I'm really sorry but this application only supports TrueType Fonts (.ttf) so pay attention 
when you're choosing your font for your text. 

## Text & Image Positions:
Be aware that the background images such as scoreboard image and subbar image are located
on your screens according to your chosen pixel values. The texts and images which are 
located ontop of your scoreboard will have the relative coordinates of your background 
image. Which means if you set the position of your scoreboard to the desktop center and 
want to display text in the top left corner of your scoreboard you will just have to 
pass 0-0 as coordinates. From this it follows that you'll only be able to position 
texts, race images and scores ontop of your scoreboard image and not outside of it.

## Subbar:
Here you don't have to use a background image. If you don't want to use a background image 
just leave this field empty. Be aware that you won't be able to move your subbar by clicking
on movable at the control panel. You'll have to adjust the position in the settings form. 
If you use a background image there won't be a problem with moving your subbar per 
drag & drop.

## Layout - Resolution:
If you created a design specified for a certain screen resolution it is possible to auto 
skew it in case you want to use the same layout on a different screen resolution. It will 
adjust the height and width considering the new screen resolution. If you want to use this
feature just insert the screen resolution your graphics got designed for WIDTHxHEIGHT 
(1280x1024) and enable 'skew'.

## Features - Auto complete:
Every layout can have an own .sqlite database containing all team names or player names. 
Once included it will auto complete your input for 'Player 1' and 'Player 2'. The 
database has to be a sqlite database with the primary key (integer) and of course the 
player name or team name (string/text). The database can update itself at a given interval.
The interval is in days and will update after starting the application.
If you want to you can also add new players/teams by right clicking on the textbox 
containing the new player. You can also delete them by using the delete button.
There is one small bug. If you for example insert two different players like 
Player and PlAyEr only one of them will get shown, so make sure this never happens.

## Features - Database layout:
The database has to have the table 'player' and the two columns id (INT) and 
name (TEXT COLLATE NOCASE)

## Advanced - Color Box:
The color box is the image which will get colorized in the selected color from the control
panel. The color box image has to be a .png file and must only contain the color white 
(#ffffff) and a transparency. The application will colorize this image according to your 
other settings in a new color considering your transparency. 

## Advanced - Colorize Race:
Just like the colorize Image/color box it will colorize your race images in the selected 
colors from the control panel. This image has to be a .png file and must only contain the 
color white (#ffffff) and a transparency. The application will colorize this image according
to your other settings in a new color considering your transparency.
If you don't want your race to get colorized you can just disable it and the application will
use the original images (which of course now can contain any color you want).

Advanced - Gamma:
In some cases it might be useful to adjust the gamma of your overlay. Values between [0,1) 
make your overlay "darker" and values between (1,inf) make your overlay "brighter". If you 
don't want to change the gamma just set it to 1. Although you can change the gamma for 
every color-code it's recommended to give all of them the same gamma value. In most cases 
a value between [0,3;2,5] is recommended.

## Advanced - Brightness
Values between [-255,255] make your overlay darker or brighter. If you don't want to change
the brightness leave it at 0. Although you can change the brightness for R, G, B it's 
recommended to give them the same brightness value. 

## Advanced - Contrast
Values between [0, 255] change your contrast. If you don't want to change it set it 0.
R, G, B should have the same value.

## Advanced - Colorize Nick:
This setting will overwrite the general color settings for player 1 and 2 and will colorize 
them in the selected color from the control panel.

## Layout - Modules:
Here you are able to select all modules which will get loaded after starting the application.
So if you change the selection it will only take affect after restarting the application. If
you want to add new modules to the list just copy the module xml file into the 'modules' 
folder.

## Animations:
You can customize the time the overlay needs to get displayed. A great feature is the stay
duration which will automatically hide the overlay after the given ms. If you don't want 
to us this set it to 0. In order to prevent some bugs please only use values which have 25
as factor (e.g 500, 1500, 725, etc.)

Default - The overlay will just appear
Slide - The overlay will slide in from a given (relative) position to the current position
Fade - The overlay will fade in
Open - The overlay will open from the center to the outside
Roll - The overlay will roll in depending on your x & y values
       -1:0 will let the overlay roll in from left
	   1: 0 will let the overlay roll in from right
	   0:-1 will let the overlay roll in from top
	   0:1 will let the overlay roll in from bottom

## Hotkeys:
Be aware that modules and the standard hotkeys mustn't have the same hotkeys. If that's the 
case the program won't be able to initialize them.

## XSplit Module:
If you want to you can also just display the generated overlay image via XSplit. This way you 
don't have to open the overlay on your side, which means it will just get integrated by 
XSplit.

XSplit -> Add -> Slideshow (it's an optional module) 
-> Add the overlay image (images/layoutfile.png) 
-> let the slideshow loop every x seconds (maybe every 5-10 sec)

It should be obvious that features like slide-in effects won't work this way.

## Modules:
It's not possible to edit or create modules in a comfortable way using the settings interface.
If you want to create your own module or modify an existing one you have to edit the xml file.
Please be careful to not change any variables like <positions> etc. only change the values 
between the brackets <don't change>this text can get changed</don't change>.

<name>Your module name</name> = The name of your module
<path>images/test.png</path>  = The image path of the background .png image (must not be empty)
<title><text></text><title>   = The title text of your application
<title><font></font><title>   = The font name of your title and it's size. Both size and 
                                font name must be given in this way 'Times New Roman; 12pt' 
								without the ''
<title><color></color></title> = Title color in RGB code and ivided with '-' like R-G-B
<title><positions id="x"></positions><title> = X-coordinate of your title
<title><positions id="y"></positions><title> = Y-coordinate of your title
<keys>                   = All of these keys must be set or empty.
  <key id="1">2</key>    = Modifier key 1
  <key id="2">1</key>    = Modifier key 2
  <key id="3">38</key>   = Standard key
</keys>                  = A list of the numbers and their keys can be found below.
<content><source></source></content> = The text, image path or url to display, further 
                                       instructions below.
<content><color></color></content> = General content color in RGB code and divided by '-' 
                                     like R-G-B
<content><font></font><content>    = The font name of your content and it's size. Both 
                                     size and font name must be given in this way 
									 'Times New Roman; 12pt' without the ''
<content><positions id="x"></positions><content> = General X-coordinate of your content
<content><positions id="y"></positions><content> = General Y-coordinate of your content
<layout></layout> = Defines a layout for downloaded content and complex text, will be explained 
                    later.

Source: 
<source>$TXT=This is the text I want to see</source> = Shows some text on your module
<source>$IMG=images/myimage.png</source> = Shows an image ontop of your module
<source>$URL=test.com/x.php?sl=3</source> = Downloads the text from this given php site
<source>$URL=test.com/x.php?sl=$p1&slk=$p2</source> = Downloads the text from this given php site
                                                      and passes the player1 & player2 nick as
                                                      parameter ($p1 & $p2) or ($id1 & $id2) if
                                                      you are using a .sqlite database. In this 
                                                      case it will transmit the primary key
                                                      
Logging - Bugs:
If you ever have problems with the application send your debug.txt file to 
coyle.maguire@googlemail.com and describe your problem so that we can reproduce it. Best thing 
would be if you would just send your whole application folder or at least your layout. Please
be aware that you shouldn't mess around with the config files if you don't have a basic 
understanding of what the values are doing.

Key list:
key id="1" & key id="2" 
It's also possible to give both modifier keys (1, 2) the same key.

0 = Shift
1 = Ctrl
2 = Alt

key id="3"
0 = 0
1 = 1
2 = 2
3 = 3
4 = 4
5 = 5
6 = 6
7 = 7
8 = 8
9 = 9
10 = Num0
11 = Num1
12 = Num2
13 = Num3
14 = Num4
15 = Num5
16 = Num6
17 = Num7
18 = Num8
19 = Num9
20 = A
21 = B
22 = C
23 = D
24 = E
25 = F
26 = G
27 = H
28 = I
29 = J
30 = K
31 = L
32 = M
33 = N
34 = O
35 = P
36 = Q
37 = R
38 = S
39 = T
40 = U
41 = V
42 = W
43 = X
44 = Y
45 = Z
46 = F1
47 = F2
48 = F3
49 = F4
50 = F5
51 = F6
52 = F7
53 = F8
54 = F9
55 = F10
56 = F11
57 = F12
