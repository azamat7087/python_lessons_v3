## Lesson 7

Курс по программированию на языке Python 

**3 слайд**- Объектно-ориентированное программирование

Добрый день дорогие участницы программы Unisat. На сегодняшнем видеоуроке по программированию на языке Python, мы рассматриваем такую тему как ООП, или объектно-ориентированное программирование.

До сих пор наши программы состояли из функций, т.е. блоков выражений, которые мани-
пулируют данными. Это называется процедурно-ориентированным стилем программиро-
вания. Существует и другой способ организации программ: объединять данные и функ-
ционал внутри некоего объекта. Это называется объектно-ориентированной парадигмой
программирования. В большинстве случаев можно ограничиться процедурным програм-
мированием, а при написании большой программы или если решение конкретной зада-
чи требует того, можно переходить к техникам объектно-ориентированного программи-
рования.
Два основных аспекта объектно-ориентированного программирования – классы и объ-
екты. Класс создаёт новый тип, а объекты являются экземплярами класса. Аналогично,
когда мы говорим о «переменных типа int », это означает, что переменные, которые хра-
нят целочисленные значения, являются экземплярами (объектами) класса int .

Объекты могут хранить данные в обычных переменных, которые принадлежат объек-
ту. Переменные, принадлежащие объекту или классу, называют полями. На данном слайде у нас изображен класс кота, который имеет такие поля, как mood - настроение,
hungry - голод, energy - энергия. Они относятся к свойствам объекта, то есть описывают текущее состояние нашего кота. Голоден ли он, ил хочет играться, или у него нет настроения на игры.
Объекты могут также обладать функционалом, т.е. иметь функции, принадлежащие классу. Такие функ-
ции принято называть методами класса. Эта терминология важна, так как она помогает
нам отличать независимые функции и переменные от тех, что принадлежат классу или
объекту.  

Всё вместе (поля и методы) принято называть атрибутами класса.
Поля бывают двух типов: они могут принадлежать каждому отдельному экземпляру объ-
екта класса или всему классу. Они называются переменными экземпляра и перемен-
ными класса соответственно.

Класс создаётся ключевым словом class . Поля и методы класса записываются в блоке
кода с отступом.

Как я говорил ранее, в данном случае у нас приведен класс Cat. Он имеет такие поля, как: настроение, голод и энергию. И помимо этого есть методы - функции пренадлежащие классу. К ним относятся методы: play, feed, sleep и meow. Данные методы влияют на наши поля. Допустим метод sleep добавляет нам параметры энергии и голода. Метод play добавляет нам настроение, уменьшает энергию и вызывает другой метод meow, который здесь не написан.

**Переход к коду**

Давайте реализуем наш класс Cat. Для этого прописываем ключевое слово class, затем пишем имя класса с большой буквы. В данном случае, Cat. Затем необходимо реализовать метод конструктор. def init с параметром self. Что такое init и self, мы с вами рассмотрим немного позже. Как вы помните, у нашего класса Кот было 3 поля: self.mood - пусть будет happy, на данный момент; self.hungry, то есть голод - будет равен 35 единицам, self.energy - будет равен 40 единицам. Давайте теперь реализуем метод. Для этого пишем ключевое слово def и пусть будет метод play, то есть кот будет играться. Опять же ключевой параметр self. И во время игры кот, опять же, теряет энергию -= 10 единиц энергии, а так же self.hungry -= 5 единиц. И пускай еще будет метод feed, который прибавляет к нашему полю голода 10 единиц. Таким образом мы реализовали самый простой класс с двумя методами. Давайте теперь будем создавать объект. Как говорилось ранее объект - это экземпляр класса. Пусть его называние будет - my_cat, то есть мой кот. Затем пишем оператор присваивания, название класса и скобочки. В данном случае наш конструктор не принимает параметров ,поэтому скобочки пустые. То есть все задается по умолчанию. Затем после создания перменной давайте посмотрим его параметры. Допустим my_cat и сколько у него осталось энергии. 40  на данный момент. А давайте запустим метод play, пусть кот поиграется. Затем выведем снова энергию и выведем голод. И как вы видите поле энергии потеряло 10 единиц, а поле голода потеряло 5 единиц.
 Пускай теперь кот покушает - my_cat.feed().  И теперь выведем, допустим, тот же самый голод. И как вы видите он вырос на 10 единиц. То есть по данному принципу работают классы.
 
**4 слайд** - self

