# PyTorch
* Import using `import torch`
* `torch.manual_seed(n)` set seeds for **random number generation**
* `torch.randn((n1, n2, n3, ...))` return a **random tensor** with dimensions n1, n2,…, mean 0 and variance 1 [doc](https://pytorch.org/docs/stable/torch.html#torch.randn)
* `torch.randn_like(input)` return a random tensor normal distributed with the size of tensor in`input`  [doc](https://pytorch.org/docs/stable/torch.html#torch.randn_like) 
* `torch.mm(tensor1, tensor2)` -> matrix multiplication of two tensors
- - - -
## Torch and Numpy
* `torch.from_numpy(tensor)` -> **transform an array into a tensor** for Torch
* `tensor.numpy()` -> transform a tensor into an array
Memory of the 2 data structures is shared: if one changes the values *in-place* (with a `_` operation) of one object, the other will change as well.
- - - -
## Tensor Manipulation
* `tensor.shape` -> return the **shape of the tensor** in a tuple
* `tensor.reshape(a, b)` -> **reshape** the tensor. *Sometimes it clone the data in another part of the memory and return that. This could result in some inefficiencies.*
* `tensor.resize_(a, b)` -> **reshape** the tensor without cloning the data. But if the new sizes contain a total number of elements that is less than the previous one, some data are lost. The `_` means that the operation is of type “[`in-place`](https://discuss.pytorch.org/t/what-is-in-place-operation/16244)”.
* `tensor.view(a,b)` -> **reshape** the tensor (**suggested**) without messing with memory [doc](https://pytorch.org/docs/stable/tensors.html#torch.Tensor.view)
	1.  `tensor.view(a,-1)` -> the `-1` *flatten* (multiply) all the remaining dimensions
- - - -

- - - -
#code/python/modules