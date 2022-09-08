# reduce_memory_usage

The maximum and minimum values for each column are compared with the maximum and minimum values that can be expressed by each dtype, and the dtype is changed to one that uses as little memory as possible as long as the values remain the same.

各列の dtype で表現できる最大値、最小値を比較し、できるだけメモリを消費しない dtype に変更する。

## Install

```
pip install reduce_memory_usage
```

## How to use

```python
import reduce_memory_usage

df_origin = pd.read_csv('<FILE>')
df = reduce_memory_usage.reduce_memory_usage(df_origin)

### sample
import reduce_memory_usage
import numpy as np
import pandas as pd
from sklearn.datasets import fetch_california_housing

data = fetch_california_housing()
df_origin = pd.DataFrame(data['data'], columns=data['feature_names'])

df = reduce_memory_usage.reduce_memory_usage(df_origin)

>>> Result
# (Origin) Mem. usage decreased to  1.26 Mb
# (New) Mem. usage decreased to  0.32 Mb (75.0% reduction)

```
