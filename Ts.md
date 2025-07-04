## **Техническое задание**

### **Название проекта:**

**GitRepoManager** — настольное приложение с проводниковым интерфейсом для управления репозиториями на популярных git-платформах.

---

### **1. Общая цель**

Разработка кроссплатформенного приложения (Windows и Linux) для управления репозиториями на таких сервисах, как GitHub, GitVerse и GitFlic. Инструмент должен предоставлять визуальные средства работы с файлами и папками в репозиториях, а также включать возможности Git-контроля версий.

---

### **2. Основной функционал**

#### **2.1. Взаимодействие с репозиториями**

* Поддержка авторизации на следующих платформах:
  * GitHub  
  * GitVerse  
  * GitFlic  

* Отображение всех доступных пользователю репозиториев  
* Возможность клонирования репозиториев локально  
* Создание нового репозитория с выбором платформы  
* Удаление репозитория при наличии соответствующих прав  

#### **2.2. Визуальное управление содержимым**

* Представление структуры репозитория в виде дерева (аналогично Windows Explorer)  
* Возможности:
  * Создание и удаление папок  
  * Загрузка и удаление файлов  
  * Переименование файлов и папок  
  * Перемещение элементов внутри репозитория  
* Drag-and-drop поддержка для перемещения содержимого  

#### **2.3. Git-функции**

* Отображение активной ветки и переключение между ветками  
* Стадия изменений, коммиты и отправка в удалённый репозиторий  
* Просмотр истории коммитов  
* Работа с ветками (создание, удаление, слияние)  
* Обработка конфликтов при merge  

#### **2.4. Локализация и настройки**

* Интерфейс приложения на русском языке  
* Настройки:
  * Указание директории для локального хранения  
  * Выбор редактора по умолчанию для открытия файлов  

---

### **3. Технические требования**

#### **3.1. Языки и технологии**

* Основной стек: C# с использованием .NET 6+  
* UI реализуется через **Avalonia UI** для поддержки нескольких платформ  
* Альтернатива: WPF (если кроссплатформенность не требуется на первом этапе)  

#### **3.2. Совместимость с ОС**

* Windows 10 и выше  
* Современные дистрибутивы Linux  

#### **3.3. Локальное хранилище и Git-интеграция**

* Данные и настройки сохраняются локально с использованием SQLite или JSON  
* Git-операции выполняются с помощью libgit2sharp либо через установленный Git-клиент  

---

### **4. Интерфейс пользователя (UI/UX)**

#### **Главное окно**

* Слева — дерево репозиториев и их структуры  
* Справа — содержимое выбранной директории  
* Верхняя панель — основные действия: создание, импорт, коммит, push, доступ к настройкам  
* Нижняя панель — отображение текущей ветки и статуса изменений  

#### **Всплывающие окна и диалоги**

* Авторизация  
* Создание репозитория  
* История коммитов  
* Обработка конфликтов  

---

### **5. План разработки**

| Этап       | Задача                                         | Примерный срок |
|------------|------------------------------------------------|----------------|
| Этап 1     | Проектирование архитектуры и UI-прототипа      | 3 дня          |
| Этап 2     | Создание интерфейса без подключения логики     | 4–5 дней       |
| Этап 3     | Интеграция Git-функциональности                | 4–6 дней       |
| Этап 4     | Работа с API GitHub/GitVerse/GitFlic           | 4–5 дней       |
| Этап 5     | Финальное тестирование и сборка под Win/Linux  | 3–5 дней       |
| **Всего:** | **Примерно 2–3 недели разработки**             |                |

---
