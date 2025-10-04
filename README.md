# Tweet_Smith


X (Twitter) Post Generator

Overview
This notebook automates the creation and optimization of engaging Twitter (X) posts for any topic using the Gemini 2.5 Flash Large Language Model API. The workflow generates an initial post, evaluates its quality, and then iteratively improves it based on LLM-generated feedback. The process continues for up to a user-defined number of optimization rounds or until the tweet is rated as "approved".

Features
Automated X Post Generation: Produces a concise, on-topic, and engaging X post for any user-supplied topic.

Evaluation and Feedback: Each generated post is evaluated on relevance, clarity, and engagement using the Gemini LLM, receiving a verdict ("approved" or "need improvement") and detailed feedback.

Iterative Optimization: If improvement is needed, the post is revised and the process is repeated, using LLM-driven suggestions, until the post meets quality standards or the optimization limit is reached.

History Tracking: All versions and feedback are stored for review, facilitating transparency and learning.

Workflow
<img width="292" height="372" alt="image" src="https://github.com/user-attachments/assets/1ac9864a-3b79-40b6-b381-5244fa9b0c82" />



Input: User provides a topic (e.g. "Salaar").

Generation: The workflow produces an initial tweet text using the Gemini API, aiming for excitement, relevance, and length under 280 characters.

Evaluation: The LLM evaluates the tweet and classifies it as "approved" or "needs improvement," providing detailed feedback.

Optimization: If needed, the tweet is modified in response to feedback, and the cycle repeats up to a set maximum (default 5 iterations).

Output: The process returns the best tweet, all tweet history, evaluations, and feedback for each round.

Example
If the topic is "Salaar", a possible system output might be:

Round 1 Tweet: Prabhas unleashed a beast in Salaar! Prashanth Neels signature intense world-building combined with raw, relentless action makes Khansaar an unforgettable experience. Still feeling the echo of that roar!

Evaluation: Approved. The tweet is well-crafted and engaging.

History: Shows all iterations if improvements were needed before reaching approval.

Project Structure
Section	Description
Imports	LLM API, graph workflow utilities
Tweet Generation	LLM prompt for initial post for topic
Tweet Evaluation	LLM assesses for clarity, engagement, relevance
Optimization	LLM rephrases tweet as per evaluation feedback
Workflow Logic	Ties together nodes, edges, and iterations
Example Execution	Demonstrates the full pipeline and result display
Requirements
Python 3.8+

langgraph, google-generativeai, operator, langchaincore

API key for Gemini LLM (via environment variable and .env file)

Jupyter Notebook

Usage
Set up a .env file containing your Gemini API key.

Install dependencies:

text
pip install langgraph google-generativeai langchain-core python-dotenv
Run notebook cells, entering your desired topic in the input state.

View generated post history, evaluation verdicts, and feedback across all optimization rounds.

Extending
Tune prompts for different social media platforms.

Adjust evaluation criteria (add hashtags, style, compliance checks).

Integrate with X API for direct posting or scheduled posts.
