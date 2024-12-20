Visual Dependency Graph Generator
Описание проекта
Инструмент командной строки для визуализации графа зависимостей коммитов в git-репозитории.
Граф строится для коммитов, в которых изменялся файл с указанным хеш-значением, и визуализируется с помощью PlantUML.

Функциональность
Анализ репозитория:
Находит коммиты, содержащие изменения файла с указанным хеш-значением.
Построение графа зависимостей:
Сообщения коммитов отображаются как узлы графа.
Стрелки между узлами показывают транзитивные зависимости.
Визуализация:
Генерирует граф в виде изображения с использованием PlantUML.
Требования
Python 3.6+
Java 8+ (для работы с PlantUML)
PlantUML (plantuml.jar)
Git (должен быть установлен на машине)
Установка и запуск
1. Клонирование проекта
Склонируйте репозиторий:

bash
Копировать код
git clone <URL-репозитория>
cd <папка_проекта>
2. Настройка конфигурации
Создайте файл config.ini в корне проекта со следующим содержимым:

ini
Копировать код
[settings]
visualizer_path = /path/to/plantuml.jar      # Путь к PlantUML JAR-файлу
repository_path = /path/to/repository        # Путь к git-репозиторию
file_hash = abc1234567890                    # Хеш-значение файла
Пример путей:

visualizer_path = /home/user/plantuml/plantuml.jar (Linux/Mac)
repository_path = C:/projects/myrepo (Windows)
3. Установка зависимостей
Убедитесь, что Python установлен. Установите pytest для тестирования (необязательно):

bash
Копировать код
pip install pytest
4. Запуск проекта
Выполните скрипт:

bash
Копировать код
python visualizer.py
5. Результат
После выполнения скрипта в текущей директории будут созданы:

graph.puml — текстовое описание графа в формате PlantUML.
graph.png — изображение графа зависимостей.
Тестирование
Запустите тесты с помощью pytest:

bash
Копировать код
pytest test_visualizer.py
Пример использования
Генерация графа:

Скрипт найдёт все коммиты, в которых изменялся указанный файл.
Создаст граф зависимостей коммитов.
Просмотр результата:

Откройте файл graph.png в любом просмотрщике изображений.