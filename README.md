# GyverHub-projects
Это база проектов на [платформе GyverHub](https://github.com/GyverLibs/GyverHub). Можно добавлять свои проекты в базу проектов (вкладка Projects в приложении). Если проект находится в базе, то можно:
- Прошить плату на актуальную версию проекта прямо из браузера (вкладка Projects в приложении)
- Получать ОТА обновления проекта

## Как добавить свой проект
- Зарегистрироваться на GitHub, создать репозиторий проекта (см. гугл)
- Оформить проект - описание, схема, инструкции и т.д.
- Создать и заполнить файл информации о проекте, он должен находиться по пути `/project.json`

## Файл информации
```json
{
  "name": "Название проекта",
  "about": "Краткое описание проекта",
  "version": "1.0",
  "notes": "Комментарии к обновлению",
  "builds": [
    {
      "chipFamily": "ESP8266",
      "parts": [
        {
          "path": "https://raw.githubusercontent.com/GyverLibs/GyverHub-example/main/bin/firmware.bin",
          "offset": 0
        }
      ]
    }
  ]
}
```

### Массив builds
Если проект может быть запущен на разных ЕСП-шках - можно приложить отдельный бинарник для каждой и указать пути к ним. Полный пример со всем семейством ESP можно посмотреть [тут](https://raw.githubusercontent.com/GyverLibs/GyverHub-example/main/project.json). 

### Параметр chipFamily
Поддерживаемые платформы и значения параметра `chipFamily`:
- `"ESP8266"`
- `"ESP32"`
- `"ESP32-C3"`
- `"ESP32-S2"`
- `"ESP32-S3"`

### Путь path
Путь должен вести к скомпилированному файлу прошивки. Его можно разместить как в самом репозитории, так и в релизах:

Если файл лежит **в репозитории**, то путь должен иметь вид:
```
https://raw.githubusercontent.com/<аккаунт>/<проект>/main/<путь от корня репозитория>
```
Примеры:
- bin
  - firmware.bin
  - esp8266
    - firmware.bin
  - esp32
    - firmware.bin
```
https://raw.githubusercontent.com/GyverLibs/GyverHub-example/main/bin/firmware.bin
https://raw.githubusercontent.com/GyverLibs/GyverHub-example/main/bin/esp8266/firmware.bin
https://raw.githubusercontent.com/GyverLibs/GyverHub-example/main/bin/esp32/firmware.bin
```

Если файл лежит **в релизах**, то путь к файлу актуального релиза должен иметь вид:
```
https://github.com/<аккаунт>/<проект>/releases/latest/download/<файл>
```
Пример:
```
https://github.com/GyverLibs/GyverHub-example/releases/latest/download/firmware.bin
```

## Добавление в базу
Нужно просто сделать fork данного (GyverHub-projects) репозитория, добавить ссылку на репозиторий своего проекта в файл projects.txt и создать Pull request:
- Перейти на [страницу редактирования](https://github.com/GyverLibs/GyverHub-projects/edit/main/projects.txt) файла projects.txt
    - Если это первое добавление - нажать **Fork this repository**
- Добавить ссылку на репозиторий своего проекта в список проектов
- Нажать **Commit changes...** в правом верхнем углу экрана
- Нажать **Propose changes** в появившемся окне
- Нажать **Create pull request** в правом верхнем углу экрана
- Нажать **Create pull request** на открывшейся странице
- Ждать ручной модерации

> Примечание: это публичная база проектов, поэтому добавляться будут только хорошо оформленные проекты

## Автоматическое обновление
Как настроить обновление с GitHub из приложения [читай wiki](https://github.com/GyverLibs/GyverHub/wiki/5.-%D0%94%D0%BE%D0%BF%D0%BE%D0%BB%D0%BD%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D0%BE)
