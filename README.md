<H3>ENTER YOUR NAME</H3> Mahalakshmi K
<H3>ENTER YOUR REGISTER NO.</H3> 212222240057

<H1 Align="center">Project Based Experiment<H1>
<H3>Objective:<H3>
To perform sentiment analysis on Facebook data using Python and TextBlob, and to count the number of times the name "Maha" appears in the extracted text.
  
<H3>Program:</H3>

# Install required libraries (run once)
# pip install pandas textblob

import pandas as pd
from textblob import TextBlob

# Step 1: Read Facebook data
df = pd.read_csv('fb_sentiment.csv')  # The CSV should have a column named 'FBPost'

# Step 2: Function for sentiment analysis
def analyze_sentiment(text):
    blob = TextBlob(str(text))
    return blob.sentiment.polarity

# Step 3: Apply sentiment analysis
df['Sentiment'] = df['FBPost'].apply(analyze_sentiment)

# Step 4: Display first few rows
print("\nSample data with Sentiment scores:")
print(df.head())

# Step 5: Filter for positive posts (optional)
positive_feedback = df[df['Sentiment'] > 0]
print("\nPositive posts:")
print(positive_feedback)

# Step 6: Count occurrences of the name "Maha"
your_name = "Maha"
all_text = " ".join(df['FBPost'].astype(str))
name_count = all_text.lower().count(your_name.lower())

print(f"\nThe name '{your_name}' appears {name_count} times in the Facebook posts.")


<H3>Output:</H3>

<img width="790" height="517" alt="Screenshot (70)" src="https://github.com/user-attachments/assets/fd568478-2e47-41c6-bc86-1f480639bff7" />

<H3>Inference:</H3>

I learned to perform sentiment analysis using Python’s Pandas and TextBlob, analyze text data, and interpret sentiment polarity effectively.
