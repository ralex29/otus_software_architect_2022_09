[> Home](../graduate_project.md)

---

# Выбор решения для реализации генератора нагрузки


## Статус

Принято

## Контекст

В QA002 есть требование, что система должна генерировать профиль нагрузки мелкими пакетами в 64 байта на максимальной 
скорости 10G интерфейса. Фреймрейт для таких условий должен быть более 14800000 pps. Стандартная сетевая подсистема 
Linux не способна на такую производительность. Необходимо выбрать решение, которое удовлетворило бы данным требованиям 

## Решение

Описать fpga dpdk ebpf

## Последствия

**Позитивные:**

- Easy to access decisions.
- Easy to find out why a decision was made.
- Quick to learn how to create and use ADRs.

**Негативные:**

- Need to on-board everyone on the project to understand ADRs.

---

[> Home](../graduate_project.md)