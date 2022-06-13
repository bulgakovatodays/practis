# Cascading Style Sheets (CSS) 
CSS — каскадные таблицы стилей, которые позволяют оформлять содержимое страницы в соответствии с описанными правилами.

## Подключение:
1) атрибутом style внутри тега (пример - <div style="font-size:20px">
2) тегом <style>(пар) в <head>. В таком случае внутри тега прописывается информация по правилу:
> имя_тега (он же селектор) {
> свойство: значение;
> } 
3) отдельным файлом "__.css" Подключается мета-тегом <link>(ссылкой)

**Селектор** — это описание того, к чему нужно применить тот или иной стиль CSS:
 - селектор .название-класса
 - селектор .название-класса.название-класса (для объекта с двумя классами сразу)
 - селектор # идентификатор (название) конкретного блока

Синтаксис правил один - " селектор {название-свойства: значение;} "

## СВОЙСТВА
### ТЕКСТ
**font-style** - свойство изменяет наклон текста (a la курсив), возможные значения:
- normal — обычный вывод текста.
- italic — курсивное начертание (стандарт)
- oblique — косое начертание
  
**font-variant** - возможность капители (вид строчных букв почти совпадает к размеру заглавных ), значения:
- normal — нормальное написание текста
- small-caps — капитель
  
**font-weight** -- начертание текста, может быть от 100 до 900
- bold (=700) -- насыщенный шрифт. Внешне текст будет выглядеть так же, как и при использовании тега < strong > или < b >
- normal (=400) — значение по умолчанию. Полезное значение, если весь текст имеет нестандартную насыщенность, но какой-то участок необходимо сделать стандартным по насыщенности
  
**font-size** - размер шрифта (указывается число и единица измерения без пробела, например "5px")
  
**line-height** -- Межстрочный интервал (интерлиньяж)
  
**font-family** - тип шрифта. Можно подгрузить из https://fonts.google.com . 
  Хорошим тоном является подгрузка в качестве запасного универсального семейства шрифта (последним в строке font-family):
-	serif — шрифты с засечками (антиквы) [пример Times New Roman]; 
-	sans-serif — шрифты без засечек (гротеск) [пример Arial и Verdana]; 
-	cursive — курсивные шрифты
-	fantasy — декоративные шрифты. Это семейство используется реже всего. Дело в том, что декоративные шрифты слишком разные, чтобы они были взаимозаменяемые
-	monospace — моноширинные шрифты. К ним относятся шрифты, в которых все символы имеют одинаковую ширину. Очень часто их используют программисты в текстовых редакторах
  Блок правил font можно записать в одну строку, в следующем порядке: (1) font-style; (2)  font-variant; (3) font-weight; (4-5) font-size [обяз]/ line-height (эти два правила записываются через слэш); (6) font-family [обяз].
  То есть вначале идут стилистические правила, затем размер шрифта и его межстрочный интервал и потом семейство шрифта! [пример: font: italic bold 24px Arial, sans-serif;]

### ЦВЕТ
  **color:** - цвет (является наследуемым, поэтому цвет будет установлен для всех текстовых элементов блока)
  
  **background-color** - фоновый цвет
  
  **border-color** — цвет границы
 
  **box-shadow** - тень для элемента
  
  Цвет может обозначаться тремя способами:
1)	словом: red, brown, white…
2)	6 буквами: # FFFFFF, # 000000 
3)	"rgba" - способ описания цвета по формуле "красный, зеленый, синий, прозрачность (0-1, десятичные - через точку). Пример: [background-color: rgba(255, 0, 255, 0.5); -- полупрозрачный фиолетовый фон]

### РАЗМЕРЫ и РАЗМЕЩЕНИЕ БЛОКОВ
**text-align** -- выравнивание с 4 основными значениями:
- left — по левому краю. Используется по умолчанию
- center — по центру
- right — по правому краю
- justify — по ширине

**width** — ширина блока
  
  **height** — высота блока
  
  Правило **box-sizing**, которое принимает следующие значения:
- content-box — значение по умолчанию. В этом случае свойства width/height обозначают то, что находится внутри padding.
- border-box — Значения width/height задают высоту/ширину всего элемента. В таком случае значения границы и внутренних отступов не увеличивают элемент, а «съедают» место у контента, то есть свойства не будут влиять и высоту и ширину. Если установлено фиксированное значение, то оно таким и останется, но для контента внутри останется меньше места

