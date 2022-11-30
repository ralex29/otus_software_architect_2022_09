

# Tales Of A Fourth Grade

Компания хочет предложить школьным округам комплексную систему управления учащимися в качестве услуги

## Пользователи: 
- преподаватели
- сотрудники 
- родители учащихся

## Требования:
- отслеживать пропуски занятий, опоздания и отговорки (вводится родителями, преподавателями или сотрудниками)
- управлять от 1000 до 1 миллиона студентов
- генерировать отчеты о деятельности учащихся
- быть доступным с игровой площадки
- отслеживать оценки и задания учащихся (выполненные и подлежащие выполнению)
- форумы родителей и учителей
- работать как система SaaS из хостинг-центра
- должны соблюдать правила безопасности FERPA (Закон о правах семьи на образование и конфиденциальность), которые можно найти по адресу (https://www2.ed.gov/policy/gen/guid/fpco/ferpa/index.html).
 
## Дополнительный контекст:
- компания планирует провести агрессивную национальную кампанию продаж
- текущий конкурент пострадал из-за утечки данных
- новый ИТ-директор
- основной маркетинговый ход заключается в гибкости, настраиваемости и (недавно добавленной) безопасности.

## Бизнес-драйверы
- показать пользователям о минимальных затратах за счет того, что нет необходимости поддерживать инфраструктуру
- показать пользователям, что основной упор делается на безопасности

## Бизнес-цель
- за счет падения доверия к конкуренту и агрессивной компании продаж захватить большую часть рынка таких систем

## Стейкхолдеры
Заинтересованные стороны, ключевые участники:
- преподаватели
пользователи системы выставляющие учащимся оценки, заполняющие журнал посещаемости, создавать и читать сообщения на форумах 
- сотрудники
пользователи системы ведущие административную работу по управлению учащимися в системе, создание и архивация профилей учащихся, учителей, родителей, 
заполняющие журнал посещаемости учащихся, создание и модерирование сообщений на форумах
- родители учащихся
пользователи системы имеющие возможность просмотра информации об оценках и посещаемости конкретного учащегося, создавать и читать сообщения на форумах учителей


## Пользовательские истории

## Базовые атрибуты качества


## Бизнес контекст


## Критичные сценарии и характеристики

### Критичные сценарии

### Критичные характеристики


## Архитектурное решение 1
### Контекст
Для игрового сервиса необходимо определится с
архитектурным подходом.

### Альтернативы
- Альтернатива 1. Монолит
- Альтернатива 2. Модульный монолит
- Альтернатива 3. Микросервисный подход

### Оценка и сравнительный анализ

|                    | Монолит | Модульный монолит | Микросервисный подход |
|--------------------|---------|-------------------|-----------------------|
| Доступность        | -       | -                 | ++                    |
| Производительность | ++      | ++                | ++                    |
| Масштабируемость   | --      | +                 | ++                    |
| Модифицируемость   | 0       | +                 | ++                    |

### Решение
Наилучшим сочетанием значений критических характеристик достигается при микросервисном подходе к архитектуре.
Кроме того при успешности данной игры компания может легко использовать микросервисы в качестве основы, которую они смогут продавать

## Архитектурное решение 2
### Контекст
Для игры необходим высокопроизводительный игровой движок способный передать визуальный вид и ощущения от игры которые разработают художники.

### Альтернативы
- Альтернатива 1. Разработка собственного игрового движка
- Альтернатива 2. Покупка подходящего готового движка

### Оценка и сравнительный анализ

|                     | Собственный движок | Сторонний движок |
|---------------------|--------------------|------------------|
| Затраты на движок   | ---                | -                |
| Время на разработку | ---                | +                |

### Решение
Компания ограничила ресурсы на разработку, в том числе и собственного игрового движка, поэтому
наилучшим выбором будет использование стороннего.
Обычно с игровым движком поставляются средства/утилиты для разработки игрового мира,
что тоже является плюсом так как художники смогут сразу использовать эти средства работая с конечным представлением
своих данных. Это избавит художников от необходимости хранить свои наработки в промежуточном формате, а затем переводить в формат
собственного движка.

## Архитектурное решение 3
### Контекст
Необходимо определить, где будет отрисовываться игровая картинка.

### Альтернативы
- Альтернатива 1. На стороне браузера
- Альтернатива 2. На стороне сервера

### Оценка и сравнительный анализ
**Альтернатива 1.** На стороне браузера
- в этом случае между браузером и сервером будет передаваться на порядок меньше данных,
  что обеспечит лучший отклик игрового мира на действия игрока
- также данный подход снизит нагрузку на игровые сервера и снизит требования к ним по производительности
- качество визуальной составляющей будет зависеть от производительности компьютера игрока, что может уменьшить
  кол-во желающих играть в данную игру

**Альтернатива 2.** На стороне сервера
- в этом случае между браузером и клиентом будет передаваться большой поток данных,
  что ограничит пользователей с плохими каналами связи
- на серверной стороне будет необходимо размещать специальные высокопроизводительные сервисы для отрисовки игровой картинке
- качество визуальной составляющей будет постоянным и высоким, при этом игра будет доступна на любой
  низкопроизводительной платформе

### Решение
Компания склоняется к варианту с отрисовкой игровой картинки в браузере игрока. Это снизит порог доступа для игроков
с плохими каналами связи, снизит отклик игровой системы на действия игрока, снизит расходы на высокопроизводительное
серверное оборудование.  
Но необходимо проработать риск:
- имеются ли готовые игровые движки работающие в современных браузерах и отрисовывающие картинку такого качества
  которого хотели бы достичь художники (игровые-дизайнеры).