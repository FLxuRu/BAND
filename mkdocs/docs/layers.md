### scaled\_dot\_product\_attention
```python
def scaled_dot_product_attention(q, k, v, mask)
```
����ע����Ȩ�ء� q, k, v �������ƥ���ǰ��ά�ȡ� k, v ������ƥ��ĵ����ڶ���ά�ȣ����磺seq_len_k = seq_len_v�� ��Ȼ mask ���������ͣ�����ǰհ���в�ͬ����״�� ���� mask �����ܽ��й㲥ת���Ա���͡�

����: q: �������״ == (..., seq_len_q, depth) k: ��������״ == (..., seq_len_k, depth) v: ��ֵ����״ == (..., seq_len_v, depth_v) mask: Float ����������״��ת���� (..., seq_len_q, seq_len_k)��Ĭ��ΪNone��

����ֵ: �����ע����Ȩ��

### create\_padding\_mask
```python
def create_padding_mask(x)
```

### create\_look\_ahead\_mask
```python
def create_look_ahead_mask(x)
```

### point\_wise\_feed\_forward\_network
```python
def point_wise_feed_forward_network(d_model, dff)
```

## class PositionalEncoding
### \_\_init\_\_
```python
def __init__(vocab_size, d_model)
```

### get\_angles
```python
def get_angles(position, i, d_model)
```

### positional\_encoding
```python
def positional_encoding(position, d_model)
```

### call
```python
def call(inputs)
```

## class MultiHeadAttention
### \_\_init\_\_
```python
def __init__(d_model, num_heads)
```

### split\_heads
```python
def split_heads(x, batch_size)
```
�ֲ����һ��ά�ȵ� (num_heads, depth). ת�ý��ʹ����״Ϊ (batch_size, num_heads, seq_len, depth)



### call
```python
def call(v, k, q, mask)
```

## class EncoderLayer
### \_\_init\_\_
```python
def __init__(d_model, num_heads, dff, rate)
```

### call
```python
def call(x, training, mask)
```

## class DecoderLayer
### \_\_init\_\_
```python
def __init__(d_model, num_heads, dff, rate)
```

### call
```python
def call(x, enc_output, training, look_ahead_mask, padding_mask)
```

## class Encoder
### \_\_init\_\_
```python
def __init__(num_layers, d_model, num_heads, dff, input_vocab_size, maximum_position_encoding, rate)
```

### call
```python
def call(inputs, training, mask)
```

## class Decoder
### \_\_init\_\_
```python
def __init__(num_layers, d_model, num_heads, dff, target_vocab_size, maximum_position_encoding, rate)
```

### call
```python
def call(x, enc_output, training, look_ahead_mask, padding_mask)
```

## class Transformer
### \_\_init\_\_
```python
def __init__(num_layers, d_model, num_heads, dff, input_vocab_size, target_vocab_size, pe_input, pe_target, rate)
```

### call
```python
def call(inp, tar, training)
```

