# 1_wanna_b3_a_r0ck5tar

### Description:

I wrote you another `song`. Put the flag in the picoCTF{} flag format

### Commands / Steps:

```bash
# Step 1: Download the file. 
wget https://challenge-files.picoctf.net/c_fickle_tempest/f2d681a895db4b1eb3801b146ae2ea3ff01656977cf8a93c23e504837629242b/lyrics.txt

# Step 2: Read the contents from the lyrics and convert them to python. The python code under the notes section.

# Step 3: Run the python program and enter 2 inputs when prompted (136, 1970).
# Enter first number: 136
# Keep on rocking!
# Enter second number: 1970
# 66
# 79
# 78
# 74
# 79
# 86
# 73
# Bring on the rock!

# Step 4: Convert the outputs into ASCII.
python3
>>> output = [66, 79, 78, 74, 79, 86, 73]
>>> flag = "picoCTF{" + "".join(chr(c) for c in output) + "}"
>>> print(flag)
```

### Flag:

> picoCTF{BONJOVI}

### Notes / Tips

- Rockstar Language: Esoteric language where lyrics are code
- Poetic Number Literals: Numbers encoded in word lengths (e.g., "a six-string" = 136)
- Keywords:
    - is/was/were = assignment
    - Listen = input
    - Say/Shout/Scream = print (different volumes)
    - without = subtraction
    - nothing = zero/null
    - Break it down = end program
- Two Inputs Required: First must equal "guitar" (136), second must equal "Music" (1970)
- Output: Numbers are ASCII values that spell "BONJOVI"


### Python Program Translation (for reference):


```bash
# Rocknroll is right
# In Rockstar, "right" often means True
Rocknroll = True

# Silence is wrong
# In Rockstar, "wrong" often means False
Silence = False

# A guitar is a six-string
# Poetic number literal: "a six-string"
# Words: "a" (1), "six" (3), "string" (6)
# Concatenated: 136
a_guitar = 136 

# Tommy's been down
# "down" -> 4 letters -> tommy = 4 
Tommy = 4

# Music is a billboard-burning razzmatazz!
# Poetic number literal: "a billboard-burning razzmatazz"
# Words: "a" (1), "billboard" (9), "burning" (7), "razzmatazz" (10->0)
Music = 1970 

# Listen to the music
# "Listen" means input in Rockstar
the_music = int(input("Enter first number: "))

# If the music is a guitar
# Compare input with a_guitar value
if the_music == a_guitar:
    
    # -------------------------------------------------------------------
    # Say "Keep on rocking!"
    # "Say" means print in Rockstar
    print("Keep on rocking!")
    
    # -------------------------------------------------------------------
    # Listen to the rhythm
    # Another input
    the_rhythm = int(input("Enter second number: "))
    
    # -------------------------------------------------------------------
    # If the rhythm without Music is nothing
    # "without" means subtraction, "nothing" means 0
    # So: the_rhythm - Music == 0
    if the_rhythm - Music == 0:
        
        # -------------------------------------------------------------------
        # Tommy is rockin guitar
        # "rockin" -> 6 letters? Actually assignment: tommy = 66
        Tommy = 66
        
        # -------------------------------------------------------------------
        # Shout Tommy!
        # "Shout" means print loudly
        print(Tommy) 
        
        # -------------------------------------------------------------------
        # Music is amazing sensation
        # Poetic number: "amazing sensation"
        # "amazing" (7), "sensation" (9) -> 79
        Music = 79
        
        # -------------------------------------------------------------------
        # Jamming is awesome presence
        # Poetic number: "awesome presence"
        # "awesome" (7), "presence" (8) -> 78
        Jamming = 78
        
        # -------------------------------------------------------------------
        # Scream Music!
        # "Scream" means print very loudly
        print(Music) 
        
        # -------------------------------------------------------------------
        # Scream Jamming!
        print(Jamming)
        
        # -------------------------------------------------------------------
        # Tommy is playing rock
        # "playing rock" -> "playing" (7), "rock" (4) -> 74
        Tommy = 74
        
        # -------------------------------------------------------------------
        # Scream Tommy!
        print(Tommy)  
        
        # -------------------------------------------------------------------
        # They are dazzled audiences
        # "dazzled audiences" -> "dazzled" (7), "audiences" (9) -> 79
        They = 79
        
        # -------------------------------------------------------------------
        # Shout it!
        print(They)  
        
        # -------------------------------------------------------------------
        # Rock is electric heaven
        # "electric heaven" -> "electric" (8), "heaven" (6) -> 86
        Rock = 86
        
        # -------------------------------------------------------------------
        # Scream it!
        print(Rock)  
        
        # -------------------------------------------------------------------
        # Tommy is jukebox god
        # "jukebox god" -> "jukebox" (7), "god" (3) -> 73
        Tommy = 73
        
        # -------------------------------------------------------------------
        # Say it!
        print(Tommy)  
        
        # -------------------------------------------------------------------
        # Break it down
        # "Break it down" means stop/end in Rockstar
        # In Python: break statement or just end
        
        # -------------------------------------------------------------------
        # Shout "Bring on the rock!"
        print("Bring on the rock!")
        
    else:
        # -------------------------------------------------------------------
        # Else Whisper "That ain't it, Chief"
        # "Whisper" means print quietly
        print("That ain't it, Chief")
        
        # -------------------------------------------------------------------
        # Break it down
        # End program
```

