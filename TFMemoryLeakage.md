# Intro


# Issue description:

When repeatedly calling 'model.predict', the program eats up
memories slowly until it crashes.

# Solution:
imported the below modules 
```python
from tensorflow.keras import backend as K
import gc
````
and added in two lines of code after each loop
```python
K.clear_session()
gc.collect()

```
It looks like gc.collect takes a bit time to run, so 
can also run gc.collection not after every loop, but
after a certain amount of loops.

ref: https://github.com/keras-team/keras/issues/13118
