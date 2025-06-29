```mermaid
gantt
    title Roadmap разработки GitRepoManager
    dateFormat  YYYY-MM-DD
    axisFormat  %d.%m
    
    section Проектирование
    Архитектурное проектирование       :des1, 2025-07-01, 3d
    Создание UI-прототипов             :des2, after des1, 2d
    
    section Фронтенд
    Разработка базового интерфейса     :front1, after des2, 4d
    Адаптация под Linux                :front2, after front1, 1d
    
    section Бэкенд
    Интеграция libgit2sharp (ядро)     :back1, after des2, 4d
    Реализация git-операций            :back2, after back1, 3d
    
    section API интеграции
    GitHub API подключение             :api1, after front2, 2d
    GitVerse/GitFlic API               :api2, after api1, 3d
    
    section Релиз
    Комплексное тестирование           :test1, after api2, 4d
    Кросс-платформенная сборка         :test2, after test1, 2d
