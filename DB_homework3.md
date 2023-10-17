# ДЗ по БД #2
## Демьяненко Виктор Николаевич БПИ217 (БПИ215 по БД)
### Задание #1
Зараннее представил диаграмму на листочке, затем изобразил результат в PlantUML.
```UML
@startuml
' Определение сущностей
entity "Издательство" as Publisher {
  + Имя
  + Адрес
}

entity "Книга" as Book {
  + ISBN
  + Год
  + Название
  + Автор
  + Количество страниц
}

entity "Категория" as Category {
  + Название категории
}

entity "Читатель" as Reader {
  + Уникальный номер
  + Фамилия
  + Имя
  + Адрес
  + День рождения
}

entity "Экземпляр книги" as BookCopy {
  + Уникальный номер копии
  + Положение на полке
}

entity "Список книг" as ListBook {
  + Уникальный номер копии книги
  + Уникальный номер читателя
  + Дата
}

' Определение связей
Book }|--|| Publisher : Издает
BookCopy }|--|| Book
Category }|--|{ Book : Принадлежит
Reader ||--|{ BookCopy : Взял
ListBook }|--|| Reader : Владеет
ListBook }|--|{ BookCopy : Содержит

@enduml
```


![Alt text](image.png)

### Задание #2

![Alt text](image.png)

```

entity "Квартира" as Apartment {
}

entity "Дом" as House {
 
}

entity "Улица" as Street {
 }

entity "Город" as City {
 
}

entity "Страна" as Country {
}

Apartment ||--|{ House  
House ||--|{ Street 
Street ||--|{ City  
City ||--|{ Country 

@enduml
```

![Alt text](image-1.png)
```
@startuml

entity "Человек" as Person {
  + Имя
  + Дата рождения
}

entity "Мужчина" as Man {
  + Имя
  + Дата рождения
}

entity "Женщина" as Woman {
  + Имя
  + Дата рождения
}

Person --o Man : Отец
Person --o Woman : Мать

@enduml
```

![Alt text](image-2.png)
```
@startuml

entity "Команда" as Team {
  + Название
}

entity "Футбол" as Football {
  + Место проведения
  + Дата проведения
}

entity "Арбитр" as Referee {
  + Имя
}

Team --o Football : Играет
Team --o Team : Против другой команды
Football --o Referee : Руководит

@enduml
```