# Multithreading
# Multithreading
#First one
import threading
import time

def func1():
    for i in range(3):
        print(f'Raqamlar => {i}')
        time.sleep(4)

def func2():
    for i in 'MSNM':
        print(f'Times => {i}')
        time.sleep(1)

thread1 = threading.Thread(target=func1)
thread2 = threading.Thread(target=func2)

start_time = time.time()
thread1.start()

thread2.start()

thread1.join()
thread2.join()
end_time = time.time()
print(f'Total time => {end_time - start_time}')

#Second one

import time
import threading


def say_hello(name):
    print(f'Wassup {name}')
    time.sleep(1)

def func(n):
    for i in range(1, n):
        print(i ** 3)
        time.sleep(1)

t1 = threading.Thread(target=say_hello, args=('Mirfayz',))
t2 = threading.Thread(target=func, args=(3,))

t1.start()
t2.start()

t1.join()
t2.join()
