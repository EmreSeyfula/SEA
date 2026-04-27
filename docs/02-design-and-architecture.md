# Задание 2: Проектиране и архитектура на решението

## 1. Тип и структура на приложението

### Тип на приложението
Проектът BeReadyForExam е уеб приложение, разработено с ASP.NET Core MVC.

### Организация на проекта
Проектът е организиран по MVC архитектура:

- Controllers – обработват заявките;
- Models – описват данните;
- Views – визуализират информацията;
- Services – съдържат бизнес логиката;
- Data – работа с базата данни.

### Основни модули
- Модул за потребители и роли
- Модул за тестове (Exams)
- Модул за въпроси (Questions)
- Модул за опити (ExamAttempts)
- Модул за резултати

---

## 2. Модел на данните

### Основни таблици

#### Subjects
- Id
- Name
- Description

#### Topics
- Id
- Name
- SubjectId

#### Exams
- Id
- Title
- TopicId
- IsActive

#### Questions
- Id
- Text
- ExamId

#### Options
- Id
- Text
- IsCorrect
- QuestionId

#### ExamAttempts
- Id
- UserId
- ExamId
- StartedAt
- FinishedAt
- ScorePercent

#### AttemptAnswers
- Id
- AttemptId
- QuestionId
- SelectedOptionId
- IsCorrect

---

### Връзки между таблиците
- Subject → много Topics
- Topic → много Exams
- Exam → много Questions
- Question → много Options
- Exam → много Attempts
- Attempt → много Answers

---

## 3. Структурирано описание

| Клас | Роля |
|------|------|
| Subject | Представя учебен предмет |
| Topic | Представя тема |
| Exam | Представя тест |
| Question | Представя въпрос |
| Option | Представя отговор |
| ExamAttempt | Представя опит |
| AttemptAnswer | Представя отговор в опит |

---

## 4. Потребителски поток

### Основни страници
- Login/Register
- Списък с тестове
- Стартиране на тест
- Решаване на тест
- Резултат
- История

### Поток
1. Потребителят влиза в системата;
2. Избира тест;
3. Стартира тест;
4. Отговаря;
5. Предава теста;
6. Вижда резултат.

---

## 5. Използвани технологии

- C#
- ASP.NET Core MVC
- Entity Framework Core
- SQL Server
- HTML, CSS, Bootstrap
- JavaScript
- ASP.NET Identity

### Причина за избор
- ASP.NET Core – подходящ за уеб приложения;
- EF Core – улеснява работа с база данни;
- SQL Server – надеждна база;
- Bootstrap – бърз UI;
- Identity – готова система за потребители.
