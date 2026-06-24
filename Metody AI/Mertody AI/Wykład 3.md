#### Metryki odległości
https://en.wikipedia.org/wiki/Minkowski_distance
**Euklides** - "w linii prostej", p=2
**Manhattan/Taxicab** - suma różnic na każdej osi, p=1
**Chebyshev** - maksimum różnic na osiach, p→∞

![[Pasted image 20260606120749.png]]
![[Pasted image 20260604000346.png]]

**Minkowskiego** - uogólnienie powyższych, zależy od parametru $p$. Można dać $p$ mniejsze od 1 i wtedy figura jest "wklęsła" - miary ułamkowe. 

![[Pasted image 20260604000411.png]]

Metryka (W TYM KONTEKSCIE!!!) musi spełniać cztery warunki (m.in. nierówność trójkąta). Miara jest luźniejszym pojęciem - nie musi ich wszystkich spełniać.
 
Przy dużej liczbie cech klasyczne metryki tracą sens (curse of dimensionality - wszystkie punkty stają się "jednakowo odległe"). Miary ułamkowe (p<1) lepiej różnicują odległości między wzorcami w takich przestrzeniach.

**Claude wysryw:**
```
4 warunki metryki:

Nieujemność — d(x,y) ≥ 0, odległość nie może być ujemna
Tożsamość — d(x,y) = 0 tylko gdy x = y
Symetria — d(x,y) = d(y,x), odległość z A do B = odległość z B do A
Nierówność trójkąta — d(x,z) ≤ d(x,y) + d(y,z), droga przez pośredni punkt nie może być krótsza niż wprost

Miary ułamkowe (p<1) łamią właśnie warunek 4 — stąd nie są metrykami.
```
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