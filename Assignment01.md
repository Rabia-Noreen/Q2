1. Messages
Purpose: The messages parameter is used to pass a conversation history to the API. It provides context for the AI to generate relevant and coherent responses.
Functionality: Each message is a dictionary with a structure like { "role": "user", "content": "Your question here" } or { "role": "assistant", "content": "Response here" }.
Roles:
"system": Sets the behavior or guidelines for the AI (e.g., "You are a helpful assistant").
"user": Represents the user's input or query.
"assistant": Stores the AI's previous responses.
By including past messages, the API can maintain the flow of conversation and context across multiple turns.
2. Model
Purpose: Specifies which AI model to use for the task.
Functionality: Different models have varying capabilities, costs, and performance. For example:
"gpt-4": Offers more advanced reasoning and understanding.
"gpt-3.5-turbo": Faster and cheaper but less capable than GPT-4.
Why it's important: Selecting the appropriate model affects response quality, cost, and latency.
3. Max Completion Tokens
Purpose: Defines the maximum number of tokens (words or parts of words) the API can generate in the response.
Functionality:
Helps control the length of the response.
Prevents excessive token usage to stay within budget and token limits.
Total token count: Includes input tokens + output tokens. For example, if the input uses 200 tokens and max_tokens is set to 1000, the API response can use up to 800 tokens.
4. n
Purpose: Specifies the number of completions or responses to generate for each input.
Functionality:
If n = 1, the API returns a single response.
If n = 3, the API generates three responses, allowing the user to choose the most appropriate one.
Useful for comparing multiple options or for creative tasks like brainstorming.
5. Stream
Purpose: Enables streaming of the API's response in real time instead of waiting for the full output.
Functionality:
If stream = true, the response is delivered incrementally, token by token.
Provides a better user experience for long responses, especially in interactive applications.
Default behavior is false, meaning the API sends the full response at once.
6. Temperature
Purpose: Controls the randomness and creativity of the AI's responses.
Functionality:
Low values (e.g., 0.2): Produce more focused and deterministic responses, suitable for factual or technical tasks.
High values (e.g., 0.8): Generate more diverse and creative responses, useful for brainstorming or storytelling.
Balances between precision and randomness in output.
7. Top_p
Purpose: Determines the diversity of the response by limiting the probability distribution of the token sampling process.
Functionality:
Works as an alternative to temperature.
Example: If top_p = 0.9, the API considers only tokens whose cumulative probability is 90%.
Encourages more coherent outputs by avoiding rare or unlikely words.
Combining temperature and top_p can fine-tune randomness and diversity.
8. Tools
Purpose: Refers to external functionalities or APIs the AI can call during its response generation.
Functionality:
Used in tool-augmented AI systems where the model performs tasks like calculations, database queries, or browsing.
Examples include plugins, custom tools, or integrations with external APIs.
Extends the AI’s capabilities beyond text generation by enabling specific actions.