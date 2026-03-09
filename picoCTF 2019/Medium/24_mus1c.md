# mus1c

### Description:

I wrote you a `song`. Put it in the picoCTF{} flag format.
Hint: Do you think you can master rockstar?

### Commands / Steps:

```bash
# Step 1: Download the file.
wget [filelink]

# Step 2: We can see that the file is in rockstar programming language, so let's translate it then find the flag.
# Lyrics and Translations are under the notes section.
# We can also use "https://codewithrockstar.com/online" to translate into code.

# Step 3: As an output, we got the below after the translation.
# 114
# 114
# 114
# 111
# 99
# 107
# 110
# 114
# 110
# 48
# 49
# 49
# 51
# 114
# These look like ASCII Codes. So, I put these into cyberchef and used the operation, "From Decimal". Then we get the flag.
```

### Flag:

> picoCTF{rrrocknrn0113r}

### Notes / Tips

- **Rockstar language**: Esoteric programming language that looks like song lyrics
- **Variable assignment**: `[variable] is [word]` assigns letter count of `[word]` to `[variable]`
- **Online interpreter**: Use codewithrockstar.com/online for easy translation and execution
- **ASCII conversion**: Output numbers often represent ASCII codes - use CyberChef "From Decimal" to convert to text 



### Lyrics
Pico's a CTFFFFFFF
my mind is waitin
It's waitin

Put my mind of Pico into This
my flag is not found
put This into my flag
put my flag into Pico


shout Pico
shout Pico
shout Pico

My song's something
put Pico into This

Knock This down, down, down
put This into CTF

shout CTF
my lyric is nothing
Put This without my song into my lyric
Knock my lyric down, down, down

shout my lyric

Put my lyric into This
Put my song with This into my lyric
Knock my lyric down

shout my lyric

Build my lyric up, up ,up

shout my lyric
shout Pico
shout It

Pico CTF is fun
security is important
Fun is fun
Put security with fun into Pico CTF
Build Fun up
shout fun times Pico CTF
put fun times Pico CTF into my song

build it up

shout it
shout it

build it up, up
shout it
shout Pico

### Translation
Pico = 19
my mind = 6
it = 6

This = my mind * Pico

my flag = This
Pico = my flag

print(Pico)
print(Pico)
print(Pico)

My song = 1
This = Pico

This = This - 3
CTF = This

print(CTF)

my lyric = 0
my lyric = This - my song
my lyric = my lyric - 3

print(my lyric)

my lyric = my lyric + 3  #my lyric+=3

print (my lyric)
print (pico)
print(it)

Pico CTF = 3
security = 9
Fun = 3
Pico CTF = security + Fun
Fun = Fun + 1
print(3543)
my song = 3543

it = it + 1

print(it)
print(it)

it = it + 1
print(it)
print(Pico)




