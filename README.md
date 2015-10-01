# Back End Coding Project

**A little context on the problem:**

The way that users interact with each other on Twitter can inform the best candidates to target for particular marketing campaigns. Your task is to develop a solution that will classify a population of users from Twitter based on their tweeting habbits. 

For these purposes we will define the following. Given the text of a tweet, you can categorize it as a:
 - Retweet
  - begins with "RT @" followed by an alphanumeric handle
 - Mention
  - contains an "@" followed by an alphanumeric handle, but is not a retweet
 - Broadcast
  - is neither a retweet nor a mention 

You can then identify a given user as a:
 - Retweeter
  - has a retweet rate at or above the 75th percentile for all users
 - Conversationalist
  - has a mention rate at or above the 75th percentile for all users
 - Broadcaster
  - has a broadcast rate at or above the 75th percentile for all users

Your solution should operate on a stream of tweet data and tag each user with zero or more of these designations as appropriate. It should also report overall statistics on the total percentage of users tagged with each designation.

**General guidelines and requirements:**

 - You will use data hosted in a publicly-accessible S3 bucket as input 
  - the location of the bucket should be in an e-mail from us
  - data in this bucket is broken into a number of objects, each representing the tweet history for a single user and keyed with the user's handle
  - each line is a JSON document of the form `{ "text": "<tweet_text>", "screen_name": "<user_handle>"}`
 - Your solution should output a csv file with  one row for each user in the dataset and column format: 
  - `screen_name, is_retweeter, is_conversationalist, is_broadcaster`
 - You are free to use any language, library or framework, but be prepared to justify your choices
 - We should be able to run your solution from a linux instance in EC2, assume the hardware limitations of a [c4.2xlarge isntance](https://aws.amazon.com/ec2/pricing/). Please provide a README on how to run your solution
 - A misclassification rate up to 10% is acceptable in order to operate on the data in a more efficient fashion
 - Your solution will be evaluated on efficiency and cleanliness

Please note that the data you are operating on has been made publicly accessible for your convenience. However, it is confidential and we ask you not to duplicate in full or share it. Actual Twitter handles have been obfuscated.

We are looking forward to seeing what you can do. Please let us know if you have any questions
