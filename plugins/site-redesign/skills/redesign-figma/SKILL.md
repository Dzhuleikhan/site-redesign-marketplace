---
name: redesign-figma
description: >
  This skill should be used after the user picked a redesign concept variant, when they
  ask to design the whole site in Figma: "/redesign-figma", "делаем этот вариант",
  "рисуй все страницы в фигме", "переноси концепт в фигму", "design every page in Figma".
  Builds every page, modal and state of the site (home included, in the themes the user picks — dark,
  light or both — desktop and mobile) in Figma from the chosen concept with a multi-agent pipeline, then runs a
  design review. No code is written on this step.
metadata:
  version: "0.5.0"
---

# Весь сайт в Figma по концепту

Код на этом шаге не трогать совсем. Источник истины для всего, что будет дальше, — фреймы Figma.

1. Прочитать `.redesign/STATE.md`: выбран ли вариант концепта. Нет — спросить и остановиться.
2. Прочитать из `redesign-playbook`: `figma-pipeline.md` (главный файл шага), `lessons.md`,
   `structure-inventory.md`.
3. Спросить одним сообщением (карточкой вопросов, если она есть) и ждать ответа:
   - **темы**: только тёмная, только светлая или обе;
   - **ссылка на Figma-файл** (коннектор Figma должен быть подключён).
   Записать выбор тем в `.redesign/STATE.md` и в `BRIEF.md`: дальше каждый агент рисует и
   проверяет только выбранные темы. Создать в файле новую страницу рядом с существующими;
   остальные страницы файла не трогать.
4. Подготовить рабочую папку конвейера (`BRIEF.md`, `DECISIONS.md`, `inventory.md`) и пакеты
   работ по `figma-pipeline.md`. Канон — артборды выбранного варианта на холсте.
5. Пакеты по одному агенту, в порядке: хром и кит → главная → страницы по разделам →
   недостающие страницы и состояния → модалки → мобильные 375. Выбранные темы на каждом шаге.
   Менеджер читает отчёт, записывает новые решения в `DECISIONS.md`, запускает следующего.
6. **Ревью дизайна** отдельным агентом, который фреймы не рисовал: структура против описи,
   планка качества, поломки вёрстки, совпадение тёмной и светлой темы (если выбраны обе). Найденное — исправить.
7. Отметить фреймы в `.redesign/STATE.md` (маршрут → id фреймов выбранных тем, 1440 и 375).

## Точка утверждения

Остановиться: «Весь дизайн в Figma. Посмотри страницу <ссылка>. Если всё ок — пишу код»
(навык `redesign-code`). Правки по комментариям — в Figma, через агентов, с записью правила
в `DECISIONS.md`.
