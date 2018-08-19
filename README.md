# Esenin python

Python wrapper for json requests to [esenin-server](https://github.com/esenin-org/esenin-server). 

### Instalation

```bash
pip install esenin_python
```

### Usage

```python
from esenin_python import Client

nlp = Client(ip="127.0.0.1", port="9000")
print(nlp.get_pos("Мама мыла раму."))
```

### Functions

##### `.get_pos(string)`
Takes arbitrary _russian_ text and returns Part Of Speech tags. 


