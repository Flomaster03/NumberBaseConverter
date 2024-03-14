1_4

Convert decimals
Description
In daily life, we mostly use the decimal numeral system, but still, there are many other ways to represent numbers. For example, when working with computers, you'll probably deal with binary, octal, and hexadecimal numbers. It's really nice to have a tool that can help you easily and correctly convert numbers from one system to another: in this project, we will build such a tool step-by-step.

In the first stage, you need to implement conversion from decimal to binary, octal, and hexadecimal. The program will read the user's decimal number and the user's target radix (or base). Then, it will output the given number in the corresponding base.

Converting from decimal to octal and hexadecimal isn't much different from converting to binary. The algorithm is really similar to binary conversion, only the base number is different with 8 or 16 in place of 2. See some examples of converting the number 110 from decimal to octal and hexadecimal below:

Quotient	Remainder of 8
110	6
13	5
1	1
Result: 
11
0
10
=
15
6
8
110 
10
​
 =156 
8
​
 

Quotient	Remainder of 16
110	14 (E)
6	6
Result: 
11
0
10
=
6
�
16
110 
10
​
 =6E 
16
​
 

In this project, you need to understand and implement the conversion algorithm.
Objectives
Your program's output should consist of the following three lines:

On the first line, the prompt Enter number in decimal system: is shown, and the user inputs a decimal number to be converted.
On the second one, the prompt Enter target base: is printed, and the user enters the target base (2, 8, or 16).
On the third one, the message Conversion result: is printed, followed by the correct number representation in the given base.
Example
The greater-than symbol followed by a space (> ) represents the user input. Note that it's not part of the input.

Example 1:

Enter number in decimal system: > 8
Enter target base: > 16
Conversion result: 8
Example 2:

Enter number in decimal system: > 101
Enter target base: > 2
Conversion result: 1100101
Example 3:

Enter number in decimal system: > 103
Enter target base: > 8
Conversion result: 147

2_4

Преобразовать в десятичное число
Описание
В этот момент пользователю необходимо каждый раз перезапускать программу после преобразования всего одного числа, что очень неудобно. Давайте исправим это и сделаем так, чтобы ваша программа запрашивала у пользователя дополнительные цифры, пока пользователь не будет готов выйти.

Также мы добавим обратное преобразование: из двоичной, восьмеричной и шестнадцатеричной систем в десятичную. Преобразование восьмеричной, шестнадцатеричной или любой другой системы в десятичную работает почти так же, как и с двоичными числами, только основание другое. Посмотреть на себя:

172
6
8
=
1
∗
512
+
7
∗
64
+
2
∗
8
+
6
∗
1
=
98
2
10
1726 
8
​
 =1∗512+7∗64+2∗8+6∗1=982 
10
​
 

А
3
С
16
=
1
0
∗
256
+
3
∗
1
6
+
12
∗
1
=
262
0
1
0
А 3 С 
16
​
 =10∗256+3∗16+12∗1=2620 
10
​
 

В этом проекте вам необходимо понять и реализовать алгоритм преобразования. Не пытайтесь найти готовые функции, которые дадут вам результат, но не требуют понимания алгоритма. Вы узнаете больше, если реализуете это самостоятельно!
Цели
Ваша программа должна вывести подсказку Do you want to convert /from decimal or /to decimal? (To quit type /exit), подсказывающую пользователю следующий шаг. Возможные команды /from: , /toи /exit.

Если пользователь вводит /from, программа должна вести себя так же, как на предыдущем этапе, и преобразовать число пользователя из десятичной системы в двоичную, восьмеричную или шестнадцатеричную.
Если пользователь вводит /to, программа должна:
Распечатайте приглашение Enter source number:и прочитайте введенное пользователем число, которое необходимо преобразовать в десятичное число.
Распечатайте подсказку Enter source base: и прочитайте целевую базу (2, 8 или 16).
Выведите сообщение Conversion to decimal result:, за которым следует представление числа в десятичной системе.
Если пользователь вводит /exit, программа останавливается. В противном случае он должен обработать команду и запросить следующую.
Примеры
Символ «больше», за которым следует пробел ( > ), представляет ввод пользователя. Обратите внимание, что это не часть ввода.

Пример 1:

Do you want to convert /from decimal or /to decimal? (To quit type /exit) > /from
Enter a number in decimal system: > 8
Enter the target base: > 16
Conversion result: 8

Do you want to convert /from decimal or /to decimal? (To quit type /exit) > /from
Enter a number in decimal system: > 101
Enter the target base: > 2
Conversion result: 1100101

Do you want to convert /from decimal or /to decimal? (To quit type /exit) > /from
Enter a number in decimal system: > 103
Enter the target base: > 8
Conversion result: 147

Do you want to convert /from decimal or /to decimal? (To quit type /exit) > /exit

3_4

Конвертируем в любую базу
Описание
В идеале мы хотим конвертировать числа в разные системы счисления, а не только из десятичной системы или в нее. На этом этапе мы добавим поддержку преобразования чисел из любой исходной базы в любую целевую базу. Поскольку латинских букв 26 и цифр 10, максимальная база равна 26 + 10 = 36. Таким образом, целевая и исходная база будут находиться в диапазоне от 2 до 36.

Также нашим пользователям было бы удобнее, если бы программа не запрашивала базу перед каждым преобразованием, а запоминала ранее введенную базу. Таким образом, пользователям придется гораздо меньше печатать, когда им нужно преобразовать группу чисел из базы А в базу Б.

