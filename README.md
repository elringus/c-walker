Задание
=======
Разработать игровой клиент (мобильный) и сервер.

Серверная часть может быть реализована на любом языке, например на PHP и использовать HTTP для передачи данных. Данные должны быть в формате JSON. Сервер должен отвечать на следующие запросы:

getObstacles – получить координаты всех препятствий на карте. Препятствия могут быть двух видов: домик или дерево. Препятствия генерируются случайно.

getPlayer – получить координаты персонажа. В ответ сервер возвращает случайную координату

getDestination – получить координаты точки в которую должен двигаться персонаж. Координаты генерируются случайно при каждом новом запросе

 

Клиент.

Клиентское приложение должно быть реализовано на Unity 3D. Скрипты должны быть написаны на C#.

Игровой мир состоит из одной сцены с террейном. На сцене присутствует озеро. Озеро должно использовать кастомый уникальный собственноручно написанный шейдер.

Координатная плоскость, в которой существуют объекты, двухмерная и состоит из 50 условных квадратов по осям x и y. Несмотря на то что координатная плоскость двухмерная, объекты должны стоять на поверхности террейна, т.е. иметь высоту точки на поверхности, а не быть утопленными в террейн.

При запуске игры клиент соединяется с сервером, запрашивает расположение и тип объектов, дожидается ответа, затем расставляет объекты на карте, затем запрашивает координаты пользователя и устанавливает фигурку пользователя в нужной точке. После этого запрашиваются координаты точки назначения и пользователь начинает двигаться в нужную точку. Если маршрут до точки рассчитать невозможно, то клиент делает запрос на получение новой точки.

Все запросы к серверу должны выполняться в отдельном потоке.  Для запросов использовать HttpWebRequest, пользоваться классом WWW нельзя.
