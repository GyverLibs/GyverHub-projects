# GyverHub-projects
Это открытая база проектов на [платформе GyverHub](https://github.com/GyverLibs/GyverHub). Чтобы добавить свой проект, нужно:

## Оформить репозиторий
- Зарегистрироваться на GitHub, создать репозиторий проекта (см. гугл)
- Оформить проект - исходники, описание, схема, инструкции и т.д.
- Загрузить скомпилированную прошивку
- Создать и заполнить файл информации о проекте `project.json` (см. ниже)
- Смотри [репозиторий-пример](https://github.com/GyverLibs/GyverHub-example)

## Добавить в базу
Cделать fork данного (GyverHub-projects) репозитория, добавить ссылку на репозиторий своего проекта в файл projects.txt и создать Pull request:
- Перейти на [страницу редактирования](https://github.com/GyverLibs/GyverHub-projects/edit/main/projects.txt) файла `projects.txt`
    - Если это первое добавление - нажать **Fork this repository**
- Добавить ссылку на репозиторий своего проекта в список проектов
- Нажать **Commit changes...** в правом верхнем углу экрана
- Нажать **Propose changes** в появившемся окне
- Нажать **Create pull request** в правом верхнем углу экрана
- Нажать **Create pull request** на открывшейся странице
- Ждать ручной модерации

## project.json
Файл содержит информацию о проекте и пути к файлам скомпилированной прошивки для разных платформ:
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
Если проект может быть запущен на разных ESP-шках - можно приложить отдельный бинарник для каждой и указать пути к ним. Полный пример со всем семейством ESP можно посмотреть [тут](https://raw.githubusercontent.com/GyverLibs/GyverHub-example/main/project.json). 

### Параметр chipFamily
Поддерживаемые платформы и значения параметра `chipFamily`:
- `ESP8266`
- `ESP32`
- `ESP32-C3`
- `ESP32-S2`
- `ESP32-S3`

### Путь path
Путь должен вести к скомпилированному файлу прошивки. Его можно разместить как в самом репозитории, так и в релизах:

#### В репозитории
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

#### В релизах
```
https://github.com/<аккаунт>/<проект>/releases/latest/download/<файл>
```
Пример:
```
https://github.com/GyverLibs/GyverHub-example/releases/latest/download/firmware.bin
```
