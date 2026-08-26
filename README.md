# roblox-game-template

Шаблон тайтла для фабрики Roblox-игр. Логика живёт в ядре
[`robloxcore`](https://github.com/DaniilMurai/robloxcore), подключённом сабмодулем;
тайтл отличается от шаблона файлом `configs/main.json` и содержимым `src/`.

## Завести новый тайтл

```bash
./tools/new-game.sh <slug> "<Отображаемое имя>"
```

## Проверки

```bash
rokit install
git submodule update --init --recursive
wally install
lune run tests/run.luau                       # конфиг проходит валидатор ядра
selene src
stylua --check src tests
rojo build -o build.rbxl
```

Живой синк со Studio: `rojo serve`, в Studio — плагин Rojo, Connect.

## Выкат

```bash
export ROBLOX_API_KEY=... ROBLOX_UNIVERSE_ID=... ROBLOX_PLACE_ID=...
./tools/publish.sh Saved       # staging-версия
./tools/publish.sh Published   # релиз
```
