# HyperFlow ⚡

> **Multi-Connection Download Manager for Android**

HyperFlow is a Android download manager that bonds multiple physical network connections (**Wi-Fi, Cellular, and Ethernet**) simultaneously to achieve unprecedented download throughput.

[![Latest Release](https://img.shields.io/github/v/release/atharva01c/HyperFlow-App?style=for-the-badge&color=007AFF&label=Download%20APK)](https://github.com/atharva01c/HyperFlow-App/releases/latest)
[![Android](https://img.shields.io/badge/Platform-Android%2010%2B%20(API%2029%E2%80%9336)-3DDC84?style=for-the-badge&logo=android&logoColor=white)](https://github.com/atharva01c/HyperFlow-App/releases)
[![License](https://img.shields.io/badge/Status-Active-brightgreen?style=for-the-badge)](https://github.com/atharva01c/HyperFlow-App)

---

## 📱 Screenshots

<p align="center">
  <img src="assets/screenshots/home.png" width="30%" alt="HyperFlow Home Screen" />
  &nbsp;&nbsp;&nbsp;&nbsp;
  <img src="assets/screenshots/detail.png" width="30%" alt="Block Matrix & Detail" />
  &nbsp;&nbsp;&nbsp;&nbsp;
  <img src="assets/screenshots/empty_state.png" width="30%" alt="Clean Empty State" />
</p>

---

## ✨ Key Features

* **⚡ Multi-Network Aggregation**
  * Simultaneously bonds active physical interfaces.
  * Bypasses traditional single-connection OS bottlenecks by routing independent TCP/HTTP streams directly through dedicated socket bindings (`Network.bindSocket`).

* **🧩 Dynamic Block Matrix & Work-Stealing**
  * Automatically splits target files into 4 MiB block ranges.
  * Faster radios continuously steal pending work from slower ones, ensuring 100% capacity utilization across all available links.

* **🔄 Zero-Loss Live Network Handover**
  * Seamlessly adapts when you walk out of Wi-Fi range or toggle networks on/off.
  * Active streams instantly shift to surviving links without stalling, failing, or re-downloading existing progress.

* **🛡️ Resilient & Private**
  * Resume capabilities utilizing HTTP 206 partial range requests.
  * Automatic clipboard link detection.
  * Files are safely published directly into your public `Downloads/HyperFlow/` folder upon completion.

---

## ⚙️ Requirements

* **Android OS:** Android 10 (API Level 29) or newer.
* **Architecture:** Compatible with `arm64-v8a`, `armeabi-v7a`, `x86_64`.
* **Hardware:** Any Android device with active Wi-Fi and/or Cellular connectivity.

---

## 🛠️ Architecture Overview

HyperFlow is engineered with an isolated two-module architecture:
* **`:engine`** — A pure Kotlin concurrent download scheduler with zero Android dependencies:
  * Concurrency Controller with hedge racing and work-stealing.
  * Windowed Speed Meter and Stream Governors.
* **`:app`** — Modern Android application shell:
  * Jetpack Compose & Material 3 UI design system.
  * Low-level socket network binding with Android ConnectivityManager.
  * Background Foreground Service (`dataSync` type) with media store publication.

---

## 💬 Feedback & Bug Reports

Found an issue or have a feature suggestion? 
Feel free to open an issue on the **[HyperFlow-App Issue Tracker](https://github.com/atharva01c/HyperFlow-App/issues)**!

---

## 🙏 Acknowledgments

HyperFlow was inspired by the concept of **[Plexo](https://github.com/anmolkapil/plexo)** by [@anmolkapil](https://github.com/anmolkapil). I deeply appreciate their work in exploring multiplexed network downloading.
