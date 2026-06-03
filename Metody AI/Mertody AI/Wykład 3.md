Dystans Euklidesa
Dystans Chebysheva/Manhattan
Dystans Taxicab
Dystans Minkowskiego - zależy od parametru $p$. Jeśli p=0 to Euklides, jeśli 2 to Manhattan, jeśli dąży do inf to Chebyshev. Można dać p mniejsze od 0 i wtedy figura jest "wklęsła" - miary ułamkowe. 

Miara a metryka - metryka musi coś spełniać, a miara nie. Miara nie musi spełniać nierówności trójkąta?? To już nie jest metryka odległości ale z tych miar ułamkowych można korzystać. Jeśli ma się zbiory danych wielowymiarowe (dużi cech) to miary ułamkowe są lepsdzym przybliżeniem odległosci między wzorcami?

#### Klasyfikatory
*k-Nearest Neighbours* to klasyfikator leniwy. Liczy się odległosć nowego punktu do całego zestawu treningowego, sprawdza się k najbliższych sąsiadów, patrzy się na ich etykiety, przypisuje się etykietę na tego podstawie. 

Taki klasyfikator można napisać samemu przy pomocy scikit-learn. Wymagany jest w sumie tylko `__init__(), fit(), predict()`.

```python
class kNN(ClassifierMixin, BaseEstimator):
	def __init__(self, k=5, random_state=None):
		self._k = k
		self._random_state = random_state
		self._random = np.random.RandomState(seed=self.random_state)
		self._distance = DistanceMetric.get_metric('euclidean')
	
	def fit(self, X, y):
		self._X, self._y = X, y
		self._labels = np.unique(self._y)
		return self
	
	def predict(self, X):
		distance_matrix = np.sort(self._distance
			.pairwise(X, self._X), axis=1)[:, :self._k]
		
		k_labels = self.y_[distance_matrix]
		preds, _ = mode(k_labels, axis=1)
		
		return preds
		

# --------------

from sklearn.datasets import make_classification # syntetyczne zbiory danych
import matplotlib.pyplot as plt
from sklearn.metrics import accuracy_score

from knn import kNN

X, y = make_classification(n_samples=500, n_features=2, n_informative=2, n_redundant=0, n_repeated=0, random_state=None) # calkiem OK zbiór żeby mieć "pod ręką", prawdziwe eksperymenty robi się na prawdziwych danych

X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.5, random_state=1410)

clf = kNN().fit(X_train, y_train)
pred = clf.predict(X_test)

print(accuracy_score(y_test, pred))

fig, ax = plt.subplots(1, 1, figsize=(10,10))
ax.scatter(X[:, 0], X[:, 1], c=y)

plt.tight_layout()
plt.savefig("test.png")
```