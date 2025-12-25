# Система нейминга Figma для синхронизации с кодом

## Структура компонентов в коде

### Основные компоненты
- `AboutIntro` → `/src/components/AboutIntro.astro`
- `CaseCard` → `/src/components/CaseCard.astro`
- `Base` → `/src/layouts/Base.astro`

### Страницы
- `index` → `/src/pages/index.astro`
- `CaseDetail` → `/src/pages/cases/[slug].astro`

---

## Правила нейминга в Figma

### 1. Компоненты (Components)

**Формат:** `ComponentName` (PascalCase, как в коде)

**Примеры:**
- `AboutIntro` — компонент о себе
- `CaseCard` — карточка кейса
- `Base` — базовый layout

**В Figma:**
- Создайте Frame с именем компонента
- Сделайте его Component (⌘+⌥+K)
- Используйте точно такое же имя, как в коде

---

### 2. Внутренние элементы компонентов

**Формат:** `componentName_elementName` (camelCase)

**Примеры для AboutIntro:**
- `aboutIntro_container` — основной контейнер
- `aboutIntro_textBlock` — блок с текстом
- `aboutIntro_title` — заголовок
- `aboutIntro_description` — описание
- `aboutIntro_links` — блок ссылок (CV, Telegram)
- `aboutIntro_image` — изображение справа

**Примеры для CaseCard:**
- `caseCard_container` — основной контейнер
- `caseCard_title` — заголовок кейса
- `caseCard_summary` — блок с описанием
- `caseCard_metrics` — блок метрик
- `caseCard_metricItem` — отдельная метрика
- `caseCard_cover` — обложка кейса
- `caseCard_link` — ссылка "Открыть подробнее"

**Примеры для Base:**
- `base_main` — основной контент
- `base_footer` — футер

---

### 3. Варианты компонентов (Variants)

**Формат:** `ComponentName/VariantName`

**Примеры:**
- `CaseCard/Default`
- `CaseCard/WithMetrics`
- `CaseCard/WithoutCover`

---

### 4. Страницы (Pages)

**Формат:** `PageName` (PascalCase)

**Примеры:**
- `Index` — главная страница
- `CaseDetail` — страница детального кейса

---

### 5. Специальные элементы

**Иконки:**
- `Icon/Telegram` — иконка Telegram
- `Icon/Arrow` — стрелка

**Изображения:**
- `Image/About` — фото в блоке About
- `Image/CaseCover` — обложка кейса

---

## Структура файла в Figma

```
📁 Portfolio Design
  📄 Index (главная страница)
    └─ Frame: AboutIntro
       ├─ aboutIntro_container
       ├─ aboutIntro_textBlock
       │  ├─ aboutIntro_title
       │  ├─ aboutIntro_description
       │  └─ aboutIntro_links
       └─ aboutIntro_image
    
    └─ Frame: CaseCard (повторяющийся)
       ├─ caseCard_container
       ├─ caseCard_title
       ├─ caseCard_summary
       ├─ caseCard_metrics
       │  └─ caseCard_metricItem (×N)
       ├─ caseCard_cover
       └─ caseCard_link

  📄 CaseDetail (страница кейса)
    └─ Frame: CaseDetail
       ├─ caseDetail_header
       ├─ caseDetail_cover
       └─ caseDetail_content

  📁 Components (библиотека компонентов)
    └─ Component: AboutIntro
    └─ Component: CaseCard
    └─ Component: Base
```

---

## Рекомендации

### ✅ Делайте:
1. Используйте точно такие же имена, как в коде (PascalCase для компонентов)
2. Группируйте элементы внутри компонента с префиксом `componentName_`
3. Создавайте Variants для разных состояний
4. Используйте Auto Layout для соответствия структуре кода
5. Добавляйте комментарии в Figma с именами классов из кода

### ❌ Не делайте:
1. Не используйте пробелы в именах компонентов
2. Не используйте кириллицу в именах компонентов (только в тексте контента)
3. Не создавайте слишком глубокую вложенность (максимум 3-4 уровня)
4. Не смешивайте стили нейминга (используйте единый формат)

---

## Пример маппинга: AboutIntro

**Figma → Код:**

| Figma Layer | Code Element | Class/Component |
|------------|--------------|-----------------|
| `AboutIntro` | `<AboutIntro />` | Component |
| `aboutIntro_container` | `<section>` | `mt-8 md:mt-10` |
| `aboutIntro_textBlock` | `<div>` | (текст слева) |
| `aboutIntro_title` | `<h1>` | `text-[28px]...` |
| `aboutIntro_description` | `<div>` | `text-[18px] leading-[1.3]...` |
| `aboutIntro_links` | `<div>` | `gap-[31px]...` |
| `aboutIntro_image` | `<div>` | `relative h-[267px]...` |

---

## Плагины для автоматизации

Рекомендуемые плагины Figma:
- **Rename It** — массовое переименование слоёв
- **Figma to Code** — экспорт компонентов в код
- **Design Tokens** — синхронизация токенов дизайна

---

## Чеклист перед передачей в разработку

- [ ] Все компоненты названы как в коде (PascalCase)
- [ ] Внутренние элементы имеют префикс `componentName_`
- [ ] Нет пробелов в именах компонентов
- [ ] Структура слоёв соответствует структуре кода
- [ ] Variants созданы для разных состояний
- [ ] Комментарии добавлены с именами классов

