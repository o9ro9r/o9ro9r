- 👋 Hi, I’m @o9ro9r
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
o9ro9r/o9ro9r is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
# List of words for the game
word_list = ['python', 'hangman', 'challenge', 'programming', 'developer','cow','cat',school','book', 'ocean', 'keyboard', 'sunflower', 'journey', 'cloud', 'adventure', 'music', 'technology', 'library', 'mountain', 'robot', 'painting', 'campfire', 'garden', 'puzzle', 'festival', 'city', 'camera', 'exploration', 'history', 'chocolate', 'exercise', 'language', 'star', 'art', 'travel', 'game', 'coffee', 'mystery', 'nature', 'mountain', 'space', 'innovation', 'dinosaur', 'moon', 'skyscraper','river', 'computer', 'holiday', 'painting', 'volcano', 'planet', 'harbor', 'skateboard', 'novel', 'bridge', 'forest', 'pyramid', 'jungle', 'instrument', 'astronomy', 'island', 'rocket', 'sunset', 'photo', 'balloon', 'robot', 'dolphin', 'village', 'skateboard', 'oasis', 'lighthouse', 'beach', 'labyrinth', 'rainbow', 'treasure', 'canyon', 'meadow', 'safari', 'museum', 'sea', 'windmill']

def choose_word():
    """Randomly choose a word from the word list."""
    return random.choice(word_list)

def display_word(word, guessed_letters):
    """Display the current state of the word with guessed letters."""
    return ' '.join(letter if letter in guessed_letters else '_' for letter in word)

def play_hangman():
    """Main function to play Hangman."""
    word = choose_word()
    guessed_letters = set()
    attempts_left = 6  # Number of allowed incorrect guesses

    print("Welcome to Hangman!")
    print("Try to guess the word.")

    while attempts_left > 0:
        print(display_word(word, guessed_letters))
        guess = input("Guess a letter: ").lower()

        if len(guess) != 1 or not guess.isalpha():
            print("Please enter a single letter.")
            continue

        if guess in guessed_letters:
            print("You already guessed that letter.")
            continue

        if guess in word:
            guessed_letters.add(guess)
            print("Good guess!")
        else:
            attempts_left -= 1
            print(f"Incorrect guess. Attempts left: {attempts_left}")

        if all(letter in guessed_letters for letter in word):
            print(f"Congratulations! You guessed the word: {word}")
           break
    else:
        print(f"Sorry, you ran out of attempts. The word was: {word}")

if __name__ == "__main__":
    play_hangman()
