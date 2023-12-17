# RaspredelennoePO
 Попытка разработать распределённое ПО
 
Эта программа представляет собой простой пример распределенного вычисления, использующего фреймворк Apache Hadoop и его MapReduce модель. Основная задача программы - выполнение операции сложения над набором целых чисел, предоставленных в виде входных данных. Подход MapReduce выбран для демонстрации распределенной обработки данных.
Цель: Программа предназначена для демонстрации, как можно использовать Hadoop для распределенной обработки простых вычислительных задач, таких как сложение чисел.

Входные данные: Программа ожидает входные данные в виде файла, содержащего целые числа. Эти числа могут быть разделены пробелами или расположены на разных строках.

Выходные данные: Результатом работы программы является сумма всех входных чисел, записанная в выходной файл.

## Как Работает Программа
Mapper (TokenizerMapper класс):

Задача: Разбивает входные данные на отдельные числа.
Процесс: Каждая строка входного файла читается отдельно. Строка разделяется на числа (токены).
Вывод: Каждое число отправляется в Reducer с фиксированным ключом "sum" и самим числом в качестве значения.
Reducer (IntSumReducer класс):

Задача: Суммирует все числа, которые были отправлены Mapper'ом.
Процесс: Reducer получает все значения, связанные с ключом "sum", и суммирует их.
Вывод: Итоговая сумма всех чисел записывается в выходной файл.
##Распределенная обработка данных:
При запуске в Hadoop-кластере, Mapper и Reducer могут работать на разных узлах кластера, обеспечивая распределенную обработку.
Hadoop автоматически обрабатывает разбиение входных данных, распределение задач между узлами и сбор результатов.
## Применение:
Эта программа является базовым примером и может быть расширена или модифицирована для более сложных распределенных вычислений. Например, можно добавить поддержку различных математических операций (вычитание, умножение и т.д.), обработку ошибок входных данных и оптимизацию производительности для работы с большими объемами данных.

Mapper: Этот компонент будет получать входные данные и преобразовывать их в пары ключ/значение. В нашем случае ключом будет операция (например, "сложение"), а значением - числа, которые нужно сложить.

Reducer: Этот компонент получает все значения, связанные с определённым ключом, и выполняет соответствующую операцию. Для операции сложения Reducer просто суммирует все значения, связанные с ключом "сложение".

TokenizerMapper разделяет входной текст на отдельные числа и отправляет их в Reducer с ключом "sum".
IntSumReducer суммирует все числа, связанные с ключом "sum", и выводит итоговую сумму.
