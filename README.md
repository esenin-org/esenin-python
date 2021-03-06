# Esenin python

Python wrapper for json requests to [esenin-server](https://github.com/esenin-org/esenin-server). 

### Installation

```bash
pip install esenin
```

### Usage

```python
from esenin import Client

nlp = Client(ip="127.0.0.1", port="9000")

print(nlp.get_pos("Мама мыла раму."))

id = nlp.fit_topics([["Мама", "мыла", "раму"], ["Мама", "мыла", "окно"], ["Мама", "мыла", "пол"]])
print(nlp.get_topics(id["id"], "Мама"))
```

### Functions

##### `.get_pos(string)`
Takes arbitrary _russian_ text and returns Part Of Speech tags. 

See [esenin-server](https://github.com/esenin-org/esenin-server#pos) for example of request and response. 

##### `.fit_topics(list of lists of string, int)`
Takes list of documents, where document is a list of terms, and number of topics. 
Trains topic modeling algorithm with given terms and number of topics.
 
Returns the id of trained model, it's used in `get_topics` function.

See [esenin-server](https://github.com/esenin-org/esenin-server#tm) for example of request and response.

##### `.get_topics(id, string)`
Takes id of trained topic model and a term. 
Returns probabilities of a term to be in each topic. 

See [esenin-server](https://github.com/esenin-org/esenin-server#tm) for example of request and response.