Методы класса имеют одно отличие от обычных функций: они должны иметь дополни-
тельно имя, добавляемое к началу списка параметров. Однако, при вызове метода никако-
го значения этому параметру присваивать не нужно – его укажет Python. Эта переменная
указывает на сам объект экземпляра класса, и по традиции она называется self.
Хотя этому параметру можно дать любое имя, настоятельно рекомендуется использовать
только имя self ; использование любого другого имени не приветствуется. Есть много до-
стоинств использования стандартного имени: во-первых, любой человек, просматриваю-
щий вашу программу, легко узнает его; во-вторых, некоторые специализированные IDE изначально рассчитаны на использование self.

Вы, должно быть, удивляетесь, как Python присваивает значение self и почему вам не
нужно указывать это значение самостоятельно. Поясним это на примере. Предположим,
у нас есть класс с именем Car, который представляет машины. Далее нам нужно создать экземпляр данного класса - объект. Таким образом мы создаем объект my_car.
Как и любая другая машина my_car должна уметь ездить. И для этого у нас есть метод drive, который принимает параметр speed - отвечающий за скорость езды. Таким образом мы вызываем метод drive у объекта my_car с аргументом speed. Обратите внимание, что при вызове мы не указываем self. Однако переходя в наш класс, происходит автоматическое преобразование, где наш метод выглядит теперь следующим образом. Как вы наверное заметили объект my_car изменился на класс Car, а параметрах метода появилось self. Так вот self - это и есть наш объект my_car, и для того чтобы класс понимал к какому именно объекту обращаться мы используем self, так как объектов у нас может быть много. Подробную работу с self мы рассмотрим далее. 


**5 слайд** - Классы

Пускай у нас есть класс Satellite - обозначающий спутники в целом. Как вы помните класс Car тоже брал виды машин в общем виде(Есть ведь и гоночные машины, грузовые и так далее). Так вот, для облегченного понимания принципа классов, давайте сравним его с чертежом. Данный чертеж позволяет нам по определенным инструкциям собирать настоящие спутники. Созданные по данному чертежу спутники являются реальными. У них есть свой вес, раскрас, модули, датчики. Так же они могут выполнять определенные действия. Например фиксировать данные или включаться. Так реальные спутники- это экземпляры данного класса или объекты. 

**Переход к коду**

Простейший класс показан в следующем примере

Мы создаём новый класс при помощи оператора class и имени класса. За
этим следует блок выражений, формирующих тело класса. В данном случае
блок у нас пуст, на что указывает оператор pass .
Далее мы создаём объект-экземпляр класса, записывая имя класса со скобка-
ми. Для проверки мы
выясняем тип переменной, просто выводя её на экран. Так мы видим, что у
нас есть экземпляр класса Satellite в модуле __main__ .

Обратите внимание, что выводится также и адрес в памяти компьютера, где
хранится ваш объект. На вашем компьютере адрес будет другим, так как
Python хранит объекты там, где имеется свободное место.


**6 cлайд** - Методы объектов

На прошлом слайде мы с вами говорили о том, что спутники-объекты могут выполнять определенные действия. Данные действия называются методами. Методы очень схожи с функциями, но между ними есть определенные различия. Функции независимы сами по себе, и выполняют отдельный абстрагированный функционал, тогда как методы тесно связаны с нашими объектами и вызываются от их лица(К примеру можно привести поездку машины). Методы влияют лиш на определенный объект, от лица которого они вызываются. Пускай мы имеем объект unisat. И для простого примера он имеет три метода: get_work_mode - возвращает нам текущий режим работы спутника(активен он или выключен), change_direction - позволяет нам влиять на направление полета спутника, update_data - активирует работу датчик спутника и обновляет базу данных новыми сведениями.


**Переход к коду**

Итак, мы выяснили что классы/объекты могут иметь методы, представляющие собой
функции, за исключением дополнительной переменной self . А теперь давайте рассмот-
рим пример. Здесь мы видим self в действии. Обратите внимание, что метод get_work_mode не
принимает параметров, но тем не менее, имеет self в определении функции.

Метод get_work_mode необходим для получения текущего режима работы спутника. Пока он только выводит статический текст.


**7 слайд** - Метод __init__

Существует много методов, играющих специальную роль в классах Python. Сейчас мы
увидим значительность метода __init__ .
Метод __init__ запускается, как только объект класса реализуется. Этот метод полезен
для осуществления разного рода инициализации, необходимой для данного объекта. Об-
ратите внимание на двойные подчёркивания в начале и в конце имени.

Мы имеем уже знакомый класс Satellite и хотим создать объект данного класса. Однако сразу при его создании нам нужно как-то обозначить созданный объект и задать ему ряд параметров. Пускай это будут поля name="unisat" и work_mode="активен". Таким образом сразу при создании объекта мы имеем спутник с именем "unisat", который находится в активном режиме работы. А что такое поля вы увидите дальше.

