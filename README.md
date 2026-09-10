# Rust Microservice Template

Шаблон Rust микросервиса с задачами VS Code для сборки, тестирования, отладки и проверки качества кода.

## Требования

- Rust (stable toolchain)
- VS Code с расширениями:
  - rust-analyzer
  - CodeLLDB (для отладки)
- LLDB

## Быстрый старт

Запустите задачу инициализации из VS Code:

1. Откройте палитру команд: `Ctrl+Shift+P` / `Cmd+Shift+P`
2. Выберите `Tasks: Run Task`
3. Выберите `project: init`

Это выполнит:
- Генерацию `rust.code-workspace` для multi-root workspace
- Инициализацию Cargo проекта (`cargo init`)
- Настройку `launch.json` с именем пакета из `Cargo.toml`

## Доступные задачи

### Сборка
- `cargo: build` — debug сборка (задача сборки по умолчанию)
- `cargo: build --release` — release сборка с оптимизациями
- `cargo: build workspace` — сборка всех членов workspace
- `cargo: check` — быстрая проверка кода без артефактов
- `cargo: check workspace` — проверка всех членов workspace

### Запуск
- `cargo: run` — запуск debug сборки
- `cargo: run --release` — запуск release сборки

### Тестирование
- `cargo: test` — запуск тестов (задача тестирования по умолчанию)
- `cargo: test workspace` — запуск тестов всего workspace
- `cargo: test package` — запуск тестов для конкретного пакета

### Качество кода
- `cargo: clippy` — запуск Clippy линтера с строгими предупреждениями
- `cargo: fmt check` — проверка форматирования кода
- `cargo: fmt` — автоформатирование кода

### Документация
- `cargo: doc` — генерация документации
- `cargo: bench` — запуск бенчмарков
- `cargo: bench package` — запуск бенчмарков для конкретного пакета

### Обслуживание
- `cargo: clean` — очистка артефактов сборки
- `cargo: update dependencies` — обновление Cargo.lock
- `workspace: generate` — генерация rust.code-workspace
- `template: configure` — настройка launch.json с именем пакета
- `project: init` — полная последовательность инициализации проекта
- `Build All Workspace` — сборка + clippy + проверка форматирования
- `Test All Workspace` — запуск всех тестов workspace

## Отладка

Конфигурации запуска доступны в `.vscode/launch.json`:

- **Launch (debug)** — запуск приложения в debug режиме
- **Launch (release)** — запуск release сборки
- **Test (debug)** — отладка тестов (один поток)
- **Attach to process** — присоединение LLDB к запущенному процессу

## Стиль кода

Настроен в `.vscode/settings.json`:
- `rust-analyzer.checkOnSave: true` — запуск clippy при сохранении
- `editor.formatOnSave: true` — форматирование при сохранении
- `rust-analyzer.check.command: "clippy"` — использовать clippy вместо cargo check
- `rust-analyzer.cargo.features: "all"` — включить все фичи для анализа

## Структура проекта

```
<project-name>/
├── .vscode/
│   ├── launch.json      # Конфигурации отладки
│   ├── tasks.json       # Задачи сборки/тестирования/линта
│   └── settings.json    # Настройки редактора и rust-analyzer
├── src/
│   └── main.rs
├── Cargo.toml
├── Cargo.lock
└── README.md
```
