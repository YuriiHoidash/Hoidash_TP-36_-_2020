<h1 align="center">Звіт до лабораторної роботи №3</h1>
<strong>Мета:</strong> отримати навички роботи з бінарними деревами.
<h2 align="center">Хід роботи</h2>
<ol>
 <li>Написати функцію видалення вузла із бінарного дерева</p> 
<p>
  
    import random
    import time
    import matplotlib
    import matplotlib.pyplot as plt
    import numpy as np

    class Node: 
    def __init__(self, data): 
        self.data = data  
        self.left = None
        self.right = None
  
    def inorder(root): 
    if root is not None: 
        inorder(root.left) 
        print (root.data) 
        inorder(root.right) 
  
    def insert(node, data): 
    if node is None: 
        return Node(data) 
  
    if data < node.data: 
        node.left = insert(node.left, data) 
    else: 
        node.right = insert(node.right, data) 
  
    return node 
  
    def minValueNode(node): 
    current = node 
  
    while(current.left is not None): 
        current = current.left  
  
    return current  
  
    def deleteNode(root, data): 
    if root is None: 
        return root  

    if data < root.data: 
        root.left = deleteNode(root.left, data) 
    elif(data > root.data): 
        root.right = deleteNode(root.right, data) 
  
    else:        
        if root.left is None : 
            temp = root.right  
            root = None 
            return temp  
              
        elif root.right is None : 
            temp = root.left  
            root = None
            return temp 
        temp = minValueNode(root.right) 

        root.data = temp.data 

        root.right = deleteNode(root.right , temp.data) 
  
    return root  

    def getLevel(node, data, level=1): 
    if (node == None): 
        return 0
  
    if (node.data == data) : 
        return level  
  
    downlevel = getLevel(node.left, data, level + 1)  
    if (downlevel != 0) : 
        return downlevel  
  
    downlevel = getLevel(node.right, data, level + 1)  
    return downlevel  
  

    def findval(root, lkpval):
    if lkpval < root.data:
        if root.left is None:
            return None
        return findval(root.left, lkpval)
    elif lkpval > root.data:
        if root.right is None:
            return None
        return findval(root.right, lkpval)
    else:
        return root.data

    ##########################__Work Area__##################################
  
    #""" Let us create following BST 
    #              5 
    #           /     \ 
    #           3      7 
    #         /  \    /  \ 
    #        2    4  6   8 """


    root = None
    root = insert(root, 5) 
    root = insert(root, 3) 
    root = insert(root, 2) 
    root = insert(root, 4) 
    root = insert(root, 7) 
    root = insert(root, 6) 
    root = insert(root, 8) 

    print ("\nInorder traversal of the given tree")
    inorder(root) 

    print ("\nDelete 2")
    root = deleteNode(root, 2) 
    print ("Inorder traversal of the modified tree")
    inorder(root) 

    print ("\nDelete 3")
    root = deleteNode(root, 3) 
    print ("Inorder traversal of the modified tree")
    inorder(root) 

    print ("\nDelete 5")
    root = deleteNode(root, 5) 
    print ("Inorder traversal of the modified tree")
