# laba5
# АНАЛИЗ ДАННЫХ И ИСКУССТВЕННЫЙ ИНТЕЛЛЕКТ [in GameDev]
# 5 ЛАБОРАТОРНАЯ РАБОТА. Интеграция экономической системы в проект Unity и обучение ML-Agent.
Отчет по лабораторной работе #5 выполнил(а):
- Маслий Илья Андреевич
- РИ211102
Отметка о выполнении заданий (заполняется студентом):

| Задание | Выполнение | Баллы |
| ------ | ------ | ------ |
| Задание 1 | * | 80 |
| Задание 2 | * | 20 |

знак "*" - задание выполнено; знак "#" - задание не выполнено;

Работу проверили:
- к.т.н., доцент Денисов Д.В.
- к.э.н., доцент Панов М.А.
- ст. преп., Фадеев В.О.

[![N|Solid](https://cldup.com/dTxpPi9lDf.thumb.png)](https://nodesource.com/products/nsolid)

[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

## Цель работы
Интегрировать экономическую систему в проект Unity и обучение ML-Agent'a
## Задание 1. Измените параметры файла. yaml-агента и определить какие параметры и как влияют на обучение модели. Файл Economic.yaml
Ход работы:
```py

behaviors:
  Economic:
    trainer_type: ppo
    hyperparameters:
      batch_size: 1024
      buffer_size: 10240
      learning_rate: 3.0e-4
      learning_rate_schedule: linear
      beta: 1.0e-2
      epsilon: 0.2
      lambd: 0.95
      num_epoch: 3      
    network_settings:
      normalize: false
      hidden_units: 128
      num_layers: 2
    reward_signals:
      extrinsic:
        gamma: 0.99
        strength: 2.0
    checkpoint_interval: 500000
    max_steps: 750000
    time_horizon: 64
    summary_freq: 5000
    self_play:
      save_steps: 20000
      team_change: 100000
      swap_steps: 10000
      play_against_latest_model_ratio: 0.5
      window: 10
      
      ```
      
- Создать новый 3D проект, скачать файл со скриптом, создать пустой объект и привязать к нему данный скрипт.
![image](https://user-images.githubusercontent.com/29748577/204833409-38e4d651-1760-423c-92a7-df35b8ff18b8.png)

## Реализовать вычисления OR
- Настроил на вычисление логического OR|ИЛИ
![image](https://user-images.githubusercontent.com/29748577/204834003-bd9a551f-d34a-4216-bcf0-3df091af2c60.png)
Далее поставил 1 эпоху для обучения и запустил сцену. В результате перцептрон не обучился.
![image](https://user-images.githubusercontent.com/29748577/204834617-89ebfb59-129a-4872-a5f5-012046abd128.png)
Затем поставил 8 эпох и результат получился удачный. Перцептрон обучился с 4 эпохи и выдал такие значения при проверке.
![image](https://user-images.githubusercontent.com/29748577/204835140-a3ce3627-32ef-410d-9745-344c177069be.png)
- Лучше всего ставить от 6 эпох, так как перцептрон не всегда успевал обучиться при 5 эпохах.

## Реализовать вычисления AND
- Настроил на вычисление логического AND|И (Аналогично OR)
![image](https://user-images.githubusercontent.com/29748577/204836510-fa3c4c6e-43fc-4e4e-b6d6-ed03d88b998a.png)
- Поставил 8 эпох, обучился с 7 эпохи. И выдал такие результаты.
![image](https://user-images.githubusercontent.com/29748577/204836884-caf99a09-9b39-4a19-92dc-ad4b02a63ced.png)

## Реализовать вычисления NAND
- Настроил на вычисление логического NAND. NAND - инвертированные значения AND.
![image](https://user-images.githubusercontent.com/29748577/204838408-d33f14a5-0d91-4c93-9609-b8041c6c8f62.png)

## Реализовать вычисления XOR
- Настроил на вычисление логического XOR. При увеличении кол-ва эпох перцептрон выдавал все больше и больше ошибок, т.к. перцептрон работает только с линейными функциями, XOR-не линейная функция.
![image](https://user-images.githubusercontent.com/29748577/204840325-5d57197a-e584-4cc2-8e19-9e169dc73215.png)
Следовательно, перцептрон не сможет обучиться и будет выдавать некорректные результаты.

## Задание 2
## Построить графики зависимости количества эпох от ошибки обучения. Указать от чего зависит необходимое количество эпох обучения.
Я использовал 8 эпох для данных логических выражений и получил вот такой график.
![image](https://user-images.githubusercontent.com/29748577/204841955-d8ded802-3574-411d-b8b2-894d2d8bb899.png)
Необходимое количество эпох обучения зависит от bias (смещения) и weights (весов).

## Выводы

Я познакомился с перцептроном, разобрался в его принципе работы. Реализовал перцептрон в Unity и обучил его производить вычислпения логических операций. Построил график зависимости кол-ва эпох от ошибки обучения.

| Plugin | README |
| ------ | ------ |
| Dropbox | [plugins/dropbox/README.md][PlDb] |
| GitHub | [plugins/github/README.md][PlGh] |
| Google Drive | [plugins/googledrive/README.md][PlGd] |
| OneDrive | [plugins/onedrive/README.md][PlOd] |
| Medium | [plugins/medium/README.md][PlMe] |
| Google Analytics | [plugins/googleanalytics/README.md][PlGa] |

## Powered by

**BigDigital Team: Denisov | Fadeev | Panov**
