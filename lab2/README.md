<h1 align="center">Звіт до лабораторної роботи №2</h1>
<strong>Мета:</strong> отримати навички роботи з масивами.
<h2 align="center">Хід роботи</h2>
<ol>
 <li>До ініціалізованого масиву добавляти випадково генероване число за допомогою методу append(). Повторити операцію 10 000 разів. Зафіксувати програмно час виконання кожної операції append() а також сумарного додавання елементів для 10 000 разів. Визначити середнє значення кожної операції append(). Це саме провести для методу pop(). Провести експеримент 5 разів для кожної операції. Провести операцію для 100, 1000, 10 000, 100 000 елементів масивів. Побудувати графік по отриманих даних.</p> 
 <li>Виконати метод pop() для значення яке знаходиться посередині масиву розмірів визначених в попередніх завданнях. Визначити час виконання методу для цих розмірів масиву (100, 1000, 10 000, 100 000). Побудувати графік по отриманих значеннях.</p> 
 <li>Виконати метод copy() для наступної кількості елементів масиву – 50, 100, 500, 1000, 2000, 5000, 10 000, 50 000, 100 000. Визначити програмний час виконання методу copy() для такої кількості елементів масиву. Побудувати графік по отриманих даних.<br> 
 <p>
   
    import time
    import matplotlib
    import matplotlib.pyplot as plt
    import numpy as np
    import random
   
    masAvr = []
    def get_AP_Time(count):
       masRandom = []
       masTime = []
       masTmp = []
       average = 0
  
    print("---", count, "---")

    print("---append---")
    rndNumber = 1000000
    for item in range(count):
        start = time.time()
        masRandom.append(random.randrange(rndNumber))
        end = time.time()
        dis = end - start
        average += dis
        masTime.append(dis)

    print("Summary time = " + str(average))
    print("Average time = " + str(average/count))

    fig = plt.figure()
    fig.suptitle("append " + str(count), fontsize=20)
    plt.plot(range(count), masTime)
    plt.show()

    masTmp = masTime.copy()

    print("---pop---")

    masTime = []
    for item in range(count):
        start = time.time()
        masRandom.pop()
        end = time.time()
        dis = end - start
        average += dis
        masTime.append(dis)

    print("Summary time = " + str(average))
    print("Average time = " + str(average/count))

    fig = plt.figure()
    fig.suptitle("pop " + str(count), fontsize=20)
    plt.plot(range(count), masTime)
    plt.show()

    start = time.time()
    dis = masTmp.pop(int(count/2))
    end = time.time()
    masAvr.append(dis)
    print("Get average value time = " + str(dis))
    get_AP_Time(100) #100
    get_AP_Time(1000) #1000
    get_AP_Time(10000) #10000
    get_AP_Time(100000) #100000

    fig = plt.figure()
    fig.suptitle("Avr " + str(4), fontsize=20)
    plt.plot(range(len(masAvr)), masAvr)
    plt.show()

    """copy"""
    print("---copy---")
    copyCount = 1000000

    masCopyNumbers = [50, 100, 500, 1000, 2000, 5000, 10000, 50000, 100000]
    masAvrTimeCopy = []

    for x in masCopyNumbers:
    masCopy = random.sample(range(x), x-1)
    start = time.time()
    masCopyTmp = masCopy.copy()
    end = time.time()
    dis = end - start
    print("Copy time for (", x, ") = ", dis)
    masAvrTimeCopy.append(dis)

     print("Summary copy time = ", np.sum(masAvrTimeCopy))

    fig = plt.figure()
    fig.suptitle("copy", fontsize=20)
    plt.plot(masCopyNumbers, masAvrTimeCopy)
    plt.show()
<ol>
<p align="center"><img src="https://github.com/YuriiHoidash/Hoidash_TP-36_-_2020/blob/master/lab2/1.png"></p> 
  <ol>
<p align="center"><img src="https://github.com/YuriiHoidash/Hoidash_TP-36_-_2020/blob/master/lab2/2.png"></p> 
  <ol>
<p align="center"><img src="https://github.com/YuriiHoidash/Hoidash_TP-36_-_2020/blob/master/lab2/3.png"></p>
  <ol>
<p align="center"><img src="https://github.com/YuriiHoidash/Hoidash_TP-36_-_2020/blob/master/lab2/4.png"></p> 
  <ol>
<p align="center"><img src="https://github.com/YuriiHoidash/Hoidash_TP-36_-_2020/blob/master/lab2/5.png"></p> 
  <ol>
<p align="center"><img src="https://github.com/YuriiHoidash/Hoidash_TP-36_-_2020/blob/master/lab2/6.png"></p> 
  <ol>
<p align="center"><img src="https://github.com/YuriiHoidash/Hoidash_TP-36_-_2020/blob/master/lab2/7.png"></p> 
  <ol>
<p align="center"><img src="https://github.com/YuriiHoidash/Hoidash_TP-36_-_2020/blob/master/lab2/8.png"></p> 
  <ol>
<p align="center"><img src="https://github.com/YuriiHoidash/Hoidash_TP-36_-_2020/blob/master/lab2/9.png"></p>
  <ol>
<p align="center"><img src="https://github.com/YuriiHoidash/Hoidash_TP-36_-_2020/blob/master/lab2/10.png"></p> 
  <ol>
<p align="center"><img src="https://github.com/YuriiHoidash/Hoidash_TP-36_-_2020/blob/master/lab2/11.png"></p> 
  <ol>
<p align="center"><img src="https://github.com/YuriiHoidash/Hoidash_TP-36_-_2020/blob/master/lab2/12.png"></p>
    <ol>
<p align="center"><img src="https://github.com/YuriiHoidash/Hoidash_TP-36_-_2020/blob/master/lab2/13.png"></p> 
  <ol>
<p align="center"><img src="https://github.com/YuriiHoidash/Hoidash_TP-36_-_2020/blob/master/lab2/14.png"></p> 
  <ol>
<p align="center"><img src="https://github.com/YuriiHoidash/Hoidash_TP-36_-_2020/blob/master/lab2/15.png"></p> 
  <ol>
<p align="center"><img src="https://github.com/YuriiHoidash/Hoidash_TP-36_-_2020/blob/master/lab2/16.png"></p> 
  <ol>
<p align="center"><img src="https://github.com/YuriiHoidash/Hoidash_TP-36_-_2020/blob/master/lab2/17.png"></p>
  <ol>
<p align="center"><img src="https://github.com/YuriiHoidash/Hoidash_TP-36_-_2020/blob/master/lab2/18.png"></p> 
  <ol>
<p align="center"><img src="https://github.com/YuriiHoidash/Hoidash_TP-36_-_2020/blob/master/lab2/19.png"></p> 
  <ol>
<p align="center"><img src="https://github.com/YuriiHoidash/Hoidash_TP-36_-_2020/blob/master/lab2/20.png"></p> 
   </li>
      </ul>
 </li>
</ol>  
<strong>Висновок:</strong> на цій лабораторній було розглянуто роботу з масивами, а також методи append(), pop(), copy().

