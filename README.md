[README.md](https://github.com/user-attachments/files/32697527/README.md)
# 🛒 Kirana ERP & POS with AI Voice Assistant (કિરાણા એપ)

[![Android](https://img.shields.io/badge/Platform-Android%208.0%2B%20(API%2026%2B)-green.svg)](https://developer.android.com)
[![Kotlin](https://img.shields.io/badge/Kotlin-2.0%2B-blue.svg)](https://kotlinlang.org)
[![Jetpack Compose](https://img.shields.io/badge/UI-Jetpack%20Compose%20Material3-blueviolet.svg)](https://developer.android.com/jetpack/compose)
[![Room Database](https://img.shields.io/badge/Database-Room%20SQLite%20(Offline)-orange.svg)](https://developer.android.com/training/data-storage/room)
[![Hilt](https://img.shields.io/badge/DI-Dagger%20Hilt-red.svg)](https://dagger.dev/hilt/)
[![Trilingual](https://img.shields.io/badge/Languages-Gujarati%20%7C%20Hindi%20%7C%20English-success.svg)](#-trilingual-support)

A modern, high-performance, 100% offline-first **Retail POS (Point of Sale), Khata Ledger (ખાતાવહી), and AI Voice ERP** application tailor-made for Indian Kirana (grocery) shopkeepers. Built entirely with **Jetpack Compose Material 3**, **Room SQLite**, and integrated with **Google Native Speech Recognition** & **ML Kit Barcode Scanning**.

---

## 🌟 Key Highlights & Modules

### 1. 🎙️ All-Round AI Voice Assistant (ગૂગલ વૉઇસ આસિસ્ટન્ટ)
- **Google Native Intent Integration**: Uses official `RecognizerIntent.ACTION_RECOGNIZE_SPEECH` to ensure zero timeout crashes, ultra-reliable voice recognition, and no premature *"અવાજ સંભળાયો નથી"* errors.
- **Draggable Floating Mic Button**: Always accessible across any screen without blocking UI elements.
- **Trilingual Speech-to-Text & TTS**: Real-time understanding in **Gujarati (`gu-IN`)**, **Hindi (`hi-IN`)**, and **Indian English (`en-IN`)**.
- **All-Round Intelligence**:
  - **Price Inquiry**: *"ચણા દાળ નો શું ભાવ છે?"* / *"Chana dal ka kya rate hai?"*
  - **Budget-to-Weight Calculator**: *"૩૫ રૂપિયાની ચણા દાળ કેટલી આવે?"* (Calculates exact grams based on live per-kg price).
  - **Weight-to-Price Inquiry**: *"૨૫૦ ગ્રામ જીરું ના કેટલા?"* / *"Aadha kilo ghee ka kitna?"*
  - **Direct Add to Cart**: *"૫૦૦ ગ્રામ ખાંડ કાર્ટમાં ઉમેરો"* (Adds line item directly into active bill).
  - **Conversational Greetings**: *"કેમ છો?"*, *"નમસ્તે"*, *"તમે કોણ છો?"*, *"આભાર"*.
  - **Live Date, Day & Time**: *"આજની તારીખ શું છે?"*, *"આજે કયો વાર છે?"*, *"કેટલા વાગ્યા?"*.
  - **Unit Conversions (કિરાણા એકમો)**:
    - `૧ મણ` = ૨૦ કિલોગ્રામ (20 kg)
    - `૧ ક્વિન્ટલ` = ૧૦૦ કિલોગ્રામ (100 kg)
    - `૧ ટન` = ૧,૦૦૦ કિલોગ્રામ (1,000 kg)
    - `૧ તોલો` = ૧૦ ગ્રામ (10g) (સોના-ચાંદી: ૧૧.૬૬ ગ્રામ)
    - `૧ કિલો` = ૧,૦૦૦ ગ્રામ | `૧ લીટર` = ૧,૦૦૦ મિલીલીટર | `૧ ડઝન` = ૧૨ નંગ
    - `અડધો કિલો` (500g), `પા કિલો` (250g), `પોણો કિલો` (750g)
  - **Retail Business & Shop Advice**:
    - Shop profit tips (margins, cash discounts, expense control).
    - Customer acquisition advice (service, punctuality, essential stock, delivery).
    - Udhar credit recovery tactics (WhatsApp reminders, credit limits).
    - Wholesale sourcing, FIFO stock rotation, and GST reverse calculations.
  - **Live Store Stats**: Queries live customer counts, total catalogued products, and total outstanding credit.
  - **Smart Unstocked Guidance**: For items not in inventory, offers polite voice explanation with **"➕ સ્ટોકમાં ઉમેરો"** and **"🔍 ગૂગલ સર્ચ"** buttons instead of cold refusal.
  - **Outside Knowledge Bridge**: Automatically opens Google Search for weather, gold/silver rates, fuel prices, match scores, and personalities.

---

### 2. ⚡ POS Billing & Fast Checkout (કાઉન્ટર બિલિંગ)
- **High-Speed Cart Entry**: Add items via Search, Category Chips, Voice commands, or Barcode Scanning.
- **Dynamic Unit Calculations**: Seamlessly handles Weight (`Kg/Gram`), Piece/Packet (`નંગ`), and Fixed items.
- **Integer Paisa Precision**: Zero floating-point drift (`100 Paisa = ₹1.00`). Eliminates rounding calculation bugs.
- **Integrated GST / Tax Calculation**: Optional GST toggle with item-level / bill-level CGST + SGST breakdown.
- **Multiple Payment Modes**: Cash (`રોકડ`), UPI (`ઓનલાઇન`), Split Payment, or Credit (`ઉધાર ખાતું`).
- **Dynamic UPI QR Generation**: Generates standard NPCI-compliant UPI QR codes offline (via embedded ZXing) with exact payable amounts for instant customer scanning.
- **Thermal Receipt Printing & WhatsApp Share**: Direct Bluetooth/ESC-POS thermal printer integration & WhatsApp digital receipt sharing.

---

### 3. 📖 Khata Ledger & Customer Management (ગ્રાહક ખાતાવહી)
- **Complete Customer Profiles**: Store Customer Name, Mobile Number, Address, and Credit Limit (`ક્રેડિટ લિમિટ`).
- **Safe Customer Details Edit**: Update details without losing transaction history or modifying existing ledger balances.
- **Udhar (Debit) & Jama (Credit) Entries**: Full audit trail of every credit sale and cash settlement.
- **1-Click WhatsApp Payment Reminders**: Send formatted Gujarati/Hindi/English payment request slips directly to customer WhatsApp.
- **Instant Search & Filter**: Filter customers by pending dues, credit limit breaches, or recent activity.

---

### 4. 📷 Real-Time Barcode & QR Scanner (બારકોડ સ્કેનર)
- **CameraX + Google ML Kit**: Multi-format barcode detection (`EAN-13`, `UPC-A`, `Code 128`, `QR Code`).
- **Instant Capture**: Automatic frame analyzer with haptic feedback vibration. Auto-populates scanned code into search or inventory forms with zero latency.
- **Flashlight & Camera Switching**: Integrated torch controls for low-light shop counters.

---

### 5. 📦 Stock & Inventory Management (માલ સ્ટોક)
- **Product Cataloging**: Gujarati name, Hindi name, English name, Barcode, Buying price, Selling price, Category, Calculation type, and Low Stock Alert threshold.
- **Low Stock Dashboard Alerts**: Visual warnings for fast-moving items running out of inventory.
- **Category Filter & Sorting**: Quickly organize spices, grains, oils, packaged goods, snacks, and dairy.

---

### 6. 🔒 100% Local Backup & Restore (બેકઅપ અને પુનઃપ્રાપ્તિ)
- **Zero Cloud / Zero Vendor Lock-in**: Full user privacy. Data never leaves the device unless exported by the user.
- **Android SAF (Storage Access Framework)**: Clean JSON export/import to internal storage, SD card, or Google Drive via system file picker.
- **Full Schema Validation**: Restores Products, Customers, Sales, Items, and Khata Ledger with transactional rollback protection against corrupted files.

---

## 🏗️ Architecture & Technology Stack

```
com.kirana.app
├── data
│   ├── backup         # SAF JSON Export/Import & Schema Validation
│   ├── dao            # Room DAOs (Product, Customer, Sale, Khata, Settings)
│   ├── db             # KiranaDatabase, Room TypeConverters & Migrations
│   ├── entity         # Room SQLite Entities (Normalized tables)
│   └── repository     # Clean Repository Pattern (Single source of truth)
├── ui
│   ├── assistant      # AI Voice Assistant: Parser, ViewModel, BottomSheet, Floating FAB
│   ├── dashboard      # Store Analytics, Daily Sales Summary, Performance Cards
│   ├── inventory      # Stock Management, Product Form, Low Stock Alerts
│   ├── khata          # Customer Khata, Ledger History, Add/Edit Customer Dialogs
│   ├── navigation     # Navigation Host, Bottom Navigation Bar, NavRoutes
│   ├── onboarding     # First-time Store Setup & Language Selection
│   ├── pos            # Point of Sale Screen, Cart, Payment Dialogs, Dynamic UPI QR
│   ├── settings       # App Settings, SAF Backup & Restore, Store Info, Language, GST
│   └── theme          # Material 3 Color Schemes, Typography, Shapes
└── util               # GoogleVoiceUtil, KiranaMoneyUtil, BarcodeScannerUtil, ZXingQrUtil
```

| Layer / Component | Technology / Library |
| :--- | :--- |
| **Language** | Kotlin 2.0+ (100% Coroutines & Flow) |
| **UI Framework** | Jetpack Compose Material 3 |
| **Architecture** | MVVM + Clean Architecture + Repository Pattern |
| **Dependency Injection** | Dagger Hilt 2.51+ |
| **Local Database** | Room SQLite 2.6+ with KSP |
| **Voice Engine** | Google Native Speech Intent (`RecognizerIntent.ACTION_RECOGNIZE_SPEECH`) + Android TTS |
| **Scanner Engine** | CameraX 1.4+ with Google ML Kit Barcode Scanning 17.3+ |
| **QR Code Engine** | Offline ZXing Core 3.5+ (NPCI UPI Specification) |
| **Storage & Backup** | Android Storage Access Framework (SAF) + Kotlinx Serialization / Gson |

---

## 🧮 Financial & Monetary Engine (`KiranaMoneyUtil`)

To ensure absolute financial accuracy and prevent IEEE 754 floating-point inaccuracies, all monetary values throughout the database and business logic are stored as **64-bit Long Integers in Paisa**:

$$\text{Paisa} = \text{Rupees} \times 100$$

- ₹10.50 is stored strictly as `1050L`.
- ₹1,000.00 is stored strictly as `100000L`.

### Weight-Based Price Formula:
$$\text{Line Total (Paisa)} = \frac{\text{Weight in Grams} \times \text{Rate Per Kg (Paisa)}}{1000}$$

### Budget-to-Weight Formula:
$$\text{Calculated Weight (Grams)} = \frac{\text{Budget (Paisa)} \times 1000}{\text{Rate Per Kg (Paisa)}}$$

---

## 🚀 Setup, Build & Run

### Prerequisites:
- Android Studio Ladybug / Meerkat or newer
- JDK 17 / JDK 21
- Android SDK 35 (Compile SDK 37, Min SDK 26)

### Build Commands (Windows / Linux / macOS):

```bash
# 1. Run Unit Tests (Validates all Intent Parsing, Unit Conversions, Math & Advice)
./gradlew testDebugUnitTest

# 2. Assemble Debug APK
./gradlew assembleDebug

# 3. Assemble Release APK
./gradlew assembleRelease
```

---

## 🌐 Trilingual Support (ત્રિભાષી સપોર્ટ)

| Domain | ગુજરાતી (Gujarati) | हिन्दी (Hindi) | English |
| :--- | :--- | :--- | :--- |
| **Navigation** | કાઉન્ટર / ખાતાવહી / સ્ટોક | काउंटर / खाताबही / स्टॉक | Counter / Khata / Stock |
| **Transactions** | ઉધાર / જમા / રોકડ | उधार / जमा / नकद | Credit / Debit / Cash |
| **Weight Units** | કિલો / ગ્રામ / મણ / ક્વિન્ટલ | किलो / ग्राम / मन / क्विंटल | Kg / Gram / Man / Quintal |
| **Voice AI** | અવાજ ઓળખ અને બોલવું | आवाज़ पहचान और बोलना | Speech Recognition & TTS |

---

## 📄 License & Privacy
- **100% Offline & Private**: No analytics trackers, no hidden network telemetry.
- **Local Storage**: All records reside securely inside the app's sandboxed Room SQLite database on the shopkeeper's device.
