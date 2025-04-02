# Submission 1


## 1. How to install `tinytroupe` packages?


## 2. What is Turing Test? In today's world with Large Language Models (LLMs), what is the definition of Turing Test?


## 3. Create a simulation of your own topic and show me the transcript. This implies define at least two personas of your own choice with conflict built in and observe their conversation. You can simply copy/paste the conversation in a `.md` file. Please comment on the transcript whether you think the Turing Test is passed.

```python
# Import Packages
from tinytroupe.agent import TinyPerson
from tinytroupe.environment import TinyWorld

# Create Persona 1
keene_ml_engineer = TinyPerson('Keene')
keene_ml_engineer.define('age', '29')
keene_ml_engineer.define('nationality', 'American')
keene_ml_engineer.define('occupation', 'Machine Learning Engineer')
keene_ml_engineer.define('traits', ['deadline-oriented', 'structured', 'perfectionist', 'mentor'])
keene_ml_engineer.define('goals', ['deliver high-quality production ready machine learning model on time', 'ensure codebase has full documentation','mentor junior and intern employees'])

# Create Persona 2
bob_intern = TinyPerson('Bob')
bob_intern.define('age', '21')
bob_intern.define('nationality', 'British')
bob_intern.define('occupation', 'Machine Learning Intern')
bob_intern.define('traits', ['eager to learn', 'inconsistent', 'overwhelmed', 'creative'])
bob_intern.define('goals', ['gain machine learning experience', 'balance internship and university classes', 'make a strong impression by showing initiative', 'learn machine learning by contributing to real-world projects'])

# Create custom world, inject initial message, then simulate it
workplace = TinyWorld("Workplace", [keene_ml_engineer, bob_intern])
workplace.make_everyone_accessible()
bob_intern.listen("Hey Bob, I reviewed your pull request. We need to talk about your code formatting and missing docs.")
workplace.run(6)
```

```bash
────────────────────────────────────────────────────────────────────────────────────────────────────
Workplace step 1 of 6 
────────────────────────────────────────────────────────────────────────────────────────────────────

────────────────────────────────────────────────────────────────────────────────────────────────────
Workplace step 2 of 6 
────────────────────────────────────────────────────────────────────────────────────────────────────

────────────────────────────────────────────────────────────────────────────────────────────────────
Workplace step 3 of 6 
────────────────────────────────────────────────────────────────────────────────────────────────────

────────────────────────────────────────────────────────────────────────────────────────────────────
Workplace step 4 of 6 
────────────────────────────────────────────────────────────────────────────────────────────────────

────────────────────────────────────────────────────────────────────────────────────────────────────
Workplace step 5 of 6 
────────────────────────────────────────────────────────────────────────────────────────────────────

────────────────────────────────────────────────────────────────────────────────────────────────────
Workplace step 6 of 6 
────────────────────────────────────────────────────────────────────────────────────────────────────
```

My comment: I think the chat bots passed the Turing Test. Here is why...
