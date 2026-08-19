# 🩻 PancreasView — Интерактивная сегментация КТ брюшной полости

[![Live Demo](https://img.shields.io/badge/🔗-Live_Demo-8b5cf6)](https://adrenolitik.github.io/medsam2/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![SAM2](https://img.shields.io/badge/Meta-SAM2-blue)](https://github.com/facebookresearch/sam2)

> Интерактивная сегментация КТ брюшной полости с использованием Segment Anything Model 2 от Meta — кликните для установки точек промпта, получайте мгновенные маски сегментации с оценкой Dice и IoU.

**[Попробовать демо →](https://adrenolitik.github.io/medsam2/)**

---

## Что делает это приложение

Загрузите КТ-снимок брюшной полости. Кликните на изображение для установки точек промпта. Получите мгновенные маски сегментации с:

- Коэффициент сходства Dice (Dice Similarity Coefficient)
- Оценка IoU (Intersection over Union)
- Разбор по органам
- Визуализация тепловой карты внимания SAM2
- Поддержка многоточечного промптинга
- Измерение задержки в реальном времени

## Поддерживаемая модальность

| Модальность | Органы/Структуры |
|------------|------------------|
| 🩻 **КТ брюшной полости** | Печень, Почка слева, Почка справа, Селезенка, **Поджелудочная железа** |

## Конвейер SAM2

```
Медицинское изображение
      │
      ▼
┌─────────────────┐
│  Hiera Encoder  │  Изображение → 256-мерные признаки патчей
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│ Prompt Encoder  │  Точки клика → разреженные эмбеддинги
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│  Mask Decoder   │  Двустороннее трансформерное внимание
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│  Multi-Scale    │  FPN → маска высокого разрешения
│  Fusion (FPN)   │
└────────┬────────┘
         │
         ▼
  Маска + Dice + IoU
```

## Использование

Откройте `index.html` в любом браузере. Никакой настройки, установки или API-ключа не требуется.

Или используйте живую демо: **https://adrenolitik.github.io/medsam2/**

## Научный контекст

- Ravi et al. (2024) — SAM 2: Segment Anything in Images and Videos (Meta FAIR)
- Ma et al. (2024) — Segment Anything in Medical Images (MedSAM, Nature Communications)
- Связанное: False Negative Induction in Brain Tumor Segmentation by Trained Noise Attack (IEEE, 2023)

---

*Переработано в PancreasView · [GitHub](https://github.com/adrenolitik/medsam2)*