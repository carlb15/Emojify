# NOTE: Implementation hidden due to Coursera Terms of Service.

# Emojify  
Have you ever wanted to make your text messages more expressive? Your emojifier app will help you do that. So rather than writing "Congratulations on the promotion! Lets get coffee and talk. Love you!" the emojifier can automatically turn this into "Congratulations on the promotion! 👍 Lets get coffee and talk. ☕️ Love you! ❤️"  

The model takes as input a sentence (such as "Let's go see the baseball game tonight!") and finds the most appropriate emoji to be used with this sentence (⚾️). In many emoji interfaces, you need to remember that  ❤️  is the "heart" symbol rather than the "love" symbol. But using word vectors, the training set explicitly relates only a few words to a particular emoji, the algorithm will be able to generalize and associate words in the test set to the same emoji even if those words don't even appear in the training set. This allows you to build an accurate classifier mapping from sentences to emojis, even using a small training set.

Start of the notebook is a baseline model (Emojifier-V1) using word embeddings, then later a more sophisticated model (Emojifier-V2) that further incorporates an LSTM.

# Examples of Model Successes:
Input: i adore you              Output: i adore you ❤️  
Input: i love you               Output: i love you ❤️  
Input: funny lol                Output: funny lol 😄  
Input: let's play with a ball   Output: let's play with a ball ⚾  
Input: food is ready            Output: food is ready 🍴  
Input: not feeling happy        Output: not feeling happy 😄  
  
# Examples of Model Failure:
Both versions of the emoji prediction model fail to predict the correct emoji in certain cases such as negation due to the small training set size. If we train on a larger dataset then the LSTM model (V2) will handle negation better than V1 which doesn't worry about word ordering.  
  
Expected emoji:😄   Prediction: she got me a nice present	❤️   
Expected emoji:😞   Prediction: yesterday we lost again	⚾  
Expected emoji:😞   Prediction: not feeling happy 😄  

# Conclusion  
Model needs a larger training dataset to handle negations and other word combinations that are currently failing. LSTM is the clear winner because it handles word ordering unlike the V1 model. Possible extensions/modifications of this project are:   
1) convert an input sentence into a emoji output sentence   
   Input: i adore you    Output: ❤️ 
2) or replace phrases with emojis throughout a sentence instead of adding an emoji at the end.  
   Input: Lets get coffee and talk.  Output: Lets get ☕️ and talk.
