[> Home](../graduate_project.md)

---

# Выбор стратегии добавления новой методики тестирования

## Статус

Принято

## Контекст

Методика тестирования несет в себе сложную бизнес логику по проведению нагрузочного теста, таким образом исполнители 
теста по разным методикам очень сильно различаются функционально и структурно. Необходимо выбрать подход, 
который позволит обобщить исполнителей заявок и упростит деплой исполнителя по новой методике тестирования, добавляя 
новую методику за меньшее время.  

## Решение

Компоненты нового исполнителя заявки необходимо упаковывать в Docker образы. 
Все образы одного исполнителя описываются с помощью DockerCompose.
Все это запускается на отдельной виртуальной машине на ESXI.

## Последствия

**Позитивные:**

- Обобщенный подход для любого уровня сложности исполнителя заявки.  

**Негативные:**

- Неавтоматизированное решение. Администратор сам должен создавать и разворачивать необходимые виртуальные машины и 
разворачивать внутри них Docker контейнеры. Использование оркестратора для разворачивания недоступно по причине 
ограниченных ресурсов и отсутствия технической экспертизы. 

---

[> Home](../graduate_project.md)