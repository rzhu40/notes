```python
# datasets, MNIST for example:
import torchvision
from torchvision import transforms, datasets

# getting data
train = datasets.MNIST("", train = True, download = True,
                      transform = transforms.Compose([transforms.ToTensor()]))
'''
 |  Args:
 |      root (string): Root directory of dataset where ``MNIST/processed/training.pt``
 |          and  ``MNIST/processed/test.pt`` exist.
 |      train (bool, optional): If True, creates dataset from ``training.pt``,
 |          otherwise from ``test.pt``.
 |      download (bool, optional): If true, downloads the dataset from the internet and
 |          puts it in root directory. If dataset is already downloaded, it is not
 |          downloaded again.
 |      transform (callable, optional): A function/transform that  takes in an PIL image
 |          and returns a transformed version. E.g, ``transforms.RandomCrop``
 |      target_transform (callable, optional): A function/transform that takes in the
 |          target and transforms it.
'''

# load data
# usually batch_size of 8-64
trainset = torch.utils.data.DataLoader(train, batch_size = 10, shuffle = True)
'''
 |      batch_size (int, optional): how many samples per batch to load
 |          (default: ``1``).
 |      shuffle (bool, optional): set to ``True`` to have the data reshuffled
 |          at every epoch (default: ``False``).

MNIST data sets are combination of two tensors, first one is an tensor of (1,28,28) tensors, second is just tesnfor of corresponding classes.
MNIST data sets always of shape (1,28,28). Just keep in mind.

'''

# an example of building a network
class Net(nn.Module):
    
    def __init__(self):
        super().__init__()
        self.fc1 = nn.Linear(784, 64)
        self.fc2 = nn.Linear(64, 64)
        self.fc3 = nn.Linear(64, 64)
        self.fc4 = nn.Linear(64, 10)
    
    def forward(self, x):
        x = F.relu(self.fc1(x))
        x = F.relu(self.fc2(x))
        x = F.relu(self.fc3(x))
        x = self.fc4(x)
        
        return F.log_softmax(x, dim = 1)
      
# reshape data and put in
X = x[0].reshape(-1, 784)
output = net(X)

# getting the weight and bias in each layer
net.fc1.weight
net.fc1.bias

# for loss
# when label is vector: MSE
# when it's scalar:
loss = F.nll_loss(output, y)
```

