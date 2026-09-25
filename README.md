# 🛍️ Tajir POS

**Tajir POS** is an offline-first mobile point-of-sale and billing application built with Flutter. Designed for small and medium retail shops, it handles the full checkout flow on-device: product catalog, barcode scanning, cart billing, and Bluetooth thermal receipt printing — no internet connection required.

## ✨ Features

- **Product management** — full CRUD inventory with barcode/QR code support
- **Smart checkout** — build carts fast via camera barcode scanning or manual entry, with automatic totals and taxes
- **Bluetooth thermal printing** — print itemized receipts directly to a thermal POS printer
- **Shop profile** — customizable shop details printed on every receipt
- **100% offline** — local Hive NoSQL database; works with zero connectivity

## 🛠 Tech Stack

- **Framework**: [Flutter](https://flutter.dev/) (SDK >= 3.1.0)
- **State management**: `flutter_bloc`
- **DI**: `get_it`
- **Routing**: `go_router`
- **Local database**: `hive` / `hive_flutter`
- **Hardware**: `mobile_scanner` (barcodes), `print_bluetooth_thermal`

Architecture: feature-first Clean Architecture (`data` / `domain` / `presentation` per feature).

```text
lib/
├── core/            # theme, widgets, utils, DI, Hive setup, error models
└── features/
    ├── billing/     # cart, checkout, invoice generation
    ├── product/     # inventory management
    ├── settings/    # app + printer configuration
    └── shop/        # shop details
```

## 🚀 Getting Started

### Prerequisites

- Flutter SDK `^3.1.0`
- Android Studio (or Xcode) for building
- Optional: a physical Android device + Bluetooth thermal printer for hardware testing

### Run

```bash
git clone https://github.com/malother/tajir-pos.git
cd tajir-pos
flutter pub get
dart run build_runner build --delete-conflicting-outputs
flutter run
```

### Build release APK

```bash
flutter build apk --release
```

## 📄 License

This project is released as-is for personal and commercial use.
