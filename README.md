import random

def number_guessing_game():  # Fixed the function name typo
    print("WELCOME TO NUMBER GUESSING GAME!!")
    print("I am thinking the number between (1 to 100)")
    secret_number = random.randint(1, 100)  # Fixed typo 'secert_number' to 'secret_number'
    attempts = 0 
    
    while True:
        user = input("MAKE A GUESS:   ")
        
        if user.lower() == 'exit':
            print("You want to exit from the game, so the number was:", secret_number)  # Fixed typo and changed 'your number was'
            break
        if not user.isdigit():
            print("Enter a valid number!!")
            continue
        
        user_converted_integer = int(user)  # Convert user input to integer
        attempts += 1
        
        # Check if the user guess is correct or not
        if user_converted_integer > secret_number:  # Compare the converted integer
            print("IS TOO high")
        elif user_converted_integer < secret_number:
            print("IS TOO Low")
        else:
            print(f"Congratulations! You guessed the correct number: {secret_number}")
            print(f"You guessed the number in {attempts} attempts.")
            break  # Exit after the correct guess

# Run the game
number_guessing_game()  # Added parentheses to call the function