**Переход к коду**
И так давайте напишем наш метод __init__.

Здесь мы определяем метод __init__ так, чтобы он принимал параметр name, work_mode
(наряду с обычным self ). Далее мы создаём новое поле с именем name и с именем work_mode . Если взять в пример переменную name, об-
ратите внимание, что это две разные переменные, даже несмотря на то, что
они обе названы name . Это не проблема, так как точка в выражении self.
name обозначает, что существует нечто с именем «name», являющееся частью
объекта «self», и другое name – локальная переменная. Поскольку мы в явном
виде указываем, к которому имени мы обращаемся, путаницы не возникнет.

Для создания нового экземпляра unisat класса Satellite мы указываем имя класса,
после которого – аргументы в скобках: unisat = Satellite('unisat', 'активен') .
Метод __init__ мы при этом не вызываем явным образом. В этом и заклю-
чается специальная роль данного метода.
После этого мы получаем возможность использовать поле self.work_mode в наших
методах, что и продемонстрировано в методе get_work_mode . Текущий режим работы - активен.


**8 слайд** - Переменные класса и объекта

Функциональную часть классов и объектов (т.е. методы) мы обсудили, теперь давайте
ознакомимся с частью данных. Данные, т.е. поля, являются не чем иным, как обычны-
ми переменными, заключёнными в пространствах имён классов и объектов. Это означа-
ет, что их имена действительны только в контексте этих классов или объектов. Отсюда и
название «пространство имён». Например разные объекты класса спутник, будут иметь свои уникальные имена или другие параметры, которые относятся только к ним.
Мы имеем класс Satellite и объект класса satellite с именем unisat.
Существует два типа полей: переменные класса и переменные объекта, которые разли-
чаются в зависимости от того, принадлежит ли переменная классу или объекту соответ-
ственно.
У класса satellite есть переменная-счетчик, которое отображает общее количество, работающих на данный момент спутников.
У объекта unisat есть переменные: имя и режим работы.

Переменные класса разделяемы – доступ к ним могут получать все экземпляры этого клас-
са. Переменная класса существует только одна, поэтому когда любой из объектов изме-
няет переменную класса, это изменение отразится и во всех остальных экземплярах того
же класса.
Переменные объекта принадлежат каждому отдельному экземпляру класса. В этом случае
у каждого объекта есть своя собственная копия поля, т.е. не разделяемая и никоим образом
не связанная с другими такими же полями в других экземплярах. Это легко понять на
примере

**Переход к коду**
Здесь active_satellites принадлежит классу Satellite , и поэто-
му называется переменной класса. Переменная name, work_mode принадлежат объекту (им
присваивается значение при помощи self ), и поэтому они являются переменной
объекта. Давайте немного допишем наш метод init. if self.work_mode = активен, то в данном случае мы увеличиваем нашу переменную класса active-satellites на одну единицу. Для этого мы уже не используем имя self, мы уже используем имя класса. Sattelite. и название переменной - active_satellites += 1. Затем добавим метод change_work_mode, который меняет текущий режим работы. И он принимает новый параметр - work_mode. Затем условие: if self.work_mode != work_mode, то есть если наше старое значение режима работы не равно новому значению режима работы. Здесь они разные. Если бы они были одинаковыми, то нет смысла делать новое присваивание. Затем внутри условия if пишем новое условие. if self.work_mode  равен активен, то есть он находится в активном, то переменная Sattelite.active_satellites -= 1. Сейчас я обьясню почему. Наш старый режим работы был активен и как только мы вызываем метод chane_work_mode с новым режимом работы, мы изменяем наше старое значение на новое. То есть в данном случае он переходит в другой режим, и исходя из этого мы отнимаем один спутник из общего количества активных спутников. Затем в самом конце нам необходимо присвоить новое значение нашему спутнику. Заметьте, что данное условие может не активироваться, если предыдущее значение режима работы не было равно активен. Затем давайте протестируем, а для начала напишем еще один метод, который возвращает нам общее количество работающих спутников. Давайте протестриуем наш код, наш класс. Добавим еще вызов метода , который возвращает нам количество работающих спутников. Затем изменим наш режим работы со значением выключен. Затем снова выведем значение наших работающих спутников. И как вы видите текущий режим работы активен из метода get_work_mode. Затем мы берем количество работающих спутников, равное единице. После этого мы меняем режим работы на спутнике unisat и делаем его выключенным. И в конце концов снова проверяем количество работающих спутников. И получаем значения нуля.
 

