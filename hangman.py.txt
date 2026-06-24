import random

# Categories and words
content = {
    "electronics": ["phone", "speaker", "fan"],
    "fruits": ["apple", "banana", "orange"],
    "computer": ["compiler", "python", "code"]
}

# Display categories
print("1. Electronics")
print("2. Fruits")
print("3. Computer")

choice = int(input("Enter your choice (1-3): "))

if choice == 1:
    category = "electronics"
elif choice == 2:
    category = "fruits"
elif choice == 3:
    category = "computer"
else:
    print("Invalid choice")
    exit()

# Select a random word
word = random.choice(content[category])

# Create blanks
display = ["_"] * len(word)

lives = 5

while lives > 0 and "_" in display:
    print("\nWord:", " ".join(display))
    guess = input("Enter a letter: ").lower()

    if guess in word:
        for i in range(len(word)):
            if word[i] == guess:
                display[i] = guess
        print("Correct!")
    else:
        lives -= 1
        print("Wrong! Lives left:", lives)

# Final result
if "_" not in display:
    print("\nCongratulations! You won.")
    print("Word =", word)
else:
    print("\nYou lose.")
    print("Correct word =", word)
