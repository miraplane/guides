# Базовые правила оформления кода

Эти правила описаны в файле __.editorconfig__ .

Большинство редакторов могут автоматически приводить в порядок ваш код,  
достаточно установить и включить соответствующий плагин [editorconfig](http://editorconfig.org/).

## Как подружить его с редактором

- __WebStorm__   
  Открываем «Настройки -> Плагины -> Editorconfig» и включаем.

- __Notepad++__    
  1. Открываем «Plugins -> Plugin Manager -> Show Plugin Manager -> Available».
  2. Находим «EditorConfig» и нажимаем «Install».

- __Sublime__   
  Смотрим инструкцию по ссылке и устанавливаем:   
  https://packagecontrol.io/search/Editorconfig

- __Atom__   
  Смотрим инструкцию по ссылке и устанавливаем:  
  https://atom.io/packages/editorconfig

- __VSCode__  
  Смотрим инструкцию по ссылке и устанавливаем:  
  https://marketplace.visualstudio.com/items?itemName=EditorConfig.EditorConfig

## Какие правила он содержит

```ini
# Для всех файлов
[*]

# Установить кодировку utf-8
charset = utf-8

# В качестве переноса строки использовать символ LF (line feed)
end_of_line = lf

# В конце файла добавить пустую строку
insert_final_newline = true

# В качестве отступов использовать 4 пробела
indent_size = 4
indent_style = space

# В конце каждой строки удалять лишние пробелы
trim_trailing_whitespace = true
```

![](http://editorconfig.org/logo.png)
