<h1 align="center">Звіт до лабораторної роботи №4-5</h1>
<strong>Мета:</strong> отримати навички роботи з масивами.
<h2 align="center">Хід роботи</h2>
<h2 align="center">Лабораторна робота №4</h2>
<ol>
<li>Опис алгоритму сортування</p>
Сортування обміном або сортування бульбашкою є простим алгоритмом сортування. Алгоритм працює таким чином — у поданому наборі даних (списку чи масиві) порівнюються два сусідні елементи. Якщо один з елементів, не відповідає критерію сортування (є більшим, або ж, навпаки, меншим за свого сусіда), то ці два елементи міняються місцями. Прохід по списку продовжується доти, доки дані не будуть відсортованими.</p>
<li>Реалізація алгоритму</p>
  <ol>
<p align="center"><img src="https://github.com/YuriiHoidash/Hoidash_TP-36_-_2020/blob/master/lab4-5/1.png"></p> 
  <ol>
<p align="center"><img src="https://github.com/YuriiHoidash/Hoidash_TP-36_-_2020/blob/master/lab4-5/2.jpg"></p> 
  <ol>
<p align="center"><img src="https://github.com/YuriiHoidash/Hoidash_TP-36_-_2020/blob/master/lab4-5/3.png"></p>
<h2 align="center">Лабораторна робота №5</h2>
<ol>
</p>
    
    letters = 'abcdefghijklmnopqrstuvwxyz'
    letters_count = len(letters)

    def encrypt(n, plaintext):
    result = ''

    for l in plaintext.lower():
        try:
            i = (letters.index(l) + n) % letters_count
            result += letters[i]
        except ValueError:
            result += l

    return result.lower()

    def decrypt(n, ciphertext):
    result = ''

    for l in ciphertext:
        try:
            i = (letters.index(l) - n) % letters_count
            result += letters[i]
        except ValueError:
            result += l

    return result

    text = "hello world"
    offset = 5

    encrypted = encrypt(offset, text)
    print('Encrypted:', encrypted)

    for key in range(letters_count):
    decrypted = decrypt(key, encrypted)
    print('Decrypted:', decrypted)
    
   <ol>
<p align="center"><img src="https://github.com/YuriiHoidash/Hoidash_TP-36_-_2020/blob/master/lab4-5/4.jpg"></p> 
   </li>
      </ul>
 </li>
</ol>  
<strong>Висновок:</strong> на цій лабораторній було розглянуто роботу алгоритмів сортування.
