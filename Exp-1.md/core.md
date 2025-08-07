code :

from keras.models import Sequential
from keras.layers import Dense
import numpy as np
import matplotlib.pyplot as plt

X = np.array([[0,0], [0,1], [1,0], [1,1]])
Y = np.array([[0], [1], [1], [0]])

model = Sequential()
model.add(Dense(4, input_dim=2, activation='relu'))
model.add(Dense(1, activation='sigmoid'))
model.compile(loss='binary_crossentropy', optimizer='adam', metrics=['accuracy'])

history = model.fit(X, Y, epochs=1000, verbose=0)

loss, acc = model.evaluate(X, Y)
print("Accuracy:", acc)

print("Predictions:", model.predict(X))

plt.plot(history.history['loss'])
plt.title('Model Loss')
plt.xlabel('Epoch')
plt.ylabel('Loss')
plt.grid(True)
plt.show()

Output :

<img width="566" height="456" alt="Screenshot 2025-08-07 212528" src="https://github.com/user-attachments/assets/a5631de9-32f7-4353-bd86-c21329d1cec0" />
<img width="1268" height="503" alt="Screenshot 2025-08-07 212352" src="https://github.com/user-attachments/assets/bdbf8982-87bd-4d5e-8739-ee4847c7b972" />
