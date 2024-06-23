# Rock-Paper-Scissor-Game
import random

def get_user_choice():
    while True:
        print("\nRock, Paper, Scissors")
        print("Enter your choice:")
        print("1. Rock")
        print("2. Paper")
        print("3. Scissors")
        choice = input("Enter number (1-3): ")
        if choice in ['1', '2', '3']:
            return {'1': 'rock', '2': 'paper', '3': 'scissors'}[choice]
        else:
            print("Invalid input! Please enter a number between 1 and 3.")

def get_computer_choice():
    choices = ['rock', 'paper', 'scissors']
    return random.choice(choices)

def determine_winner(user_choice, computer_choice):
    print(f"\nYou chose: {user_choice}")
    print(f"Computer chose: {computer_choice}")

    if user_choice == computer_choice:
        return "It's a tie!"
    elif (user_choice == 'rock' and computer_choice == 'scissors') or \
         (user_choice == 'paper' and computer_choice == 'rock') or \
         (user_choice == 'scissors' and computer_choice == 'paper'):
        return "You win!"
    else:
        return "Computer wins!"

def play_game():
    print("Welcome to Rock, Paper, Scissors!")

    while True:
        user_choice = get_user_choice()
        computer_choice = get_computer_choice()

        result = determine_winner(user_choice, computer_choice)
        print(result)

        play_again = input("\nDo you want to play again? (yes/no): ").lower()
        if play_again != 'yes':
            print("\nThanks for playing!")
            break

# Start the game
play_game()
