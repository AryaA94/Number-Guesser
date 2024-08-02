import random

def get_top_of_range():
    """Get the top of the range from the user"""
    while True:
        try:
            top_of_range = int(input("Type a number larger than 0: "))
            if top_of_range > 0:
                return top_of_range
            else:
                print("Please type a number larger than 0.")
        except ValueError:
            print("Please type a number.")

def game_loop(top_of_range):
    """Play the guessing game"""
    random_number = random.randint(0, top_of_range)
    guesses = 0

    while True:
        guesses += 1
        try:
            user_guess = int(input("Make a guess: "))
        except ValueError:
            print("Please type a number.")
            continue

        if user_guess == random_number:
            print("You got it!")
            break
        elif user_guess > random_number:
            print("You were above the number!")
        else:
            print("You were below the number!")

    print(f"You got it in {guesses} guesses.")

def main():
    top_of_range = get_top_of_range()
    game_loop(top_of_range)

if __name__ == "__main__":
    main()