<ol>
<p align="center"><img src="https://github.com/YuriiHoidash/Hoidash_TP-36_-_2020/blob/master/lab3/1.png"></p> 
<li>Написати функцію визначення глибини вузла</p>
<p>
  
    inorder(root);
    import random
    import time
    import matplotlib
    import matplotlib.pyplot as plt
    import numpy as np


    class Node: 
        def __init__(self, data): 
            self.data = data  
            self.left = None
            self.right = None

    def inorder(root): 
        if root is not None: 
            inorder(root.left) 
            print (root.data) 
            inorder(root.right) 

    def insert(node, data): 
        if node is None: 
            return Node(data) 
  
    if data < node.data: 
        node.left = insert(node.left, data) 
    else: 
        node.right = insert(node.right, data) 
  
    return node 
  
    def minValueNode(node): 
    current = node 
  
    while(current.left is not None): 
        current = current.left  
  
    return current  
  
    def deleteNode(root, data): 
    if root is None: 
        return root  

    if data < root.data: 
        root.left = deleteNode(root.left, data) 
    elif(data > root.data): 
        root.right = deleteNode(root.right, data) 
  
    else:        
        if root.left is None : 
            temp = root.right  
            root = None 
            return temp  
              
        elif root.right is None : 
            temp = root.left  
            root = None
            return temp 
        temp = minValueNode(root.right) 

        root.data = temp.data 

        root.right = deleteNode(root.right , temp.data) 
  
    return root  

    def getLevel(node, data, level=1): 
    if (node == None): 
        return 0
  
    if (node.data == data) : 
        return level  
  
    downlevel = getLevel(node.left, data, level + 1)  
    if (downlevel != 0) : 
        return downlevel  
  
    downlevel = getLevel(node.right, data, level + 1)  
    return downlevel  
  

    def findval(root, lkpval):
    if lkpval < root.data:
        if root.left is None:
            return None
        return findval(root.left, lkpval)
    elif lkpval > root.data:
        if root.right is None:
            return None
        return findval(root.right, lkpval)
    else:
        return root.data

    ##########################__Work Area__##################################

    #""" Let us create following BST 
    #              5 
    #           /     \ 
    #           3      7 
    #         /  \    /  \ 
    #        2    4  6   8 """


    root = None
    root = insert(root, 5) 
    root = insert(root, 3)
    root = insert(root, 2) 
    root = insert(root, 4) 
    root = insert(root, 7) 
    root = insert(root, 6) 
    root = insert(root, 8) 


    """ LVL """
    print ("Get Level of a node in a Binary Tree")
    x = 7
    level = getLevel(root, x) 
    if (level) : 
        print("Level of", x, "is", level) 
    else: 
        print(x, "is not present in tree")
  <ol>
<p align="center"><img src="https://github.com/YuriiHoidash/Hoidash_TP-36_-_2020/blob/master/lab3/2.png"></p> 
  <ol>
<p align="center"><img src="https://github.com/YuriiHoidash/Hoidash_TP-36_-_2020/blob/master/lab3/3.png"></p> 
    <li>Згенерувати бінарні дерева на 100, 1000, 10000, 100000 елементів. Визначити час виконання функцій вставки, і пошуку для бінарного дерева. Провести експеримент 5 разів для кожної функції. Побудувати графік по отриманих значеннях</p>
  <h2 align="center">Для 100:</h2>
  <p>
    
    import random
    import time
    import matplotlib
    import matplotlib.pyplot as plt
    import numpy as np


    class Node: 
        def __init__(self, data): 
            self.data = data  
            self.left = None
            self.right = None

    def inorder(root): 
        if root is not None: 
            inorder(root.left) 
            print (root.data) 
            inorder(root.right) 

    def insert(node, data): 
        if node is None: 
            return Node(data) 
  
    if data < node.data: 
        node.left = insert(node.left, data) 
    else: 
        node.right = insert(node.right, data) 
  
    return node 
  
    def minValueNode(node): 
    current = node 
  
    while(current.left is not None): 
        current = current.left  
  
    return current  
  
    def deleteNode(root, data): 
    if root is None: 
        return root  

    if data < root.data: 
        root.left = deleteNode(root.left, data) 
    elif(data > root.data): 
        root.right = deleteNode(root.right, data) 
  
    else:        
        if root.left is None : 
            temp = root.right  
            root = None 
            return temp  
              
        elif root.right is None : 
            temp = root.left  
            root = None
            return temp 
        temp = minValueNode(root.right) 

        root.data = temp.data 

        root.right = deleteNode(root.right , temp.data) 
  
    return root  

    def getLevel(node, data, level=1): 
    if (node == None): 
        return 0
  
    if (node.data == data) : 
        return level  
  
    downlevel = getLevel(node.left, data, level + 1)  
    if (downlevel != 0) : 
        return downlevel  
  
    downlevel = getLevel(node.right, data, level + 1)  
    return downlevel  
  

    def findval(root, lkpval):
    if lkpval < root.data:
        if root.left is None:
            return None
        return findval(root.left, lkpval)
    elif lkpval > root.data:
        if root.right is None:
            return None
        return findval(root.right, lkpval)
    else:
        return root.data

    """ 100 """
    quantity = 5
    arrInsertTimes = []
    arrFindTimes = []

    count = 100 + 1
    print("--- ", count - 1, " ---")
    items = random.sample(range(count), count-1)
    for q in range(quantity) :
        print(q+1)

    root = None

    """Insert"""
    for item in items:
        startTime = time.time()

        root = insert(root, item)

        endTime = time.time()
    dis = endTime - startTime 
    arrInsertTimes.append(dis)

    """Find"""
    print ("\nFind value of the tree")
    x = random.randrange(count-1)
    startTime = time.time()
    val = findval(root, x)
    endTime = time.time()

    if(val) : 
        print(val, "is found")
    else :
        print("Value (", x,") not found")
    dis = endTime - startTime
    print("Find func time execution =", dis)

    arrFindTimes.append(dis)

    fig = plt.figure()
    fig.suptitle("Insert Times ", fontsize=20)
    plt.plot(range(1, quantity+1), arrInsertTimes)
    plt.show()

    fig = plt.figure()
    fig.suptitle("Find Times ", fontsize=20)
    plt.plot(range(1, quantity+1), arrFindTimes)
    plt.show()
   <ol>
