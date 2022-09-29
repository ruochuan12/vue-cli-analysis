# Создание проекта

## vue create

Для создания нового проекта запустите команду:

```bash
vue create hello-world
```

::: warning Предупреждение
Если используете Git Bash с minTTY на Windows, то интерактивные подсказки не будут работать. Запускайте команды таким образом `winpty vue.cmd create hello-world`.
При желании использовать синтаксис `vue create hello-world` можно создать псевдоним для команды, добавив следующую строку в ваш файл `~/.bashrc`.
`alias vue='winpty vue.cmd'`
Необходимо будет перезапустить сеанс терминала Git Bash для использования обновлённого файла bashrc.
:::

Вам будет предложено выбрать пресет настроек. Можно выбрать пресет по умолчанию (default), который добавляет Babel + ESLint, или настройку вручную («Manually select features») для выбора требуемых возможностей в новом проекте.

![скриншот CLI](/cli-new-project.png)

Настройки по умолчанию отлично подходят для быстрого прототипирования нового проекта, в то время как настройка вручную предоставляет больше опций, которые могут потребоваться.

![скриншот CLI](/cli-select-features.png)

При выборе настройки вручную, в самом конце будет также предложено сохранить ваш выбор в качестве нового пресета настроек, чтобы воспользоваться им в будущем. Подробнее пресеты настроек и плагины мы обсудим в следующем разделе.

::: tip ~/.vuerc
Создаваемые пресеты сохраняются в JSON-файле `.vuerc` в домашнем каталоге вашего пользователя. Если вы захотите изменить сохранённые пресеты / настройки, можете это сделать отредактировав этот файл.

В процессе создания проекта, также может быть предложено выбрать предпочитаемый менеджер пакетов или использовать [Taobao зеркало для npm регистра](https://npmmirror.com/), чтобы ускорить установку зависимостей. Этот выбор также будет сохранён в `~/.vuerc`.
:::

Команда `vue create` предоставляет множество опций — вы можете изучить их все выполнив:

```bash
vue create --help
```

```
Использование: create [options] <app-name>

создание нового проекта с помощью vue-cli-service


Опции:

  -p, --preset <presetName>       Пропустить подсказки и использовать сохранённый или сторонний пресет настроек
  -d, --default                   Пропустить подсказки и использовать пресет настроек по умолчанию
  -i, --inlinePreset <json>       Пропустить подсказки и использовать вставленную строку JSON в качестве пресета настроек
  -m, --packageManager <command>  Использовать указанный npm клиент при установке зависимостей
  -r, --registry <url>            Использовать указанный npm регистр при установке зависимостей
  -g, --git [message|false]       Форсировать / пропустить инициализацию git, опционально указать сообщение к первому коммиту
  -n, --no-git                    Пропустить инициализацию git
  -f, --force                     Перезаписать целевой каталог, если такой уже есть
  -c, --clone                     Использовать git clone при загрузке стороннего пресета настроек
  -x, --proxy                     Использовать указанный прокси при создании проекта
  -b, --bare                      Развернуть проект не показывая инструкции для новичков
  -h, --help                      Вывод информации об использовании команды
```

## Использование GUI

Вы можете создавать и управлять проектами через графический интерфейс командой `vue ui`:

```bash
vue ui
```

Команда выше откроет окно браузера с графическим интерфейсом, в котором можно пройти те же шаги создания проекта.

![UI preview](/ui-new-project.png)

## Шаблоны для версии 2.x (старое поведение)

Vue CLI >= 3 использует команду `vue`, поэтому он перезаписывает Vue CLI 2 (`vue-cli`). Если вам по-прежнему необходимо старое поведение и функциональность команды `vue init`, нужно лишь установить глобально дополнительный плагин `@vue/cli-init`:

```bash
npm install -g @vue/cli-init
# vue init теперь работает точно также, как и в vue-cli@2.x
vue init webpack my-project
```