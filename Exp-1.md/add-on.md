Code :

import numpy as np
import matplotlib.pyplot as plt
from sklearn.linear_model import Perceptron
X = np.array([[0,0],[0,1],[1,0],[1,1]])
y = np.array([0,1,1,0])
clf = Perceptron(tol=1e-3, random_state=0)
clf.fit(X, y)
print("Predictions:", clf.predict(X))

for i in range(len(X)):
  if y[i] == 0:
    plt.scatter(X[i][0], X[i][1], color='red')
  else:
    plt.scatter(X[i][0], X[i][1], color='blue')

x_values = [0, 1]
y_values = -(clf.coef_[0][0]*np.array(x_values) + clf.intercept_)/clf.coef_[0][1]
plt.plot(x_values, y_values)
plt.title('Perceptron Decision Boundary for XOR')
plt.show()

Output :

<img width="676" height="450" alt="Screenshot 2025-08-07 212825" src="https://github.com/user-attachments/assets/4a4dba7b-3ad8-4375-bca3-27704c341df4" />
<img width="587" height="359" alt="Screenshot 2025-08-07 212810" src="https://github.com/user-attachments/assets/c696716a-7fe6-4816-a0a3-1a980adebcd1" />