<p align="center"><img src="https://github.com/YuriiHoidash/Hoidash_TP-36_-_2020/blob/master/lab3/4.png"></p> 
  <ol>
<p align="center"><img src="https://github.com/YuriiHoidash/Hoidash_TP-36_-_2020/blob/master/lab3/5.png"></p> 
  <ol>
<p align="center"><img src="https://github.com/YuriiHoidash/Hoidash_TP-36_-_2020/blob/master/lab3/6.png"></p> 
     <h2 align="center">Для 1000:</h2>
  <p>
    
    import random
    import time
    import matplotlib
    import matplotlib.pyplot as plt
    import numpy as np


    class Node: 
    def __init__(self, data): 
        self.data = data  
        self.left = None
        self.right = None
  
    def inorder(root): 
    if root is not None: 
        inorder(root.left) 
        print (root.data) 
        inorder(root.right) 
  
    def insert(node, data): 
    if node is None: 
        return Node(data) 
  
    if data < node.data: 
        node.left = insert(node.left, data) 
    else: 
        node.right = insert(node.right, data) 
  
    return node 
  
    def minValueNode(node): 
    current = node 
  
    while(current.left is not None): 
        current = current.left  
  
    return current  
  
    def deleteNode(root, data): 
    if root is None: 
        return root  

    if data < root.data: 
        root.left = deleteNode(root.left, data) 
    elif(data > root.data): 
        root.right = deleteNode(root.right, data) 
  
    else:        
        if root.left is None : 
            temp = root.right  
            root = None 
            return temp  
              
        elif root.right is None : 
            temp = root.left  
            root = None
            return temp 
        temp = minValueNode(root.right) 

        root.data = temp.data 

        root.right = deleteNode(root.right , temp.data) 
  
    return root  

    def getLevel(node, data, level=1): 
    if (node == None): 
        return 0
  
    if (node.data == data) : 
        return level  
  
    downlevel = getLevel(node.left, data, level + 1)  
    if (downlevel != 0) : 
        return downlevel  
  
    downlevel = getLevel(node.right, data, level + 1)  
    return downlevel  
  

    def findval(root, lkpval):
        if lkpval < root.data:
            if root.left is None:
                return None
            return findval(root.left, lkpval)
        elif lkpval > root.data:
            if root.right is None:
                return None
            return findval(root.right, lkpval)
        else:
            return root.data

    """ 1000 """
    quantity = 5
    arrInsertTimes = []
    arrFindTimes = []

    count = 1000 + 1
    print("--- ", count - 1, " ---")
    items = random.sample(range(count), count-1)
    for q in range(quantity) :
        print(q+1)

    root = None

    """Insert"""
    for item in items:
        startTime = time.time()

        root = insert(root, item)

        endTime = time.time()
    dis = endTime - startTime 
    arrInsertTimes.append(dis)

    """Find"""
    print ("\nFind value of the tree")
    x = random.randrange(count-1)
    startTime = time.time()
    val = findval(root, x)
    endTime = time.time()

    if(val) : 
        print(val, "is found")
    else :
        print("Value (", x,") not found")
    dis = endTime - startTime
    print("Find func time execution =", dis)

    arrFindTimes.append(dis)

    fig = plt.figure()
    fig.suptitle("Insert Times ", fontsize=20)
    plt.plot(range(1, quantity+1), arrInsertTimes)
    plt.show()

    fig = plt.figure()
    fig.suptitle("Find Times ", fontsize=20)
    plt.plot(range(1, quantity+1), arrFindTimes)
    plt.show()
  
  <ol>
