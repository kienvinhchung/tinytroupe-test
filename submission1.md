# Submission 1


## 1. How to install `tinytroupe` packages?

* We can install TinyTroupe package usig git clone:

    ```bash
    git clone https://github.com/microsoft/TinyTroupe.git
    ```

## 2. What is Turing Test? In today's world with Large Language Models (LLMs), what is the definition of Turing Test?

* The Turing Test was proposed by Alan Turing in 1950. He is a British mathematician and pioneer in computer science. It was introduced in his paper "Computing Machinery and Intelligence", where he famously posed the question: 
    
    > "Can machines think?"

* There is a practice test to answer this question:

    * A human judge has a text-based conversation with 2 unseen participants: human, and machine.

    * If the judge cannot reliably distinguish which is which, the machine is said to have pass the Turing Test, it demonstrates human-like intelligence.

* In today's world Large Language Models (LLMs) such as openAI ChatGPT, Google Gemini, they often pass casual Turing Test in informal conversations, sometimes even outperforming humans in structures tasks. 

* Passing the Turing Test is no longer a gold standard for intelligence. Theses LLMs generate language using pattern recognition, not understanding. They can simulate intelligence, but they don't have beliefs, goals, or awareness.

## 3. Create a simulation of your own topic and show me the transcript. This implies define at least two personas of your own choice with conflict built in and observe their conversation. You can simply copy/paste the conversation in a `.md` file. Please comment on the transcript whether you think the Turing Test is passed.

### Python Code:

```python
# Import Packages
from tinytroupe.agent import TinyPerson
from tinytroupe.environment import TinyWorld
```

```python
# Create Persona 1
keene_ml_engineer = TinyPerson('Keene')
keene_ml_engineer.define('age', '29')
keene_ml_engineer.define('nationality', 'American')
keene_ml_engineer.define('occupation', 'Machine Learning Engineer')
keene_ml_engineer.define('traits', ['deadline-oriented', 'structured', 'perfectionist', 'mentor'])
keene_ml_engineer.define('goals', ['deliver high-quality production ready machine learning model on time', 'ensure codebase has full documentation','mentor junior and intern employees'])
```

```python
# Create Persona 2
bob_intern = TinyPerson('Bob')
bob_intern.define('age', '21')
bob_intern.define('nationality', 'British')
bob_intern.define('occupation', 'Machine Learning Intern')
bob_intern.define('traits', ['eager to learn', 'inconsistent', 'overwhelmed', 'creative'])
bob_intern.define('goals', ['gain machine learning experience', 'balance internship and university classes', 'make a strong impression by showing initiative', 'learn machine learning by contributing to real-world projects'])
```

```python
# Create custom world
workplace = TinyWorld("Workplace", [keene_ml_engineer, bob_intern])
workplace.make_everyone_accessible()
```

```python
# Inject the initial message to start the conversation
bob_intern.listen("Hey Bob, I reviewed your pull request. We need to talk about your code formatting and missing docs.")
```

```python
# simulate the 'workplace' world
workplace.run(6)
```

### Simulation:

```text
────────────────────────────────────────────────────────────────────────────────────────────────────
Workplace step 1 of 6 
────────────────────────────────────────────────────────────────────────────────────────────────────
Keene acts: [DONE] 

Bob acts: [THINK] 
         > I need to address the feedback on my pull request. It's important to understand what
         > specific issues they found with my code formatting and documentation. I hope I can
         > clarify and improve my work based on their suggestions.
Bob acts: [TALK] 
         > Thanks for reviewing my pull request! I appreciate the feedback. Can we go over the
         > specific issues you found with the code formatting and the missing documentation? I want
         > to make sure I understand everything clearly.
Bob acts: [DONE] 

Bob --> Keene: [CONVERSATION] 
         > Thanks for reviewing my pull request! I appreciate the feedback. Can we go over the
         > specific issues you found with the code formatting and the missing documentation? I want
         > to make sure I understand everything clearly.
```