Таким образом, мы обращаемся к переменной класса active_satellites как Satellite.active_satellites , а не self.active_satellites . К переменной же объекта name во всех методах этого объекта мы обращаемся при помощи обозначения self.name .
Помните об этой простой разнице между переменными класса и объекта. Так-
же имейте в виду, что переменная объекта с тем же именем, что и переменная
класса, сделает недоступной («спрячет») переменную класса!

Помните, что к переменным и методам самого объекта нужно обращаться, пользуясь
только self . Это называется доступом к атрибутам.

**9 слайд** - Наследование

Одно из главных достоинств объектно-ориентированного программирования заключа-
ется в многократном использовании одного и того же кода, и один из способов этого
достичь – при помощи механизма наследования. Легче всего представить себе наследова-
ние в виде отношения между классами как тип и подтип.
Как я говорил ранее класс Satellite - это общее представление всех видов спутников. Как вы знаете есть так же нано-спутники, погодные спутники, спутники коммуникации и многие другие. У каждого из этих подвидов спутников есть свои отличительные особенности. Например размер, вес, особенности работы, доступный функционал, количество датчиков и так далее. Однако у данных спутников есть и много общего. Они все являются спутниками, находятся на орбите, имеют базовую электронику, аккумулятор, базовые датчики. И представьте, что нам нужно создать данные виды спутников в виде классов. В таком случае, мы можем просто скопировать весь написанный в классе Satellite код, однако такое решение приведет к многим неудобствам. Например если вы все же захотите изменить код написанный в классе Satellite, то вам придется менять его и в других спутниках. Так же это приведет к громоздкости проекта и его неудобности и нечитаемости. Выходом из такой ситуации является наследование новых производных классов от базового класса спутник. Тогда мы сможем избежать всех вышеперечисленных проблем. В данном случае класс Satellite называетя классом родителем, а производные от него классы наследниками.



**Переход к коду**
Давайте представим, что нам необходимо создать новый класс Нано-спутник. У него будут такие же атрибуты и методы, как и у класса Спутник. Конечно мы можем создат ь независимый класс и работать с ним, но тогда добавление какой-либо новой общей характеристики потребует добавления ее к каждому из этих независимых классов по отдельности, что делает программу неповоротливой. 

  Лучше создать общий класс с именем Satellite , а затем сделать так, чтобы класс NanoSatellite наследовал этот класс, т.е. чтобы он стал подтипом этого
типа (класса), после чего добавить любые специфические характеристики к этому подтипу.

У такого подхода есть множество достоинств. Если мы добавим/изменим какую-либо
функциональность в Satellite , это автоматически отобразится и во всех подтипах.
Например, мы можем добавить новое поле температуры или скорости, просто добавив его к классу Satellite . С другой стороны, изменения в подтипах
никак не влияют на другие подтипы. Ещё одно достоинство состоит в том, что обращать-
ся к объекту наноспутника можно как к объекту спутника , что может
быть полезно в ряде случаев, например, если у нас имеются и другие типы спутников. Когда подтип может быть подставлен в любом месте, где ожидается родительский тип, т.е. объект считается экземпляром родительского класса, это называется полиморфизмом.
Заметьте также, что код родительского класса используется многократно, и нет необходи-
мости копировать его во все классы, как пришлось бы в случае использования независи-
мых классов.
Класс Satellite в этой ситуации называют базовым классом или надклассом, класс NanoSatellite называют производным классом или подклассом.

И так, пускай мы имеем знакомый нам класс Satellite. И пусть мы добавим к нему новое поле type. Пусть это будет default. Теперь нам необходимо создать класс наследник - класс наноспутник. В данном случае, мы опять же пишем ключевое слово class, название - NanoSatellite. А затем в скобках, уже указываем имя родительского класса, от которого мы будем наследоваться - это Satellite. Далее опять же переопределяем метод init. И переменная type в данном случае, будет уже не default, а nano. Все остальное можно оставить прежним. Давайте напишем новый метод, характерный только для данного класса - def get_type(self). Мы написали наш производный класс и теперь давайте создадим объект данного класса. В данном случае это уже будет не Satellite, а NanoSatellite. И таким образом весь написанный ранее функционал и поля, будут находиться так же и в этом классе. И кроме этого мы будем иметь наш новый метод get_type. Давайте вызовем сперва метод get_name - unisat.get_name. Как вы видите в данном классе его нет и он все равно вызывается и он все равно работает. Затем вызовем метод get_type, который является новым методом. И в данном случае мы получаем уже не default, а nano. 
Так как unisat является экземпляром класса NanoSatellite, который является наследником класса Satellite.
