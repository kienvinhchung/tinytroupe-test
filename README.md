# tinytroupe-test

## Clone project and install packages
```bash
git clone https://github.com/microsoft/TinyTroupe.git
cd TinyTroupe
pip install .
```

## Set up openAI API Key
```bash
export OPENAI_API_KEY="sk-xxx"
```

## Simulation with default agent: Lisa the Data Scientist
```python
from tinytroupe.examples import create_lisa_the_data_scientist
lisa_ds = create_lisa_the_data_scientist()
lisa_ds.listen_and_act("Tell me about your life")
```

## Customized Persona
```python
from tinytroupe.agent import TinyPerson

keene = TinyPerson("Keene")
keene.define("age", 28)
keene.define("nationality", "USA")
keene.define("occupation", "Machine Learning Engineer")
keene.define("traits", "professional engineer with strict deadline date and good documentation")

john = TinyPerson("John")
john.define("age", 21)
john.define("occupation", "I work as an intern where Keene works")
john.define("nationality", "USA")
```

## To instantiate a conversation between two personas above, you will need `Tiny World` function.
```python
from tinytroupe.environment import TinyWorld
world = TinyWorld("Work place", [keene, john])
world.make_everyone_accessible()
keene.listen("I want the python file well documented")
world.run(3) #trigger the conversation wit 3 rounds back-and-forth
```