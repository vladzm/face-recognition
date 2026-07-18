# Face Recognition - DLS

Итоговый проект курса Deep Learning School: выравнивание лиц (face alignment), обучение с ArcFace, полный пайплайн распознавания лиц.

Все выводы, графики и комментарии по результатам - внутри ноутбуков. Выполнение полностью локальное, пути к данным в ноутбуках указаны локальные (см. раздел «Как воспроизвести» ниже).

## Структура репозитория

```
notebooks/
  face_aligment_solution.ipynb          - выравнивание лиц 
  2_ArcFace_solution (1).ipynb          - обучение модели с ArcFace loss
  3_FaceRecognitionPipeline_solution.ipynb - итоговый пайплайн распознавания лиц

annotation/
  aligned_dataset.csv                   - датасет выровненных лиц (пути, разметка)
  selected_mainset.csv                  - отобранное подмножество для обучения/валидации

group_photo/
  images.png                            - групповое фото для проверки пайплайна распознавания
```

## Что НЕ лежит в репозитории (слишком большие файлы)

Веса моделей и часть данных превышают разумный размер для Git-репозитория, поэтому загружены на Google Диск:

**Веса моделей** (`arcface_best.pt`, `ce_best.pt`, `best_hourglass.pt`):
https://drive.google.com/drive/folders/1n7_ZNPNKmN-EXz20UaMfAd8XHZMwPhLp?usp=share_link

**Сырые аннотации CelebA** (`identity_CelebA.txt`, `list_attr_celeba.txt`, `list_bbox_celeba.txt`, `list_landmarks_celeba.txt`, `list_landmarks_align_celeba.txt`):
https://drive.google.com/drive/folders/1ev1vYnfGG9J8xhr2HaMB3flE1LkvTH2g?usp=share_link

**faces_aligned/** (выровненные лица):
https://drive.google.com/drive/folders/1-pr9DK8VmUWJ1xyCA6X2MYbey5ClaUaJ?usp=share_link

**faces_cropped/** (кропнутые лица):
https://drive.google.com/drive/folders/1T9mhikAh8HSLzDXeG-sK1FynsIDB1s3C?usp=share_link

**img_celeba/** (исходные изображения CelebA) - не загружены на Диск из-за размера, скачиваются из оригинального источника датасета: [CelebA dataset](https://mmlab.ie.cuhk.edu.hk/projects/CelebA.html).

## Как воспроизвести

1. Склонировать репозиторий.
2. Скачать веса моделей и данные по ссылкам выше, `img_celeba/` - из оригинального источника CelebA.
3. Разложить файлы по путям, ожидаемым в ноутбуках (пути внутри ноутбуков - локальные, при необходимости поправить под свою структуру папок).
4. Запускать ноутбуки в указанном порядке: `face_aligment_solution.ipynb` -> `2_ArcFace_solution (1).ipynb` -> `3_FaceRecognitionPipeline_solution.ipynb`.

## Как должен выглядеть проект после добавления всех папок и файлов

```
face-recognition/
├── notebooks/
│   ├── face_aligment_solution.ipynb
│   ├── 2_ArcFace_solution (1).ipynb
│   └── 3_FaceRecognitionPipeline_solution.ipynb
├── annotation/
│   ├── aligned_dataset.csv
│   ├── selected_mainset.csv
│   ├── identity_CelebA.txt              (с Google Диска)
│   ├── list_attr_celeba.txt              (с Google Диска)
│   ├── list_bbox_celeba.txt              (с Google Диска)
│   ├── list_landmarks_celeba.txt         (с Google Диска)
│   └── list_landmarks_align_celeba.txt   (с Google Диска)
├── models_weight/                        (с Google Диска)
│   ├── arcface_best.pt
│   ├── ce_best.pt
│   └── best_hourglass.pt
├── faces_aligned/                        (с Google Диска)
├── faces_cropped/                        (с Google Диска)
├── img_celeba/                           (скачать с оригинального источника CelebA)
├── group_photo/
│   └── images.png
├── README.md
└── .gitignore
```
