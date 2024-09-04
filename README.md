<!DOCTYPE html>
<html>
<head>
  <title>Сравнение данных за январь и февраль между двумя загрузками</title>
  <style>
    body {
      font-family: sans-serif;
    }
    h1, h2 {
      margin-bottom: 10px;
    }
    pre {
      background-color: #eee;
      padding: 10px;
      border-radius: 5px;
      overflow-x: auto;
    }
  </style>
</head>
<body>

<h1>Сравнение данных за январь и февраль между двумя загрузками</h1>

<h2>Описание задачи:</h2>

<p>Таблица <code>RAW_DATA</code> содержит информацию о финансовых данных, загружаемых ежемесячно 5 числа. Загрузка включает в себя данные за все прошедшие месяцы текущего года, например:</p>

<ul>
  <li>5 февраля - данные за январь (LOAD_ID = '20220205')</li>
  <li>5 марта - данные за январь и февраль (LOAD_ID = '20220305')</li>
  <li>5 апреля - данные за январь, февраль и март (LOAD_ID = '20220405')</li>
</ul>

<p>Задача состоит в том, чтобы проверить, изменились ли данные за январь и февраль по сравнению с предыдущей загрузкой на 5 апреля.</p>


