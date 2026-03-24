# Word Search Game - Specification

## Concept & Vision
Интерактивный филворд в стиле праздничной открытки на день рождения. Две спрятанные фразы — поздравление и извинение — пользователь находит их, выделяя буквы. Атмосфера радостная, но с ноткой нежности.

## Design Language
- **Aesthetic**: Минималистичный праздничный дизайн с мягкими тенями
- **Colors**:
  - Primary (phrase 1): #E53935 (красный)
  - Secondary (phrase 2): #EC407A (розовый)
  - Background: #FFF8E1 (кремовый)
  - Grid background: #FFFFFF
  - Text: #333333
  - Found highlight: rgba(76, 175, 80, 0.4)
- **Typography**: 'Nunito' для текста, sans-serif fallback
- **Motion**: Плавное выделение букв, появление фраз с fade-in

## Layout & Structure
```
┌─────────────────────────────────────────┐
│              WORD SEARCH                 │
│              (title)                    │
├─────────────────────┬───────────────────┤
│                     │  Found: 0/10      │
│                     │  Remaining: 10     │
│    LETTER GRID      │  ─────────────────│
│    (15x15)          │  Phrases:          │
│                     │  [hidden phrase 1] │
│                     │  [hidden phrase 2] │
│                     │  ─────────────────│
│                     │  [🔍 Hint]         │
└─────────────────────┴───────────────────┘
```

## Features & Interactions

### Grid
- 15x15 буквенная сетка
- Буквы фразы 1 выделены красным (#E53935)
- Буквы фразы 2 выделены розовым (#EC407A)
- Фразы расположены горизонтально и вертикально в случайном порядке

### Word Selection
- Клик и перетаскивание выделяют буквы
- Валидация: выделение должно совпадать с одним из слов
- При нахождении слова — буквы остаются подсвеченными
- Неверное выделение — сброс

### Progress Tracking
- Счётчик "Found: X" и "Remaining: Y"
- Обновляется при каждом найденном слове

### Phrase Reveal
- Фразы скрыты (показываются как "???")
- Раскрываются полностью когда все слова фразы найдены

### Hint Button
- Клик показывает confirm alert
- При подтверждении подсвечивает первую букву ненайденного слова на 2 секунды

## Words List
**Phrase 1 (красный):** Sorry, I, was, late (4 words)
**Phrase 2 (розовый):** Happy, birthday, Stasy (3 words)

## Technical Approach
- Single HTML file with embedded CSS and JS
- Canvas или CSS Grid для сетки
- Vanilla JavaScript для логики
- Google Fonts: Nunito
