# Face Recognition — DLS

Итоговый проект курса Deep Learning School: выравнивание лиц (face alignment), обучение с ArcFace, полный пайплайн распознавания лиц.

Все выводы, графики и комментарии по результатам — прямо внутри ноутбуков. Выполнение полностью локальное, пути к данным в ноутбуках указаны локальные (см. раздел «Как воспроизвести» ниже).

## Структура репозитория

```
notebooks/
  face_aligment_solution.ipynb          — выравнивание лиц (бывш. "Решение1.ipynb")
  2_ArcFace_solution (1).ipynb          — обучение модели с ArcFace loss
  3_FaceRecognitionPipeline_solution.ipynb — итоговый пайплайн распознавания лиц

annotation/
  aligned_dataset.csv                   — датасет выровненных лиц (пути, разметка)
  selected_mainset.csv                  — отобранное подмножество для обучения/валидации

group_photo/
  images.png                            — групповое фото для проверки пайплайна распознавания
```

## Что НЕ лежит в репозитории (слишком большие файлы)

Веса моделей и часть данных превышают разумный размер для Git-репозитория, поэтому загружены на Google Диск:

**Веса моделей** (`arcface_best.pt`, `ce_best.pt`, `best_hourglass.pt`):
[ССЫЛКА НА GOOGLE ДИСК — models_weight]

**Изображения и сырые аннотации CelebA** (`faces_aligned/`, `faces_cropped/`, `img_celeba/`, а также оригинальные файлы аннотаций CelebA — `identity_CelebA.txt`, `list_attr_celeba.txt`, `list_bbox_celeba.txt`, `list_landmarks_celeba.txt`, `list_landmarks_align_celeba.txt`):
[ССЫЛКА НА GOOGLE ДИСК — данные]

## Как воспроизвести

1. Склонировать репозиторий.
2. Скачать веса моделей и данные по ссылкам выше.
3. Разложить файлы по путям, ожидаемым в ноутбуках (пути внутри ноутбуков — локальные, при необходимости поправить под свою структуру папок).
4. Запускать ноутбуки в указанном порядке: `face_aligment_solution.ipynb` → `2_ArcFace_solution (1).ipynb` → `3_FaceRecognitionPipeline_solution.ipynb`.
