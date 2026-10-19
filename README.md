# WhatInMyFridge

Aplikasi iOS untuk mendeteksi bahan makanan dari foto atau kamera live, lalu memberikan rekomendasi resep secara on-device.

## Tampilan Aplikasi

<img width="2362" height="1029" alt="Fridge App" src="https://github.com/user-attachments/assets/9e52a237-1a6b-4c2e-be78-82485b927cb3" />

## Fitur

- **Klasifikasi gambar** — unggah atau ambil foto bahan makanan, dianalisis dengan Core ML (`MyImageClassifier`)
- **Live Scanner** — deteksi objek makanan secara real-time lewat kamera dengan bounding box (`FoodObjectDetector`)
- **Rekomendasi resep** — generate resep + estimasi nutrisi memakai Apple Foundation Models (Apple Intelligence)
- **Feedback** — analisis sentimen terhadap feedback pengguna

## Tech Stack

| Layer | Teknologi |
| --- | --- |
| UI | SwiftUI |
| Vision / ML | Vision, Core ML |
| Kamera | AVFoundation |
| Generative AI | Foundation Models (on-device) |

## Struktur Project

```
WhatInMyFridge/
├── App/                  # Entry point
├── Models/               # Detection, FoodResult, RecipeModels
├── Views/                # Home, Live Scanner, Result, Recipe, Feedback
├── ViewModels/           # RecipeViewModel
├── Services/             # Classifier, Camera, Foundation Models, Sentiment
└── Resources/            # Assets + model Core ML
```

## Requirements

- Xcode terbaru (dengan dukungan Foundation Models / Apple Intelligence)
- Perangkat iOS fisik direkomendasikan (kamera + Apple Intelligence)
- Izin kamera saat memakai Live Scanner

## Cara Menjalankan

1. Buka `WhatInMyFridge.xcodeproj` di Xcode
2. Pilih target device / simulator
3. Build & Run (`⌘R`)

> Catatan: Live Scanner dan Apple Intelligence paling baik diuji di device fisik. Simulator memakai fallback CPU-only untuk inference.

## Alur Singkat

1. User pilih foto atau buka Live Scanner
2. Model Core ML mendeteksi / mengklasifikasi bahan
3. Hasil ditampilkan di Result View
4. User bisa generate resep dari bahan yang terdeteksi
