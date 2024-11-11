import random
def player_input():
 while True:
 try:
 player_run = int(input("Enter your run (1-6): "))
 if player_run in range(1, 7):
 return player_run
 else:
 print("Invalid input! Enter a number between 1 and 6.")
 except ValueError:
 print("Please enter a valid number.")def generate_computer_run():
 return random.randint(1, 6)
def play_turn():
 player_run = player_input()
 computer_run = generate_computer_run()
 if player_run == computer_run:
 print(f"You're out! Both chose {player_run}.")
 return False, 0
 else:
 print(f"You scored {player_run} while computer chose
{computer_run}.")
 return True, player_run
def game():
 score = 0
 outs = 0
 while outs < 3:
 is_not_out, run = play_turn()
 if is_not_out:
 score += run
 print(f"Your total score is: {score}")
 else:
 outs += 1
 print(f"You have {3 - outs} outs remaining.")
 print(f"Game Over! Your final score is {score}.")