<p align="center"><img src="https://github.com/YuriiHoidash/Hoidash_TP-36_-_2020/blob/master/lab3/7.png"></p> 
  <ol>
<p align="center"><img src="https://github.com/YuriiHoidash/Hoidash_TP-36_-_2020/blob/master/lab3/8.png"></p> 
  <ol>
<p align="center"><img src="https://github.com/YuriiHoidash/Hoidash_TP-36_-_2020/blob/master/lab3/9.png"></p> 
     <h2 align="center">Для 10000:</h2>
  <p>
    
    import random
    import time
    import matplotlib
    import matplotlib.pyplot as plt
    import numpy as np


    class Node: 
    def __init__(self, data): 
        self.data = data  
        self.left = None
        self.right = None
  
    def inorder(root): 
    if root is not None: 
        inorder(root.left) 
        print (root.data) 
        inorder(root.right) 
  
    def insert(node, data): 
    if node is None: 
        return Node(data) 
  
    if data < node.data: 
        node.left = insert(node.left, data) 
    else: 
        node.right = insert(node.right, data) 
  
    return node 
  
    def minValueNode(node): 
    current = node 
  
    while(current.left is not None): 
        current = current.left  
  
    return current  
  
    def deleteNode(root, data): 
    if root is None: 
        return root  

    if data < root.data: 
        root.left = deleteNode(root.left, data) 
    elif(data > root.data): 
        root.right = deleteNode(root.right, data) 
  
    else:        
        if root.left is None : 
            temp = root.right  
            root = None 
            return temp  
              
        elif root.right is None : 
            temp = root.left  
            root = None
            return temp 
        temp = minValueNode(root.right) 

        root.data = temp.data 

        root.right = deleteNode(root.right , temp.data) 
  
    return root  

    def getLevel(node, data, level=1): 
    if (node == None): 
        return 0
  
    if (node.data == data) : 
        return level  
  
    downlevel = getLevel(node.left, data, level + 1)  
    if (downlevel != 0) : 
        return downlevel  
  
    downlevel = getLevel(node.right, data, level + 1)  
    return downlevel  
  

    def findval(root, lkpval):
    if lkpval < root.data:
        if root.left is None:
            return None
        return findval(root.left, lkpval)
    elif lkpval > root.data:
        if root.right is None:
            return None
        return findval(root.right, lkpval)
    else:
        return root.data

    """ 10000 """
    quantity = 5
    arrInsertTimes = []
    arrFindTimes = []

    count = 10000 + 1
    print("--- ", count - 1, " ---")
    items = random.sample(range(count), count-1)
    for q in range(quantity) :
    print(q+1)

    root = None

    """Insert"""
    for item in items:
        startTime = time.time()

        root = insert(root, item)

        endTime = time.time()
    dis = endTime - startTime 
    arrInsertTimes.append(dis)

    """Find"""
    print ("\nFind value of the tree")
    x = random.randrange(count-1)
    startTime = time.time()
    val = findval(root, x)
    endTime = time.time()

    if(val) : 
        print(val, "is found")
    else :
        print("Value (", x,") not found")
    dis = endTime - startTime
    print("Find func time execution =", dis)

    arrFindTimes.append(dis)

    fig = plt.figure()
    fig.suptitle("Insert Times ", fontsize=20)
    plt.plot(range(1, quantity+1), arrInsertTimes)
    plt.show()

    fig = plt.figure()
    fig.suptitle("Find Times ", fontsize=20)
    plt.plot(range(1, quantity+1), arrFindTimes)
    plt.show()
