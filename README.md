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
## Задание 1. Измените параметры файла. yaml-агента и определить какие параметры и как влияют на обучение модели.
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
![image](https://user-images.githubusercontent.com/29748577/205342465-5f161595-cba2-4f3d-88eb-950eba173220.png)
- Затем я установил TensorBoard и получил там такой график:
![image](https://user-images.githubusercontent.com/29748577/205342770-b004a966-8142-4720-9b05-3b83dfb0d14a.png)

## Задание 2
Еслий сделать переменную batch_size=300, то наши графики станут кривыми.
![image](https://user-images.githubusercontent.com/29748577/205344370-4ba2a260-3f05-49db-a5c7-a11529ac544b.png)
Я сделал переменную batch_size=1024 и изменил параметр lambd с 0.95 на 0.9. Графики стали более линейными.
![image](https://user-images.githubusercontent.com/29748577/205344053-56e166c2-b107-4707-b22c-eded9e2f1779.png)

## Выводы
Я интегрировал экономическую систему в проект Unity и обученил ML-Agent'a. Изменил параметры файла. yaml-агента и определил какие параметры и как влияют на обучение модели.

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