Чтобы преобразовать число из исходной системы счисления в целевую систему счисления, необходимо сначала преобразовать его в десятичную систему, а затем преобразовать десятичное число в целевую систему счисления.

Обратите внимание, что начиная с этого этапа числа могут оказаться больше, чем вы ожидаете, поэтому вам следует использовать BigIntegerвместо Intили Longво избежание ошибок.

Цели
Ваша программа должна иметь двухуровневое меню:

На первом уровне пользователь видит следующую подсказку: Enter two numbers in format: {source base} {target base} (To quit type /exit). Затем они вводят два числа, разделенные одним пробелом: исходную базу и целевую базу. Пользователь также имеет возможность использовать /exitкоманду для выхода из программы.
На втором уровне пользователь видит еще одно приглашение: Enter number in base {user source base} to convert to base {user target base} (To go back type /back)и вводит число в исходной базе. Программа выводит сообщение Conversion result:, за которым следует число в целевой базе. Затем программа запрашивает новое число для преобразования из ранее предоставленной исходной базы в целевую базу. Для изменения баз пользователь может выбрать BACKкоманду и вернуться в меню первого уровня для внесения необходимых изменений.
Пример
Символ «больше», за которым следует пробел ( > ), представляет ввод пользователя. Обратите внимание, что это не часть ввода.

Enter two numbers in format: {source base} {target base} (To quit type /exit) > 10 2
Enter number in base 10 to convert to base 2 (To go back type /back) > 11
Conversion result: 1011

Enter number in base 10 to convert to base 2 (To go back type /back) > 18
Conversion result: 10010

Enter number in base 10 to convert to base 2 (To go back type /back) > 127
Conversion result: 1111111

Enter number in base 10 to convert to base 2 (To go back type /back) > 189344562689000108753301247
Conversion result: 1001110010011111010001010100111110001111101101011010101101001001111110100010111011111111

Enter number in base 10 to convert to base 2 (To go back type /back) > /back

Enter two numbers in format: {source base} {target base} (To quit type /exit) > 36 10
Enter number in base 36 to convert to base 10 (To go back type /back) > abcde
Conversion result: 17325410

Enter number in base 36 to convert to base 10 (To go back type /back) > 13a0
Conversion result: 50904

Enter number in base 36 to convert to base 10 (To go back type /back) > az
Conversion result: 395

Enter number in base 36 to convert to base 10 (To go back type /back) > /back

Enter two numbers in format: {source base} {target base} (To quit type /exit) > /exit

4_4

Преобразование дробей
Описание
Дробные числа также можно переводить из одной системы счисления в другую, поэтому давайте добавим эту возможность в нашу программу!

Чтобы перевести дробное число из одного основания в другое, нужно разделить число на две части: целую и дробную. Преобразуйте каждую часть из их основы в десятичную независимо, а затем преобразуйте их (еще раз отдельно) в целевую базу. Наконец, объедините обе части и получите конечный результат!

Самой сложной частью, вероятно, будет преобразование десятичной дробной части в целевую основу. Однако не волнуйтесь: поскольку вы уже знаете, как переводить дроби из десятичных в двоичные, это не должно стать для вас проблемой! Преобразование дробей из десятичной дроби в любое основание практически одинаково: просто используйте правильный знаменатель, который является целевым основанием, вместо2.

В приведенном ниже примере показано, как преобразовать число 0,375 из десятичной системы счисления в систему счисления по основанию 20:

Дробный	Целое число
0,375 * 20 =	7 + 0,5
0,5 * 20 =	10 + 0,0
Результат:
0
.
3
7
5
1
0
"="
0
.
7
а
2
0
0,37 5 
10
​
 "="0,7 а 
20
​
 

Как и на предыдущем этапе, входные числа могут быть большими. Возможно, вы захотите рассмотреть возможность использования java.math.BigDecimalдля обработки больших дробей.

Цели
Ваша программа должна вести себя почти так же, как и на предыдущем этапе: двухуровневое меню и команды остаются прежними.

Когда ваша программа получает дробное число, она должна выводить его представление в целевой базе, округленное до 5 символов (цифр или букв) в дробной части. Если в исходном числе нет дробной части, то ее следует опустить и в результирующем числе.

Пример
Символ «больше», за которым следует пробел ( > ), представляет ввод пользователя. Обратите внимание, что это не часть ввода.

Enter two numbers in format: {source base} {target base} (To quit type /exit) > 10 7
Enter number in base 10 to convert to base 7 (To go back type /back) > 0.234
Conversion result: 0.14315

Enter number in base 10 to convert to base 7 (To go back type /back) > 10.234
Conversion result: 13.14315

Enter number in base 10 to convert to base 7 (To go back type /back) > /back

Enter two numbers in format: {source base} {target base} (To quit type /exit) > 35 17
Enter number in base 35 to convert to base 17 (To go back type /back) > af.xy
Conversion result: 148.g88a8

Enter number in base 35 to convert to base 17 (To go back type /back) > aaaa.0
Conversion result: 54e36.00000

Enter number in base 35 to convert to base 17 (To go back type /back) > /back

Enter two numbers in format: {source base} {target base} (To quit type /exit) > 21 10
Enter number in base 21 to convert to base 10 (To go back type /back) > 4242
Conversion result: 38012

Enter number in base 21 to convert to base 10 (To go back type /back) > 4242.13a
Conversion result: 38012.05550

Enter number in base 21 to convert to base 10 (To go back type /back) > /back

Enter two numbers in format: {source base} {target base} (To quit type /exit) > /exit
