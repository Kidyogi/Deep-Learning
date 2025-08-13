code :

from keras.datasets import mnist 
from keras.models import Sequential 
from keras.layers import Conv2D, MaxPooling2D, Flatten, Dense 
from keras.utils import to_categorical 
(X_train, y_train), (X_test, y_test) = mnist.load_data() 
X_train = X_train.reshape(-1, 28, 28, 1).astype('float32') / 255 
X_test = X_test.reshape(-1, 28, 28, 1).astype('float32') / 255 
y_train = to_categorical(y_train) 
y_test = to_categorical(y_test) 
model = Sequential([ 
  Conv2D(32, (3, 3), activation='relu', input_shape=(28, 28, 1)), 
  MaxPooling2D(pool_size=(2, 2)), 
  Flatten(), 
  Dense(128, activation='relu'), 
  Dense(10, activation='softmax') 
]) 
model.compile(optimizer='adam', loss='categorical_crossentropy', 
metrics=['accuracy']) 
model.fit(X_train, y_train, epochs=5, batch_size=32, validation_data=(X_test, 
y_test))

Output :

<img width="1114" height="246" alt="Screenshot 2025-08-13 110413" src="https://github.com/user-attachments/assets/ad24327d-c934-4af7-a9e1-94a9424ebcc3" />
<img width="609" height="359" alt="Screenshot 2025-08-13 110351" src="https://github.com/user-attachments/assets/adc1f383-0a09-43bc-83f9-4b0e015f8d78" />
