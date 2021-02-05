# MoviePickerZSH
![Help](https://github.com/ArtiomSu/MoviePickerZSH/blob/main/screenshots/h.png)

MoviePicker is writen in zsh since dealing with colours is alot easier than with bash. You can run it with bash without any issues after changing all the print commands with the appropriate colour codes.

MoviePicker is handy for those who have alot of movies and tv series thrown across multiple hard drives. With MoviePicker they are essentially all in one place, easy to navigate and play movies directly from the script with your choosen media player.

MoviePicker also takes your terminal window size into account so if you want you can use it with a small window but you wont be able to view the help page until you increase your window size to a reasonable amount.

See screenshots bellow to get an idea of what this looks like.

# Config
Open MoviePicker in vim or any other text editor as we will need to change some settings before you can run it.

`VIDEO_PLAYER="smplayer"`

By default this script will use smplayer to open videos you can change this to vlc if you want. You can also supply command line arguements to the player for example to launch vlc with full screen `VIDEO_PLAYER="vlc -f"`

### Configure folders
This array stores all the imediate folders that you can access. You can't set a direct path to a video file here because thats useless.

I have my config setup so that all the top level folders for my movies are at the top then specific trilogies and series that I'm currently watching are a subdirectory inside the main folders.

To setup the config you simply add folders path to the array.

##### Headers
Config supports adding headers to split up the text to add a header just make sure that it starts with a # otherwise it will think its a path to a folder

By default the config looks like this
```
config=(
					"#All Movies"
					"/nas/nfs-8tbhdd/Movies" 
					"/nas/nfs-8tbhdd/Movies/0 New Movies"
					"/nas/nfs-movies/movies" 
					"/nas/nfs-movies/new_movies" 
					"#All Series"
					"/nas/nfs-8tbhdd/Series"  
					"/nas/nfs-movies/series" 
					"/nas/nfs-movies/new_series" 
					"#Series Left to Watch"
					"/nas/nfs-8tbhdd/Series/Altered Carbon/Altered Carbon Season 2 2160p"
					"/nas/nfs-8tbhdd/Series/American_Gods_S03"
					"/nas/nfs-8tbhdd/Series/BatwomanS02"
					"/nas/nfs-8tbhdd/Series/Better Call Saul"
					"/nas/nfs-8tbhdd/Series/His Dark Materials S02"
					"/nas/nfs-8tbhdd/Series/The Mandalorian S02"
					"/nas/nfs-8tbhdd/Series/The Chilling Adventrures of Sabrina S04"
					"/nas/nfs-8tbhdd/Series/Watchmen Season 1"
					"#Movie Trilogies.."
					"/nas/nfs-8tbhdd/Movies/The Matrix Trilogy (1999-2003)"
					"/nas/nfs-8tbhdd/Movies/The Resident Evil"
					"/nas/nfs-movies/movies/Alien.movies"
					"/nas/nfs-movies/movies/Harry Potters"
					"/nas/nfs-movies/movies/Pirates Of The Caribbean"
					"/nas/nfs-movies/movies/terminators"
					"/nas/nfs-movies/movies/underworld 4 movies"
				)
```
And with the default theme it looks like this
![Main](https://github.com/ArtiomSu/MoviePickerZSH/blob/main/screenshots/1.png)

### Configure file types
You will need to add your movie file extensions if you are using something other than the most common ones
```
file_types=(
		"mkv"
		"mp4"
		"avi"
		"mov"
		"ogg"
		"webm"
		"m4v"
		"mpv"
		"mpg"
		"mpeg"
		"m4p"
	)
```
This allows the script to run faster by just parsing the extention instead of looking at the metadata of the file. It is used to theming so folders and movies are styled differently and also it is used to check if the file you selected is a movie when opening it in your media player since you wouldn't want to open a .txt for example.

### Override default theme
Under the file_types array you will see a bunch of commented out themes. You can choose a theme with command like arguements `MoviePicker -t amber` for example but if you want to set the amber theme as default you can uncomment the line under amber like so
```
#Amber
c_b=208; c_f=202; c_h=234; c_v=39; c_h_l=166; c_h_c=232; c_s_l1=209; c_s_l2=210; c_s_l3=211; c_s_c1=237; c_s_c2=236; c_s_c3=235; c_current_path=3; c_s_option=88; c_hist_l=212; c_hist_c=235; c_e_l=88; c_e_c=184; c_p_l=208; c_p_c=235; c_p_m=209
```

# Arguements
### "h" "-h" "--help"
Shows the help page
### "t" "-t" "--theme"
Allows you to change the theme. If you supply nothing after t it will list all the available themes `MoviePicker -t`.

To pick a theme write the name of the theme like so `MoviePicker -t amber` for example to set the amber there. See screenshots bellow for a preview of all the themes.

# Adding your own theme
Close to the top of the file you will find a bunch of commented out themes copy 
```
#default template leave commented
#c_b=39; c_f=118; c_h=234; c_v=208; c_h_l=69; c_h_c=56; c_s_l1=38; c_s_l2=37; c_s_l3=36; c_s_c1=26; c_s_c2=25; c_s_c3=24; c_current_path=28; c_s_option=91; c_hist_l=35; c_hist_c=23; c_e_l=88; c_e_c=184; c_p_l=24; c_p_c=163; c_p_m=10
```
and paste it into the theme_chooser function you can see how the other themes are setup so just do the same. The default theme is expanded with a description of what each colour variable changes so you can use that as a guide. You can find the default theme at around line 37.

# Screenshots
![1](https://github.com/ArtiomSu/MoviePickerZSH/blob/main/screenshots/1.png)
![2](https://github.com/ArtiomSu/MoviePickerZSH/blob/main/screenshots/2.png)
![3](https://github.com/ArtiomSu/MoviePickerZSH/blob/main/screenshots/3.png)
![4](https://github.com/ArtiomSu/MoviePickerZSH/blob/main/screenshots/4.png)
![5](https://github.com/ArtiomSu/MoviePickerZSH/blob/main/screenshots/5.png)
![6](https://github.com/ArtiomSu/MoviePickerZSH/blob/main/screenshots/6.png)
![7](https://github.com/ArtiomSu/MoviePickerZSH/blob/main/screenshots/7.png)
![8](https://github.com/ArtiomSu/MoviePickerZSH/blob/main/screenshots/8.png)
![9](https://github.com/ArtiomSu/MoviePickerZSH/blob/main/screenshots/9.png)
![10](https://github.com/ArtiomSu/MoviePickerZSH/blob/main/screenshots/10.png)
![11](https://github.com/ArtiomSu/MoviePickerZSH/blob/main/screenshots/11.png)
![12](https://github.com/ArtiomSu/MoviePickerZSH/blob/main/screenshots/12.png)
![13](https://github.com/ArtiomSu/MoviePickerZSH/blob/main/screenshots/13.png)









