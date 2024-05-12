### ENTER YOUR NAME
### ENTER YOUR REGISTER NO.
### DATE:
## Project Based Experiment
### Objective:
Perform sentiment analysis using your Facebook data and count the number of Occurrences of my name in the extracted text.
### Program:
~~~
pip install pandas textblob
import pandas as pd
from textblob import TextBlob

# Load the CSV file into a DataFrame
df = pd.read_csv('fb_sentiment.csv')

# Function to perform sentiment analysis using TextBlob
def analyze_sentiment(text):
    blob = TextBlob(str(text))
    return blob.sentiment.polarity

# Apply sentiment analysis to each row in the DataFrame
df['Sentiment'] = df['FBPost'].apply(analyze_sentiment)

# Output the DataFrame with sentiment analysis results
print(df.head())

# Filter out rows with negative sentiment (label 'N')
negative_feedback = df[df['Label'] == 'N']

# Output the negative feedback
print(negative_feedback)

~~~

### Output:
![image](https://github.com/parsh2004/Project-Based-Experiment-AAI/assets/95388047/fbe1cdb7-073d-41fc-b67c-029cf2c67f9a)
### Inference:
Inference: Thus sentiment analysis using your Facebook data ias done and filtering the data that has only negative feedback for the code is done.

