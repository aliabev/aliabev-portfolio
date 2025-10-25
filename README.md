# Aliabev Portfolio (Astro + Tailwind + MDX)

Готовый стартовый проект для портфолио с главной и детальными страницами кейсов.

## Структура
- `src/content/cases/*.mdx` — кейсы (контент).
- `public/assets/...` — изображения.
- `src/pages/index.astro` — главная.
- `src/pages/cases/[slug].astro` — страница кейса.

## Как редактировать контент (GitHub Web UI)
1. Открой `src/content/cases/` → **Add file → Create new file**.
2. Вставь шаблон MDX (frontmatter + текст).
3. Загрузить изображения: **Upload files** в `public/assets/...`.
4. Сохранить (Commit).

## Деплой на Vercel (без локальной установки)
1. Залей содержимое репозитория в GitHub.
2. В Vercel нажми **Add New… → Project → Import** из GitHub.
3. Framework: **Astro** (определится автоматически).
4. Build Command: `astro build` ; Output: `dist`.
5. Deploy.

## Аналитика (шаг 2)
- Добавить Яндекс.Метрику или Plausible в общий layout (или в `index.astro`/`[slug].astro`).

## Лицензия
MIT