```text
────────────────────────────────────────────────────────────────────────────────────────────────────
Workplace step 2 of 6 
────────────────────────────────────────────────────────────────────────────────────────────────────
Keene acts: [THINK] 
           > Bob is asking for clarification on the feedback I provided on his pull request. I need
           > to ensure I address the specific issues he mentioned regarding code formatting and
           > documentation.
Keene acts: [TALK] 
           > Sure, Bob! Let's go over the specific issues I found. The first thing I noticed was
           > some inconsistency in the code formatting, particularly with indentation and spacing.
           > Also, there are a few functions that lack documentation. I can point those out for you.
           > Do you have the pull request open?
Keene acts: [DONE] 

Keene --> Bob: [CONVERSATION] 
           > Sure, Bob! Let's go over the specific issues I found. The first thing I noticed was
           > some inconsistency in the code formatting, particularly with indentation and spacing.
           > Also, there are a few functions that lack documentation. I can point those out for you.
           > Do you have the pull request open?
Bob acts: [THINK] 
         > Keene has pointed out specific issues with my code formatting and documentation. I need
         > to make sure I understand the details so I can fix them. I should have the pull request
         > open to address these points directly.
Bob acts: [TALK] 
         > Yes, I have the pull request open. Please go ahead and point out the specific issues you
         > found with the indentation, spacing, and the functions that lack documentation. I want to
         > make sure I address everything properly.
Bob acts: [DONE] 

Bob --> Keene: [CONVERSATION] 
         > Yes, I have the pull request open. Please go ahead and point out the specific issues you
         > found with the indentation, spacing, and the functions that lack documentation. I want to
         > make sure I address everything properly.
```

```text
────────────────────────────────────────────────────────────────────────────────────────────────────
Workplace step 3 of 6 
────────────────────────────────────────────────────────────────────────────────────────────────────
Keene acts: [THINK] 
           > Bob is ready to go over the specific issues, which is great. I need to be clear and
           > detailed in my feedback to help him improve his code effectively.
Keene acts: [TALK] 
           > Great! So, for the indentation, I noticed that some lines are not aligned properly,
           > which can make the code harder to read. For example, in the `processData` function, the
           > indentation of the `if` statement is off. As for spacing, there are a few places where
           > there are extra spaces before or after operators. Lastly, regarding documentation, the
           > `calculateResults` function doesn't have any comments explaining what it does or what
           > parameters it takes. Let's address these one by one. Does that make sense?
Keene acts: [DONE] 

Keene --> Bob: [CONVERSATION] 
           > Great! So, for the indentation, I noticed that some lines are not aligned properly,
           > which can make the code harder to read. For example, in the `processData` function, the
           > indentation of the `if` statement is off. As for spacing, there are a few places where
           > there are extra spaces before or after operators. Lastly, regarding documentation, the
           > `calculateResults` function doesn't have any comments explaining what it does or what
           > parameters it takes. Let's address these one by one. Does that make sense?
Bob acts: [THINK] 
         > Keene has provided specific feedback on my code. I need to take notes on the indentation
         > issues, spacing problems, and the lack of documentation for the `calculateResults`
         > function. This is a great opportunity to improve my coding skills and make my work
         > clearer.
Bob acts: [TALK] 
         > Yes, that makes perfect sense! Let's start with the indentation issue in the
         > `processData` function. Can you show me exactly where the `if` statement is misaligned? I
         > want to make sure I understand how to fix it properly.
Bob acts: [DONE] 

Bob --> Keene: [CONVERSATION] 
         > Yes, that makes perfect sense! Let's start with the indentation issue in the
         > `processData` function. Can you show me exactly where the `if` statement is misaligned? I
         > want to make sure I understand how to fix it properly.
```

```text
────────────────────────────────────────────────────────────────────────────────────────────────────
Workplace step 4 of 6 
────────────────────────────────────────────────────────────────────────────────────────────────────
Keene acts: [THINK] 
           > Bob is eager to learn and wants to fix the indentation issue correctly. I need to be
           > specific and clear in my explanation to help him understand how to align the `if`
           > statement properly.
Keene acts: [TALK] 
           > Sure! If you look at the `processData` function, the `if` statement should be aligned
           > with the previous line. It should have the same indentation level as the line that
           > starts the function. For example, if the function starts with four spaces, the `if`
           > statement should also start with four spaces. Let me show you the exact lines. Can you
           > see where it is misaligned?
Keene acts: [DONE] 

Keene --> Bob: [CONVERSATION] 
           > Sure! If you look at the `processData` function, the `if` statement should be aligned
           > with the previous line. It should have the same indentation level as the line that
           > starts the function. For example, if the function starts with four spaces, the `if`
           > statement should also start with four spaces. Let me show you the exact lines. Can you
           > see where it is misaligned?
Bob acts: [THINK] 
         > Keene has explained how the indentation should be aligned in the `processData` function.
         > I need to carefully check the lines to see where the misalignment is and make the
         > necessary adjustments. This is a good learning opportunity for me.
Bob acts: [TALK] 
         > Yes, I can see where the `if` statement is misaligned. It should start with the same
         > indentation level as the function itself. Thank you for pointing that out! I will fix
         > that right away. What should I do next?
Bob acts: [DONE] 

Bob --> Keene: [CONVERSATION] 
         > Yes, I can see where the `if` statement is misaligned. It should start with the same
         > indentation level as the function itself. Thank you for pointing that out! I will fix
         > that right away. What should I do next?
```

