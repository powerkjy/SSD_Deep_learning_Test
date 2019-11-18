##Tensorflow 관련 Attribute Error
  - `import tensorflow.compat.v1 as tf`
  - `tf.disable_v2_behavior()`

##RuntimeError: Attempting to capture an EagerTensor without building a function.##
  - `tf.enable_eager_execution()`

##_tkinter.TclError: couldn't connect to display ":0"
   - `import matplotlib`
   - `matplotlib.use('pdf')`
   - `import matplotlib.pyplot as plt`
