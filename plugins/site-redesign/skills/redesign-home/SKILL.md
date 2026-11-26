---
name: redesign-home
description: >
  This skill should be used when the user has picked a redesign variant and asks to
  implement it: "/redesign-home", "делаем этот вариант", "пиши код главной", "переписывай
  главную под макет", "implement the chosen design on the home page". Rewrites the theme
  layer, fonts, header, sidebar, footer, the home page sections and the sign-in/sign-up
  modals to match the chosen mockup in both themes, then verifies block by block.
metadata:
  version: "0.2.0"
---

# Код главной под выбранный вариант

1. Прочитать `.redesign/STATE.md` (опись, выбранный вариант, ссылку на холст). Нет файла или
   не выбран вариант — спросить, какой холст и вариант, и остановиться.
2. Прочитать навык `project-rules` целиком и из `redesign-playbook`:
   `references/lessons.md`, `references/implementation.md`, `references/verification.md`.
3. Прочитать артборды выбранного варианта с холста (главная тёмная/светлая, модалка
   тёмная/светлая) — это эталон. Не работать по памяти.
4. Убедиться, что пользователь на нужной ветке (`git --no-optional-locks status` / `git branch
   --show-current`); ветку не создавать и не переключать — если она не подходит, спросить.
5. Список задач: один пункт на слой каркаса, на каждую секцию главной из описи, на каждую
   модалку, последний пункт — общая сверка и саморевью диффа.
6. Реализовать по `implementation.md` в порядке: переменные темы → шрифты → хедер → сайдбар
   (вкл. свёрнутый и нижние кнопки) → футер → секции сверху вниз → модалки → мобильная
   навигация.
7. После КАЖДОГО пункта — сверка по `verification.md` (1440 и 375, обе темы).
8. Саморевью: прочитать весь дифф (`git diff`), прогнать по правилам `project-rules`,
   починить своё.
9. Отчёт: что сделано (2–3 строки), раздел «расхождения с макетом», напоминание запустить
   typecheck/lint/тесты. Обновить `.redesign/STATE.md`.

## Точка утверждения

Остановиться: «Посмотри главную. Если всё ок — раскатываю на весь сайт» (навык `redesign-site`).