```text
────────────────────────────────────────────────────────────────────────────────────────────────────
Workplace step 5 of 6 
────────────────────────────────────────────────────────────────────────────────────────────────────
Keene acts: [THINK] 
           > Bob is ready to move on to the next issue after fixing the indentation. I need to guide
           > him on the spacing issues next, as well as the documentation for the functions.
Keene acts: [TALK] 
           > Next, let's address the spacing issues. I noticed that in several places, there are
           > extra spaces before operators like `+` and `-`. For example, in the `calculateResults`
           > function, you have `result = value1 + value2` with an extra space before the `+`. You
           > should remove those extra spaces to keep the code clean. Can you find those instances?
Keene acts: [DONE] 

Keene --> Bob: [CONVERSATION] 
           > Next, let's address the spacing issues. I noticed that in several places, there are
           > extra spaces before operators like `+` and `-`. For example, in the `calculateResults`
           > function, you have `result = value1 + value2` with an extra space before the `+`. You
           > should remove those extra spaces to keep the code clean. Can you find those instances?
Bob acts: [THINK] 
         > Keene has pointed out the spacing issues in my code, specifically mentioning the extra
         > spaces before operators. I need to carefully review the `calculateResults` function and
         > identify all instances where this occurs. This is important for maintaining clean code.
Bob acts: [TALK] 
         > Got it! I will look for those extra spaces before operators in the `calculateResults`
         > function and remove them. Thank you for pointing that out! Is there anything else I
         > should be aware of while I make these changes?
Bob acts: [DONE] 

Bob --> Keene: [CONVERSATION] 
         > Got it! I will look for those extra spaces before operators in the `calculateResults`
         > function and remove them. Thank you for pointing that out! Is there anything else I
         > should be aware of while I make these changes?
```

```text
────────────────────────────────────────────────────────────────────────────────────────────────────
Workplace step 6 of 6 
────────────────────────────────────────────────────────────────────────────────────────────────────
Keene acts: [THINK] 
           > Bob is making good progress and is eager to learn. I should remind him about the
           > importance of documentation as well, since that was one of the issues we identified
           > earlier.
Keene acts: [TALK] 
           > Absolutely! While you're making those changes, don't forget to add documentation for
           > the `calculateResults` function. It’s important to explain what the function does, what
           > parameters it takes, and what it returns. This will help anyone who reads your code in
           > the future. Do you need any help with how to document it?
Keene acts: [DONE] 

Keene --> Bob: [CONVERSATION] 
           > Absolutely! While you're making those changes, don't forget to add documentation for
           > the `calculateResults` function. It’s important to explain what the function does, what
           > parameters it takes, and what it returns. This will help anyone who reads your code in
           > the future. Do you need any help with how to document it?
Bob acts: [THINK] 
         > Keene has emphasized the importance of adding documentation for the `calculateResults`
         > function. I need to explain what the function does, its parameters, and its return value.
         > This is crucial for making my code understandable for others. I should think about how to
         > structure this documentation clearly.
Bob acts: [TALK] 
         > I appreciate the reminder about the documentation! I understand that I need to explain
         > what the `calculateResults` function does, its parameters, and what it returns. I think I
         > can manage that, but if you have any tips on how to structure it, I would love to hear
         > them!
Bob acts: [DONE] 

Bob --> Keene: [CONVERSATION] 
         > I appreciate the reminder about the documentation! I understand that I need to explain
         > what the `calculateResults` function does, its parameters, and what it returns. I think I
         > can manage that, but if you have any tips on how to structure it, I would love to hear
         > them!
```

