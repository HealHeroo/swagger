# Swagger Documentation for HealHero API

Repositori ini berisi dokumentasi Swagger untuk HealHero API. HealHero adalah proyek yang didedikasikan untuk memberikan informasi tentang apa saja yang ada pada aplikasi.

## Table of Contents

- [Introduction](#introduction)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
- [Swagger Documentation](#swagger-documentation)
  - [Swagger Function](#swagger-function)
  - [OpenAPI Specification](#openapi-specification)
  - [Viewing Swagger Documentation](#viewing-swagger-documentation)

## Introduction

HealHero adalah proyek aplikasi kesehatan sederhana yang bertujuan memberikan informasi dan layanan berkaitan dengan kesehatan kepada pengguna. Aplikasi ini dirancang untuk memberikan kemudahan akses kepada pengguna terkait dengan informasi obat, pelayanan pengguna oleh admin, serta layanan pengiriman obat oleh driver. Aplikasi ini mencakup tiga peran utama: admin, pengguna/pelanggan, dan driver.

## Getting Started

Follow these steps to set up the HealHero Swagger documentation on your local machine.

### Prerequisites

Before you begin, ensure you have the following installed:

- Node.js
- npm (Node Package Manager)
```bash
# Example
npm install
```
### Installation
Clone this repository and install the dependencies.
```bash
# Example
git clone https://github.com/HealHeroo/swagger.git
cd swagger
npm install
```

## Swagger Documentation

### Swagger Function
The swagger_function.js file in this repository serves the following purpose: 

1. **`import SwaggerUIBundle from "https://cdn.skypack.dev/swagger-ui-dist/swagger-ui-bundle.js";`**
   - Mengimpor modul `SwaggerUIBundle` dari paket Skypack. Ini adalah bundel Swagger UI yang mencakup semua komponen yang diperlukan untuk menampilkan dokumentasi OpenAPI.

2. **`import SwaggerUIStandalonePreset from "https://cdn.skypack.dev/swagger-ui-dist/swagger-ui-standalone-preset.js";`**
   - Mengimpor modul `SwaggerUIStandalonePreset` dari paket Skypack. Ini adalah paket preset Swagger UI yang mencakup gaya dan konfigurasi standar.

3. **`export let URLData = "./openapi.yaml";`**
   - Mengekspor variabel `URLData` yang berisi lokasi file OpenAPI Specification (dalam format YAML) di dalam repositori atau server.

4. **`export const UIData = SwaggerUIBundle({ ... });`**
   - Mengekspor konstanta `UIData`, yang dibuat dengan memanggil fungsi `SwaggerUIBundle` dengan konfigurasi tertentu.
     - `url: URLData`: Menentukan lokasi OpenAPI spec yang akan digunakan oleh Swagger UI.
     - `dom_id: "#swagger-ui"`: Menentukan ID elemen HTML tempat Swagger UI akan ditampilkan.
     - `deepLinking: true`: Mengaktifkan atau menonaktifkan deep linking untuk mengizinkan tautan langsung ke bagian-bagian spesifik dari dokumentasi.
     - `presets: [SwaggerUIBundle.presets.apis, SwaggerUIStandalonePreset]`: Menggunakan preset yang disediakan oleh Swagger UI.
     - `plugins: [SwaggerUIBundle.plugins.DownloadUrl]`: Menambahkan plugin untuk mendukung unduhan spesifikasi OpenAPI.

5. **`export function setSwagger() { return UIData; }`**
   - Mengekspor fungsi `setSwagger` yang mengembalikan data konfigurasi Swagger UI. 

### OpenAPI Specification
The openapi.yaml file contains the OpenAPI Specification for the HealHero API

1. Info
- **title:** Menyebutkan judul dokumentasi API.
- **description:** Memberikan deskripsi umum tentang API HealHero.
- **termsOfService:** Menyertakan URL ke halaman ketentuan layanan di GitHub.
- **contact:** Menyertakan URL untuk menghubungi melalui formulir biodata di situs HealHero.
- **license:** Menyertakan nama dan URL lisensi.
- **version:** Menyebutkan versi API.

2. ExternalDocs
- **description:** Memberikan deskripsi tentang repositori GCF di GitHub.
- **url:** Menyertakan URL ke repositori GCF di GitHub.

3. Servers
- Mendefinisikan server dengan URL dari cloud functions di Google Cloud Platform (GCP).

4. Tags
- Menyertakan beberapa tag yang mewakili fungsionalitas berbeda dari API, seperti Auth, SignUp, User, Pengguna, Driver, Obat, dan Order.

5. Paths
- Mendefinisikan operasi CRUD untuk setiap jalur API, seperti `/login`, `/signup_pengguna`, `/signup_driver`, `/user`, `/pengguna`, `/driver`, `/obat_healhero`, dan `/order_healhero`.

6. Components
- **schemas:** Mendefinisikan objek skema untuk entitas seperti Login, AuthResponse, User, Pengguna, Driver, Obat, dan Order.
- **requestBodies:** Mendefinisikan body permintaan untuk beberapa operasi, seperti AuthReq dan UserArray.
- **securitySchemes:** Mendefinisikan skema keamanan menggunakan API key di header Authorization.
- **examples:** Menyertakan contoh untuk pembaruan profil Pengguna dan Driver.

### Viewing Swagger Documentation
Once the Swagger documentation is generated, you can view it by opening the following URL in your browser:
Open the following URL in your browser: https://healheroo.github.io/swagger/
