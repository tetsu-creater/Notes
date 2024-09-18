# Pytorchの基本的な実装

```python
import torch
import torch.nn as nn

class Model(nn.Module):
    def __init__(self):
        super(Model, self).__init__()

        self.linear1 = nn.Linear(input_size, output_size)
```

