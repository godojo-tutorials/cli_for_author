# GoDojo Author CLI

[🇺🇸 English](#english) | [🇷🇺 Русский](#русский)

---

## English

An interactive CLI tool for creating educational content for the GoDojo platform.

### 🚀 Quick Start

#### Download

Choose the appropriate binary for your operating system:

**⚠️ Important**: Only download from official GitHub releases to ensure security and compatibility.

| Platform | Architecture | File |
|----------|-------------|------|
| Linux | x86_64 | [`godojo-author-linux-amd64`](godojo-author-linux-amd64) |
| Linux | ARM64 | [`godojo-author-linux-arm64`](godojo-author-linux-arm64) |
| macOS | Intel | [`godojo-author-macos-intel-amd64`](godojo-author-macos-intel-amd64) |
| macOS | Apple Silicon | [`godojo-author-macos-silicon-arm64`](godojo-author-macos-silicon-arm64) |
| Windows | x86_64 | [`godojo-author-windows-amd64.exe`](godojo-author-windows-amd64.exe) |

#### Installation

```bash
# Make the file executable (macOS/Linux)
chmod +x godojo-author-linux-amd64

# Test functionality
./godojo-author-linux-amd64 --version
```

#### First Use

1. **Initialize author profile:**
```bash
./godojo-author-linux-amd64 init
```

2. **Start interactive mode:**
```bash
./godojo-author-linux-amd64
```

3. **Create a new topic:**
```bash
godojo> create topic
```

### 📋 Features

- **Interactive mode** with autocompletion and command history
- **Author profile management** with expertise configuration
- **Educational content creation** across structured categories
- **Automatic template generation** with proper frontmatter
- **Content quality validation** (800+ words, 3+ code examples)
- **Multi-language support** (Russian and English interface)

### 🗂️ Content Structure

```
content/
├── basics/           # Language fundamentals
├── concurrency/      # Concurrent programming
├── web/              # Web development
├── database/         # Database operations
├── testing/          # Testing
├── production/       # Production-ready code
├── performance/      # Performance optimization
├── frameworks/       # Frameworks and libraries
└── security/         # Security
```

### 🛠️ Main Commands

#### Interactive Mode
```bash
create topic     # Create a new topic
check structure  # Check repository structure
status          # View status
config          # Configuration management
validate        # Content validation
list            # List created content
help            # Help
```

#### Direct Commands
```bash
./godojo-author init           # Initialize profile
./godojo-author create topic   # Create topic
./godojo-author status         # View status
```

### 📖 Content Requirements

- ✅ Minimum **800 words** of text
- ✅ Minimum **3 working Go code examples**
- ✅ Minimum **2 practical exercises**
- ✅ All code examples must **compile**
- ✅ Properly formatted **frontmatter**

### 📚 Documentation

- [Complete User Guide](user-guide.en.md)

---

## Русский

Интерактивный CLI-инструмент для создания образовательного контента для платформы GoDojo.

### 🚀 Быстрый старт

#### Скачивание

Выберите подходящий бинарник для вашей операционной системы:

**⚠️ Важно**: Скачивайте только с официальных GitHub releases для обеспечения безопасности и совместимости.

| Платформа | Архитектура | Файл |
|-----------|-------------|------|
| Linux | x86_64 | [`godojo-author-linux-amd64`](godojo-author-linux-amd64) |
| Linux | ARM64 | [`godojo-author-linux-arm64`](godojo-author-linux-arm64) |
| macOS | Intel | [`godojo-author-macos-intel-amd64`](godojo-author-macos-intel-amd64) |
| macOS | Apple Silicon | [`godojo-author-macos-silicon-arm64`](godojo-author-macos-silicon-arm64) |
| Windows | x86_64 | [`godojo-author-windows-amd64.exe`](godojo-author-windows-amd64.exe) |

#### Установка

```bash
# Сделайте файл исполняемым (macOS/Linux)
chmod +x godojo-author-linux-amd64

# Проверьте работу
./godojo-author-linux-amd64 --version
```

#### Первое использование

1. **Инициализация профиля автора:**
```bash
./godojo-author-linux-amd64 init
```

2. **Запуск интерактивного режима:**
```bash
./godojo-author-linux-amd64
```

3. **Создание новой темы:**
```bash
godojo> create topic
```

### 📋 Возможности

- **Интерактивный режим** с автодополнением и историей команд
- **Управление профилем автора** с настройкой экспертизы
- **Создание образовательного контента** по структурированным категориям
- **Автоматическая генерация шаблонов** с правильным frontmatter
- **Валидация качества контента** (800+ слов, 3+ примера кода)
- **Поддержка нескольких языков** (русский и английский интерфейс)

### 🗂️ Структура контента

```
content/
├── basics/           # Основы языка
├── concurrency/      # Параллельное программирование
├── web/              # Веб-разработка
├── database/         # Работа с базами данных
├── testing/          # Тестирование
├── production/       # Production-ready код
├── performance/      # Оптимизация производительности
├── frameworks/       # Фреймворки и библиотеки
└── security/         # Безопасность
```

### 🛠️ Основные команды

#### В интерактивном режиме
```bash
create topic     # Создать новую тему
check structure  # Проверить структуру репозитория
status          # Просмотреть статус
config          # Управление конфигурацией
validate        # Валидация контента
list            # Список созданного контента
help            # Справка
```

#### Прямые команды
```bash
./godojo-author init           # Инициализация профиля
./godojo-author create topic   # Создание темы
./godojo-author status         # Просмотр статуса
```

### 📖 Требования к контенту

- ✅ Минимум **800 слов** текста
- ✅ Минимум **3 рабочих примера** кода Go
- ✅ Минимум **2 практических упражнения**
- ✅ Все примеры кода должны **компилироваться**
- ✅ Правильно оформленный **frontmatter**

### 📚 Документация

- [Полное руководство пользователя](user-guide.md)

---

## 🌟 Features / Особенности

- **Self-contained binaries** with no dependencies / **Самодостаточные бинарники** без зависимостей
- **Cross-platform support** / **Кроссплатформенность**
- **Interactive REPL** with autocompletion / **Интерактивный REPL** с автодополнением
- **Real-time validation** / **Валидация в реальном времени**

## 📄 License / Лицензия

This software is proprietary. See [LICENSE.txt](LICENSE.txt) for complete terms and conditions.  
Это программное обеспечение является проприетарным. См. [LICENSE.txt](LICENSE.txt) для ознакомления с полными условиями использования.

## 🤝 GoDojo Ecosystem / Экосистема

This CLI tool is part of the GoDojo educational platform ecosystem.  
Этот CLI-инструмент является частью образовательной экосистемы GoDojo.

---

**Version / Версия**: Latest stable / Последняя стабильная  
**Support / Поддержка**: support@godojo.dev