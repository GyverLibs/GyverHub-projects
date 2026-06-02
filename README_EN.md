This is an automatic translation and may be incorrect in some places. See the source README and examples for authoritative information.

# GyverHub-projects
This is an open database of projects[platform](https://github.com/GyverLibs/GyverHub). To add your project, you need to:

## Design a repository
- Register on GitHub, create a project repository (see Google)
- Design the project - source, description, scheme, instructions, etc.
- Download the compiled firmware
- Create and complete a project information file`project.json`(see below)
- Look.[repository](https://github.com/GyverLibs/GyverHub-example)

## Add to the database
Make a fork of this repository, add a link to your project repository to your projects.txt file, and create a Pull request:
- Switch to[editing page](https://github.com/GyverLibs/GyverHub-projects/edit/main/projects.txt)file`projects.txt`
    - If this is the first addition, click **Fork this repository**
- Add a link to your project repository to the list of projects
- Press **Commit changes...** in the upper right corner of the screen
- Click **Propose changes** in the window that appears
- Press **Create pull request** in the upper right corner of the screen
- Click **Create pull request** on the open page
- Wait for manual moderation

## project.json
The file contains information about the project and the path to the compiled firmware files for different platforms:
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

### Array builds
If the project can be run on different ESP-scans, you can attach a separate binary for each and specify the paths to them. A complete example of the ESP family can be seen.[here](https://raw.githubusercontent.com/GyverLibs/GyverHub-example/main/project.json). 

### Parameter chipFamily
Supported platforms and parameter values`chipFamily`:
- `ESP8266`
- `ESP32`
- `ESP32-C3`
- `ESP32-S2`
- `ESP32-S3`

### Pathway
The path should lead to the compiled firmware file. It can be placed both in the repository itself and in releases:

#### In the repository.
```
https://raw.githubusercontent.com/<account>/<project>/main/<path from the root of the repository >>
```
Examples:
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

#### On releases
```
https://github.com/<account>/<project>/releases/latest/download/<file >>
```Example:
```
https://github.com/GyverLibs/GyverHub-example/releases/latest/download/firmware.bin
```
