# Check if GPU is attached
Python code for Tensorflow and Keras to check if GPU is attached for use in machine/deep learning.

## Tensorflow
**Confirm Tensorflow sees the GPU**

```python
from tensorflow.python.client import device_lib
assert 'GPU' in str(device_lib.list_local_devices())
```

## Keras
**Confirm Keras sees the GPU**

```python
from keras import backend
assert len(backend.tensorflow_backend._get_available_gpus()) > 0
```
