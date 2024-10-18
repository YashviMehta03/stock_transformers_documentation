# Time2Vec

## Intro to Time2Vec

Time2Vec is a time encoding mechanism that transforms time-related features into a higher-dimensional space, capturing both linear and periodic patterns. It uses a combination of sine and linear components to effectively represent temporal information. This encoding helps improve the performance of models in time series forecasting tasks by providing a richer representation of time.

## Code Snippet

```python
class Time2Vec:
    def __init__(self, kernel_size=1):
        self.k = kernel_size

    def __call__(self, inputs):
        wb = tf.Variable(tf.random.normal([inputs.shape[-1], self.k]))
        bb = tf.Variable(tf.random.normal([self.k]))
        wa = tf.Variable(tf.random.normal([inputs.shape[-1], self.k]))
        ba = tf.Variable(tf.random.normal([self.k]))

        bias = tf.matmul(inputs, wb) + bb
        dp = tf.matmul(inputs, wa) + ba
        wgts = tf.math.sin(bias) + dp

        return tf.concat([inputs, wgts], axis=-1)
```

## Implementation

Key points about this implementation:

The architecture creates kernel_size number of new temporal features
For each feature, it learns:  

A periodic component: sin(Wx + b)  
A linear component: Wx + b  
These are summed together


Each temporal feature has its own learnable parameters:

- wb, bb: Parameters for inside the sine function  
- wa, ba: Parameters for the linear component


The original input is preserved in the output by concatenating it with the new features
This implementation allows the model to adaptively learn:

- Different frequencies (through wb)  
- Phase shifts (through bb)  
- Linear trends (through wa and ba)