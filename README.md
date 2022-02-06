# Задача о сапёре. 
На плоскости задано прямоугольное поле, разбитое на квадратные клетки: n Х m клеток одинакового размера. По клеткам передвигается сапёр. За секунду дискретного времени он может переместиться из одной клетки в соседнюю. В начальный момент времени сапёр находится в левом нижнем углу. В каждой из клеток может находиться мина. Известно, что находясь в какой-либо клетке с координатами (i,j), сапёр подорвётся с вероятностью Р(i,j) ∈ [0, 1]. Предполагается, что числа Р(i, j) известны заранее (генерируются случайным образом). Целью движения сапёра является переход в правый верхний угол поля, с итоговой максимальной вероятностью выжить при этом.
Для решения задачи используется динамический алгоритм Беллмана. 

Рассматривается два случая движения:
1) Сапёр может двигаться только по горизонтали или вертикали; 
2) В дополнение к предыдущему пункту можно двигаться в соседнюю ячейку по диагонали.

# Функции:
- GenerateTable (n, m) — функция создаёт поле размера n Х m и случайным образом задаёт вероятности Р(i, j). Структуры данных сохранены в рабочей области Matlab для дальнейшего использования. Так же генерируется поле, цветом указываются вероятности Р(i, j) в клетках и выводится шкала соответствия цвета и вероятности.
- SavePrivateRyan(var) — функция решает уравнение Беллмана и определяет максимальную вероятность выжить для сапёра в ходе выполнения своей миссии. В результате на ранее нарисованном поле выводится оптимальный путь сапёра, а числами отображается функция цены в клетках. Например, в начальной точке цена == вероятность выжить на всем пути, а в финальной = 1, т.к. двигаться больше никуда не нужно. Параметр var определяет вариант движения: var  - 0, если можно двигаться только вправо или влево; var - 1, если можно также двигаться по диагонали.
