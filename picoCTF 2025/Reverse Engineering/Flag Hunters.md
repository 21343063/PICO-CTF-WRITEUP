# Challenge: Reverse Engineering - Flag Hunters

> Lyrics jump from verses to the refrain kind of like a subroutine call. There's a hidden refrain this program doesn't print by default. Can you get it to print it? There might be something in it for you.

# Step 1 : Observation

First, i try to connect the program with the netcat. the output was a song lyric and it need an input from the user to the variable "crowd". i try to randomly input a word to see what's gonna happen next.

<img width="500" height="489" alt="image" src="https://github.com/user-attachments/assets/4b5a5d05-a2a8-4ee0-90aa-75ab8cc4614a" />

i guess the input i give is saved on the program and then will be repeatedly show in the lyrics. Then, i try to check on the program to see more clues. 

<img width="500" height="307" alt="image" src="https://github.com/user-attachments/assets/33e8053d-3835-4ff1-afa7-4a4d5530bebf" />

as we can see, the flag is already in the secret_intro variable. we just need to show the var to the output. the secret_intro is in the first part of the lyric. but why they skip the first part? 

> reader(song_flag_hunters, '[VERSE1]')

we can find the answer in the last line of the code. Now, how can we access the 0 part of the lyrics?
<img width="500" height="576" alt="image" src="https://github.com/user-attachments/assets/fdc58937-2410-45fc-9fe8-b3f19a35140c" />

in this part of the program, we can see that (line 121-122) there is a RETURN that we can use to go back to the lines we want. 

<img width="500" height="556" alt="image" src="https://github.com/user-attachments/assets/3392f520-f4c5-4b2f-9615-1d16f27b4291" />

dont forget to add the semicolon (;) when using the RETURN because the program wont recognize it if we doesnt use it.

## RESULTS : picoCTF{70637h3r_f0r3v3r_b248b032}

