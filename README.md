name: Python UI Tests

on: [push]

jobs:
  test:
    runs-on: ubuntu-latest

    steps:
      # Шаг 1: Получить код из репозитория
      - name: Checkout code
        uses: actions/checkout@v3

      # Шаг 2: Установить Python
      - name: Set up Python
        uses: actions/setup-python@v4
        with:
          python-version: '3.10'  # Изменено на корректную версию Python (3.18 не существует)

      # Шаг 3: Установить зависимости
      - name: Install dependencies
        run: pip install -r requirements.txt

      # Шаг 4: Запустить тесты с помощью pytest
      - name: Run tests
        run: pytest -v