<ol>
<p align="center"><img src="https://github.com/YuriiHoidash/Hoidash_TP-36_-_2020/blob/master/lab3/10.png"></p> 
  <ol>
<p align="center"><img src="https://github.com/YuriiHoidash/Hoidash_TP-36_-_2020/blob/master/lab3/11.png"></p> 
  <ol>
<p align="center"><img src="https://github.com/YuriiHoidash/Hoidash_TP-36_-_2020/blob/master/lab3/12.png"></p> 
     <h2 align="center">Для 100000:</h2>
  <p>
    
    import random
    import time
    import matplotlib
    import matplotlib.pyplot as plt
    import numpy as np


    class Node: 
    def __init__(self, data): 
        self.data = data  
        self.left = None
        self.right = None
  
    def inorder(root): 
    if root is not None: 
        inorder(root.left) 
        print (root.data) 
        inorder(root.right) 
  
    def insert(node, data): 
    if node is None: 
        return Node(data) 
  
    if data < node.data: 
        node.left = insert(node.left, data) 
    else: 
        node.right = insert(node.right, data) 
  
    return node 
  
    def minValueNode(node): 
    current = node 
  
    while(current.left is not None): 
        current = current.left  
  
    return current  
  
    def deleteNode(root, data): 
    if root is None: 
        return root  

    if data < root.data: 
        root.left = deleteNode(root.left, data) 
    elif(data > root.data): 
        root.right = deleteNode(root.right, data) 
  
    else:        
        if root.left is None : 
            temp = root.right  
            root = None 
            return temp  
              
        elif root.right is None : 
            temp = root.left  
            root = None
            return temp 
        temp = minValueNode(root.right) 

        root.data = temp.data 

        root.right = deleteNode(root.right , temp.data) 
  
    return root  

    def getLevel(node, data, level=1): 
    if (node == None): 
        return 0
  
    if (node.data == data) : 
        return level  
  
    downlevel = getLevel(node.left, data, level + 1)  
    if (downlevel != 0) : 
        return downlevel  
  
    downlevel = getLevel(node.right, data, level + 1)  
    return downlevel  
  

    def findval(root, lkpval):
    if lkpval < root.data:
        if root.left is None:
            return None
        return findval(root.left, lkpval)
    elif lkpval > root.data:
        if root.right is None:
            return None
        return findval(root.right, lkpval)
    else:
        return root.data

    """ 100000 """
    quantity = 5
    arrInsertTimes = []
    arrFindTimes = []

    count = 100000 + 1
    print("--- ", count - 1, " ---")
    items = random.sample(range(count), count-1)
    for q in range(quantity) :
    print(q+1)

    root = None

    """Insert"""
    for item in items:
        startTime = time.time()

        root = insert(root, item)

        endTime = time.time()
    dis = endTime - startTime 
    arrInsertTimes.append(dis)

    """Find"""
    print ("\nFind value of the tree")
    x = random.randrange(count-1)
    startTime = time.time()
    val = findval(root, x)
    endTime = time.time()

    if(val) : 
        print(val, "is found")
    else :
        print("Value (", x,") not found")
    dis = endTime - startTime
    print("Find func time execution =", dis)

    arrFindTimes.append(dis)

    fig = plt.figure()
    fig.suptitle("Insert Times ", fontsize=20)
    plt.plot(range(1, quantity+1), arrInsertTimes)
    plt.show()

    fig = plt.figure()
    fig.suptitle("Find Times ", fontsize=20)
    plt.plot(range(1, quantity+1), arrFindTimes)
    plt.show()
<ol>
<p align="center"><img src="https://github.com/YuriiHoidash/Hoidash_TP-36_-_2020/blob/master/lab3/13.png"></p> 
  <ol>
<p align="center"><img src="https://github.com/YuriiHoidash/Hoidash_TP-36_-_2020/blob/master/lab3/14.png"></p> 
  <ol>
<p align="center"><img src="https://github.com/YuriiHoidash/Hoidash_TP-36_-_2020/blob/master/lab3/15.png"></p> 
     </li>
      </ul>
 </li>
</ol>  
<strong>Висновок:</strong> на цій лабораторній було розглянуто бінарне дерево та операції над ним.
