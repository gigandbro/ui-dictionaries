# polygram-i18n

```
https://raw.githubusercontent.com/gigandbro/polygram-i18n/main/i18n/en.json
https://raw.githubusercontent.com/gigandbro/polygram-i18n/main/i18n/uk.json
```

Русский язык в Polygram встроен в код; English и Українська приложение
скачивает **один раз**, при выборе языка в настройках, и сохраняет локально.

## Формат

```json
{
  "format": 1,
  "language": "en",
  "count": 787,
  "entries": { "Сегодня": "Today", … }
}
```

Ключ — точный русский текст из исходников. Непокрытые строки остаются
русскими. Версия формата проверяется приложением перед применением.

## Синхронизация

Словари здесь — зеркало файлов `i18n/en.json` и `i18n/uk.json` из основного
репозитория Polygram. После изменения строк интерфейса запустите из корня
основного репозитория:

```bash
python3 tools/i18n_extract.py        # обновит i18n/_keys.json
# …пополните i18n/en.json и i18n/uk.json новыми ключами…
python3 tools/i18n_publish.py        # проверит и отправит зеркала сюда
```

Проверка полноты (каждый ключ переведён, плейсхолдеры `{n}` на месте) входит
в CI основного репозитория: `python3 tools/i18n_check.py`.
