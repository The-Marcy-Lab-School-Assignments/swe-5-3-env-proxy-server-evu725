# Short Response Questions

Answer each question below in your own words. Aim for 3–5 sentences per answer. Be specific — use the exact terms and concepts from the lesson.

Your responses will each be evaluated out of 6 points. You can earn 3 points for writing quality and 3 points for the accuracy and precision of the technical content per question.

---

## Question 1:

Why is it unsafe to make requests to a third-party API (like Giphy) directly from frontend JavaScript code? What specific risk does this create, and how can a malicious user exploit it?

**Your answer here**:
When your API key is in your frontend code, it becomes publicly accessible to anyone who inspects your source code or check your network requests from the browser's developer tools. Since the key is tied to your personal account, a malicious user can steal it and make requests from your own API account, either from abusing your rate limits or stacking up charges if you're on a paid subscription.

---

## Question 2:

What is the proxy server strategy? How does it help avoid exposing API Keys in client-side code while still providing access to APIs that require keys?

**Your answer here**:
The proxy server strategy uses your own backend server as a middleman between the frontend and the third-party API. The client sends a request to your server, your server adds the API key forwards the request to the API, then passes the response back to the client. Since the API key only lives on the server, the client never has access to it and it can't be stolen from the browser.

---

## Question 3:

What is an environment variable, and why do we store API keys in a .env file instead of directly in source code? What role does .gitignore play in this setup, and what could go wrong if the .env file were accidentally committed to GitHub?

**Your answer here**:
Environment variables are values stored outside your source code, usually in a .env file so that sensitive information like API keys isn't inside to your program. Since .env files are excluded by .gitignore, they never get pushed to GitHub. If someone accidentally committed the .env file, anyone browsing the repository could read the API key and use it to make requests on your account, abusing rate limits or running up charges.

---
