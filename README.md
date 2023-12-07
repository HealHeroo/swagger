# swagger
https://healheroo.github.io/swagger/

# Swagger Documentation for HealHero API

Repositori ini berisi dokumentasi Swagger untuk HealHero API. HealHero adalah proyek yang didedikasikan untuk memberikan informasi kesehatan sederhana kepada pengguna.

## Table of Contents

- [Introduction](#introduction)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
- [Swagger Documentation](#swagger-documentation)
  - [Swagger Function](#swagger-function)
  - [OpenAPI Specification](#openapi-specification)
  - [Generating Swagger Documentation](#generating-swagger-documentation)
  - [Viewing Swagger Documentation](#viewing-swagger-documentation)

## Introduction

HealHero is [provide a brief introduction to the project, its goals, and its significance].

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
Konfigurasi untuk menggunakan Swagger UI, sebuah alat pengembangan web yang memungkinkan untuk menampilkan dan mengonsumsi dokumentasi OpenAPI (sebelumnya dikenal sebagai Swagger). 

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
