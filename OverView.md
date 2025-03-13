# Steps

1. Load the data
2. Manually tagged (Characters, Themes, Actions, Emotions, Speaker, Listener, Contextual Tag by making clusters)
3. Word embedded the Translation Column and stored it as a column Embedding (1x784, total 700x784) and put them into 20 clusters with KMeans and categorized the verses in 20 clusters and put contextual tags via ChatGPT Prompting not api
4. For word embedding used Sentence Transformer "all-mpnet-base-v2" with 784 vectors convert the user prompt into 1x784 vector
5. Normalize everything within -1 to 1
6. Match the user prompt with word embedding with the help of cosine similarity
7. After matching all, we store it into the Embedding Variable and sort it out in descending order
8. Extract the top k indices that are most relatable verse to prompt
9. Provide the output
10. Added the verse number and thinking of adding contextual meaning after each column [https://github.com/Parthdsaiml/GitaConsiousness/blob/main/sources/ContextMeaning.py]
-----------------

What we thinking now

1. Using LLM API to provide more human response instead of just that verse
2. Creating Prompt dataset which contains what prompts we have to give LLM API
3. After this trying to store this into database with user some personal info {mood, metaphor, age, vibe, gender, ...} which helps LLM API to generate more relatable output
4. Then suggesting real world examples and how to implement it
5. Making it less sugarcoating yet more relatable so that it does make changes