**padding**  - внутренний отступ со всех сторон (отступы вокруг текста):
- padding-top — внутренний отступ сверху
- padding-right — внутренний отступ справа
- padding-bottom — внутренний отступ снизу
- padding-left — внутренний отступ слева
Порядок указания важен и соответствует тому, как он указан выше!
Пример: [padding: 10px 0 10px 20px;] 

**border** - рамка вокруг элемента, может делиться на несколько свойств:
- border-width — ширина границы
- border-style — стиль границы (их восемь: dotted - пунктирная; dashed - штриховая; solid - сплошная; double - "двойной"; groove - "канавка"; ridge - "хребет"; inset - "вставка"; outset - "начало")
- border-color — цвет границы
В одну строку записывается в том же порядке: [1px solid #000;]

**margin** - внешний отступ от блока:
•	margin-top — внешний отступ сверху
•	margin-right — внешний отступ справа
•	margin-bottom — внешний отступ снизу
•	margin-left — внешний отступ слева
Последовательность важна! Пример: [margin: 10px 0 10px 20px;] 

**Сокращённые записи этих правил:**
1) если указать только одно значение, то оно будет использовано одновременно для всех сторон
2) если указать два значения, то первое будет использоваться для отступов по вертикали (сверху и снизу), а второе по горизонтали (справа и слева)
3) если указать три значения, то они будут использоваться для отступа сверху, по горизонтали и снизу

Кроме пикселей **размеры можно выразить в относительных единицах:**
- проценты (например относительно размера шрифта в теге. Пример: .news h2 { font-size: 200%; }
- em. (относительно размера шрифта у родительского элемента, т.е. 1.5em будет на 50% больше базового вычисленного размера шрифта родителя)
- rem. (относительно размера шрифта у корневого элемента, т.е. у тега html (значение по-умолчанию 16px)
* значение "none" - отменяет ранее установленное свойство

## ПРИОРИТЕТЫ
Правила, определяющие приоритеты стилей из разных источников. По степени важности список выглядит следующим образом:
- Стили в атрибуте тега
- Стили в отдельном файле
- Стили по умолчанию, которые добавляет браузер
Значения, указанные в атрибуте style будут важнее свойств в теге <style>, а они будут важнее стандартных стилей браузера.

Cселекторы в следующем порядке по приоритету:
1. Селектор по идентификатору (#blue)
2. Селектор по классу (.red)
3. Селектор по тегу (p)

Cвойства, которые ещё полностью не поддерживаются и не являются частью стандарта обозначают специальными конструкциями — префиксами. 

## Правила ТИПОГРАФИКИ
1. Используйте стандартные шрифты. Например Arial, Verdana, Tahoma, Times New Roman и так далее.
2. Используйте не больше двух шрифтов на странице. Например: один - для заголовков, а другой для текста.
3. Используйте достаточный размер шрифта (не меньше 14 пикселей)
4. Используйте достаточный межстрочный интервал. Стандарт: размер интервала = 150% от размера шрифта. Пример: если текст размером 14 пикселей, то межстрочный интервал = 21 пиксель.
5. Выравнивайте текст по левому краю

## БОЛЕЕ СЛОЖНЫЕ КОНСТРУКЦИИ:
### Правило media
  - правило подстраивать свои страницы под разные вариации разрешений. Можно воспринимать как новый CSS. Запись:

  #### @media
 Построение: @media (условие) { /* Правила */ }
  
Условиями могут быть:
1) Ширина или высота viewport (пример: ширина viewport меньше или равно 700 пикселей. Тогда указывается правило max-width: 700px)
2) Горизонтальная или вертикальная ориентация экрана
3) Тип устройства
4) orientation - специальное условие, которое может иметь одно из двух значений:
- portrait — портретная ориентация устройства. Высота экрана больше, чем его ширина
- landscape — альбомная ориентация устройства. Высота экрана меньше, чем его ширина

  
  #### @keyframes
  - базовый принцип анимации в CSS

  Построение: @keyframes название_анимации { *правило анимации* }
Пример: 
> < style >
> @keyframes color-change {
> 0% {color: blue;}
> 50% {color: red;}
> 100% {color: blue;}
> }
> .animation-text {animation: color-change 3s infinite;}
> < / style >
> < p class="animation-text" >This is some text< /p >

**Переменная** создаётся с помощью конструкции [--имя-переменной]
  
Для создания глобальной переменной её нужно указать в специальной конструкции :root. Обычно это делается в самом начале CSS файла:

> :root {

> --main-color: #000000;

> }

  И дальше по тексту: записывать уже переменную: var(--main-color).