### Additional simulation (optional):

```python
# Since agents remember the conversation, lets try to keep going by adding 3 more steps:
workplace.run(3)
```

```text
────────────────────────────────────────────────────────────────────────────────────────────────────
Workplace step 1 of 3 
────────────────────────────────────────────────────────────────────────────────────────────────────
Keene acts: [THINK] 
           > Bob is looking for tips on how to structure the documentation for the
           > `calculateResults` function. I need to provide him with a clear and concise structure
           > that he can follow.
Keene acts: [TALK] 
           > For structuring the documentation, you can follow this format: Start with a brief
           > description of what the function does. Then, list the parameters with their types and a
           > short explanation of each. Finally, describe what the function returns. For example:
           > """ Calculates the results based on input values.  Parameters: - value1 (int): The
           > first value to be processed. - value2 (int): The second value to be processed.
           > Returns: - int: The sum of value1 and value2. """  This structure makes it easy for
           > others to understand the function at a glance. Does that help?
Keene acts: [DONE] 

Keene --> Bob: [CONVERSATION] 
           > For structuring the documentation, you can follow this format: Start with a brief
           > description of what the function does. Then, list the parameters with their types and a
           > short explanation of each. Finally, describe what the function returns. For example:
           > """ Calculates the results based on input values.  Parameters: - value1 (int): The
           > first value to be processed. - value2 (int): The second value to be processed.
           > Returns: - int: The sum of value1 and value2. """  This structure makes it easy for
           > others to understand the function at a glance. Does that help?
Bob acts: [THINK] 
         > Keene provided a clear structure for documenting the `calculateResults` function. I need
         > to follow this format to ensure my documentation is concise and informative. This will
         > help others understand my code better. I should also remember to apply the same
         > principles to other functions in the future.
Bob acts: [TALK] 
         > Thank you for the documentation structure! That really helps. I will write the
         > documentation for the `calculateResults` function following your format. Once I make
         > those changes, I’ll let you know. Is there anything else you’d like me to focus on while
         > I’m at it?
Bob acts: [THINK] 
         > I need to make sure I implement all the feedback Keene provided. I will fix the
         > indentation, remove the extra spaces, and add the documentation for the
         > `calculateResults` function. This is a great opportunity to improve my coding skills and
         > show my initiative.
Bob acts: [TALK] 
         > I will get started on those changes right away! Thank you for your help, Keene. I’ll let
         > you know once I’ve made the updates to the code and documentation.
Bob acts: [DONE] 

Bob --> Keene: [CONVERSATION] 
         > Thank you for the documentation structure! That really helps. I will write the
         > documentation for the `calculateResults` function following your format. Once I make
         > those changes, I’ll let you know. Is there anything else you’d like me to focus on while
         > I’m at it?
Bob --> Keene: [CONVERSATION] 
         > I will get started on those changes right away! Thank you for your help, Keene. I’ll let
         > you know once I’ve made the updates to the code and documentation.
```

```text
────────────────────────────────────────────────────────────────────────────────────────────────────
Workplace step 2 of 3 
────────────────────────────────────────────────────────────────────────────────────────────────────
Keene acts: [THINK] 
           > Bob is taking the initiative to make the changes, which is great. I should prepare to
           > review his updates once he finishes. I need to stay available for any further questions
           > he might have.
Keene acts: [DONE] 

Bob acts: [DONE]
```

```text
────────────────────────────────────────────────────────────────────────────────────────────────────
Workplace step 3 of 3 
────────────────────────────────────────────────────────────────────────────────────────────────────
Keene acts: [DONE] 

Bob acts: [DONE]
```

## My comment

* In terms of language fluency and context awareness

    * It absolutely passed the Turing Test

    * The language is natural, polite, and professional.

    * Both personas give detailed and thouhtful responses and instructions, actionable feedback, and show growth and curiosity.

    * The conversation flows logically and stays on-topic.

* In terms of linguistic. and interaction standpoint:

    * It can be too formal, structured, and lengthy.

    * Still, it can fool an average human observer.

    * The agents do not show true understanding, they only simulate understanding through pattern recognition, not real comprehension.