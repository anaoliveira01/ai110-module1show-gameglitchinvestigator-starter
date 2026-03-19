# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

- What did the game look like the first time you ran it?
A guessing game with a simplistic UI and features that seem to work fine. After testing these features, I discovered several issues. I also noticed that the range and attempts did not make sense for the difficulty options.

- List at least two concrete bugs you noticed at the start  
  (for example: "the secret number kept changing" or "the hints were backwards").
  - The attempts allowed don't update correctly
  - Secrets exceed the range for easy and hard modes
  - Range on hard mode is smaller than normal
  - There is an issue with even numbers
  - The hints were wrong

---

## 2. How did you use AI as a teammate?

- Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)?
  - Claude in VSCode

- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).
  - For example, on the try block at line 36, it suggested me to fix the "go lower" and "go higher" print statements. The result made logical sense.

- Give one example of an AI suggestion that was incorrect or misleading (including what the AI suggested and how you verified the result).
  - It did not suggest updating the update_score function in logic_utils.py correctly after doing the same for the parse_guess function. I noticed that the correct changes were not being made. It also included a new redundant function to check if the "go lower" and "go higher" statements are still in the wrong place, even after fixing that part of the code.
  

---

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
  - For basic changes, I tested the game again through the UI by targeting the changes implemented. For test_game_logic.py, I made a new function to output the results from each test case and ran the file again.
- Describe at least one test you ran (manual or using pytest) and what it showed you about your code.
  - I ran the functions test_winning_guess(), test_guess_too_high(), and test_guess_too_low(). I tested then manually by running the file instead of using pytest.
- Did AI help you design or understand any tests? How?
  - It help me fix the tuple issue in those three functions and helped me design the main test function to see each output.

---

## 4. What did you learn about Streamlit and state?

- In your own words, explain why the secret number kept changing in the original app.
  - The "New Game" button in the original code updated the secret but left the user stuck on the previous game because it didn't change the status back to "playing".
- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?
  - If you change the code, it automatically refreshes the page without needing to manually refresh it.
- What change did you make that finally gave the game a stable secret number?
  - By adding the line st.session_state.status = "playing", so that the game restarts properly after clicking "New Game".
---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
    - I plan on thinking about AI responses critically, fully understanding the context it has and its suggestions. It is important to give correct, detailed intructions and analyze its responses.
- What is one thing you would do differently next time you work with AI on a coding task?
  - The AI commited errors and gave irrelevant suggestions, so I will be more aware of this possibility and take control of all the changes made.
- In one or two sentences, describe how this project changed the way you think about AI generated code.
  - It is not always correct or achieving the same goal that you have in mind.
