# Hangman

https://colab.research.google.com/drive/1_4-frxVf1Z8_l6DxZW46yuVH-CLfTLwk?authuser=5#scrollTo=BErZouQvKhoI&line=35&uniqifier=1

## Code

  import random
  
  word_list = [ 
  'absurd',
  'injury', 
  'jackpot',
  'bagpipes',
  'rhythm',
  'blizzard',
  'syndrome',
  'wave',       
  'bookworm', 
  'funny',  
  'galaxy',
               
  ]
  
  correct_word = random.choice(word_list)
  word_len = len(correct_word)
  
  
  game_end = False
  
  lives = 6
  
  
  print(correct_word)
  
  display = []
  for _ in range(word_len):
      display += "_"
  
  while not game_end:
      guess = input("Guess a letter: ").lower()
  
      if guess in display:
        print(f"You have already guessed {guess}")
  
      for position in range(word_len):
          letter = correct_word[position]
        
          if letter == guess:
              display[position] = letter
  
      if guess not in correct_word:
  
        print(f"The letter {guess} is not in the word. You lose a life ")
        
        lives -= 1
        if lives == 0:
            game_end = True
            print("Game Over.")
  
      print(f"{' '.join(display)}")
  
      if "_" not in display:
        game_end = True
        print("You have guessed the word correctly. You win. ")
