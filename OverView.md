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
10. Added the verse number and thinking of adding contextual meaning after each column [https://github.com/Parthdsaiml/GitaConsiousness/blob/main/sources/ContextMeaning.json]
-----------------

What we thinking now

1. Using LLM API to provide more human response instead of just that verse
2. Creating Prompt dataset which contains what prompts we have to give LLM API
3. After this trying to store this into database with user some personal info {mood, metaphor, age, vibe, gender, ...} which helps LLM API to generate more relatable output
4. Then suggesting real world examples and how to implement it
5. Making it less sugarcoating yet more relatable so that it does make changes

-----

# **GeetaBot: AI-Powered Wisdom from the Bhagavad Gita**  

## **Overview**  
GeetaBot is an advanced AI-driven assistant that delivers **personalized, practical wisdom** from the Bhagavad Gita. Unlike generic chatbots, it **understands context, emotions, and user intent** to provide deep, meaningful responses based on **Gita verses**. The goal is not just to display verses but to **make them relatable, actionable, and transformative** for the user.  

## **How We Are Building It**  

### **1. Data Preparation & Manual Tagging**  
- **700+ Bhagavad Gita verses** are manually tagged with:  
  - **Characters:** Who is speaking? Who is being addressed?  
  - **Themes:** Dharma, Karma, Detachment, Devotion, etc.  
  - **Actions:** What action does the verse suggest?  
  - **Emotions:** What feelings does the verse invoke?  
  - **Contextual Tagging:** Clusters similar verses into meaningful groups.  

### **2. Embedding & Clustering for Smart Matching**  
- **Word Embedding:**  
  - Each verse is **converted into a 784-dimensional vector** using **Sentence Transformer (all-mpnet-base-v2)**.  
  - The same technique is used to **embed the user’s query**, making it machine-comparable.  
- **KMeans Clustering:**  
  - **20 clusters** group verses with similar meaning to enhance **contextual retrieval**.  

### **3. Intelligent Query Matching**  
- User input is **normalized (-1 to 1)** and compared with verse embeddings using **cosine similarity**.  
- The most **relevant verses are extracted and ranked** based on similarity.  

### **4. Beyond Just Retrieval – Making Responses Human**  
- **LLM API Integration**:  
  - Instead of just showing a verse, we **use an LLM to generate a natural response**.  
  - Ensures the reply **feels like real advice, not just a text dump**.  
- **Prompt Engineering for LLM**:  
  - A structured **prompt dataset** is designed for better LLM responses.  
  - Example: A user struggling with failure shouldn’t just get BG 2.47 but a **motivational, real-world explanation**.  

### **5. Personalization for Deeper Impact**  
- User-specific attributes (mood, metaphor preference, age, vibe, etc.) are considered for **tailored responses**.  
- **Real-world analogies** are added to make teachings applicable in daily life.  

### **6. Action-Oriented Advice**  
- **Verses are not just explained but turned into action points.**  
- Example: BG 2.47 → "Make a list of 3 tasks you’ve been avoiding due to fear of results."  

### **7. Structured Data Representation**  
Every verse has structured metadata for **versatile AI processing**, including:  

```json
{
  "BG 2.47": {
    "character": ["Arjuna", "Krishna"],
    "theme": ["Karma Yoga", "Detachment", "Dharma"],
    "action": ["Focus on efforts", "Detach from results", "Perform duty without hesitation"],
    "speaker": "Krishna",
    "listener": "Arjuna",
    "emotion": "Encouragement",
    "cluster_tag": "Detachment from Results",
    "contextual_tag": "Arjuna is anxious about the war; Krishna explains selfless action",
    "philosophical_meaning": "Focus on duty without attachment to outcomes. True yoga is performing action without desiring rewards.",
    "modern_analogies": ["Like a student writing exams without obsession over marks", "Like a farmer planting crops without stressing over the rain"],
    "actions": ["List 3 tasks you're avoiding due to outcome fear", "Practice a task today without worrying about the result"],
    "emotional_phrases": {
      "anxiety": "Your right is to work, not the fruits – let go like a gardener plants trees.",
      "failure": "Every attempt is a step in Yoga, even if results disappoint.",
      "overthinking": "Action matters, not endless calculations – flow with your duty."
    }
  }
}
```


### **Why This Approach?**  
✔ **Combines AI retrieval & LLM intelligence** for **precise, human-like responses**.  
✔ **Goes beyond traditional keyword search** – uses **embeddings & clustering** to deeply understand queries.  
✔ **Emotionally intelligent** – detects user **mood & intent** to give **motivational, practical guidance**.  
✔ **Personalized & Actionable** – converts **spiritual wisdom into real-world applications**.  

GeetaBot is not just a **Bhagavad Gita search engine**—it’s an **AI-driven mentor** that makes ancient wisdom **truly relevant** to modern life.  

---

