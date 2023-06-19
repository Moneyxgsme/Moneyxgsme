import random

def roll_dice():
    return random.randint(1, 6)

def play_game():
    print("Welcome to Roll the Dice!")
    print("You have 100 credits.")
    
    credits = 100
    
    while credits > 0:
        print("Place your bet (minimum 1 credit):")
        bet = int(input())
        
        if bet < 1 or bet > credits:
            print("Invalid bet. Please try again.")
            continue
        
        print("Rolling the dice...")
        dice_value = roll_dice()
        print("You rolled a", dice_value)
        
        if dice_value == 6:
            winnings = bet * 5
            print("Congratulations! You win", winnings, "credits!")
        else:
            print("Sorry, you lose.")
            winnings = -bet
        
        credits += winnings
        print("Your current balance:", credits, "credits\n")
    
    print("Game over. You are out of credits.")

play_game()
