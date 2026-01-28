---
layout: post
title: "Prompt Engineering"
categories: AI
---

Prompt engineering adalah suatu disiplin ilmu dalam merancang sebuah prompt untuk membimbing model Generative AI menghasilkan respons yang sesuai dengan keinginan.

Prompt engineering pada dasarnya merupakan cara menyusun pertanyaan yang lebih baik untuk diajukan kepada model Generative AI. Lebih dari itu, prompt engineering sebenarnya mempelajari cara membentuk pemikiran dan menyusunnya menjadi sebuah pertanyaan terstruktur sehingga dapat mengurangi risiko hasil keluaran yang salah.

## Contents
* [Best Practice](#best-practice)
* [Pola-pola dalam Prompt Engineering](#pola-pola-dalam-prompt-engineering)
  * [Pola Dasar](#pola-dasar)
    * [Pola Persona](#pola-persona)
    * [Persona Audiens](#persona-audiens)
    * [Few-shots](#few-shots)
    * [Chain of Thought](#chain-of-thought)
    * [Pola ReAct](#pola-react)
  * [Adaptive Prompting](#adaptive-prompting)
    * [Question Refinement](#question-refinement)
    * [Alternative Approaches](#alternative-approaches)
    * [Cognitive Verifier](#cognitive-verifier)
    * [Flipped Interaction](#flipped-interaction)
  * [Pola Konsistensi Hasil](#pola-konsistensi-hasil)
    * [Tail Generation](#tail-generation)
    * [Pola Template](#pola-template)
  * [Iterative Prompt Development](#iterative-prompt-development)

## Best Practice

Cara terbaik untuk membuat prompt yang jelas adalah dengan membuatnya menggunakan sebuah struktur informasi yang terdiri dari empat elemen utama yaitu: Peran, Objektif, Konteks, Batasan.

**Contoh Prompt:**

```plaintext
Peran: Bertindaklah sebagai **mentor karier untuk software developers.**
Objektif: **Susunlah panduan mengenai apa saja yang perlu ditulis pada bagian "About" di profil LinkedIn.**
Konteks: **Panduan ini ditujukan khusus untuk fresh graduate yang baru lulus kuliah.**
Batasan: Pastikan panduan tersebut memiliki **batasan maksimal empat paragraf.**
```

## Pola-pola dalam Prompt Engineering

### 1. Pola Dasar

#### 1.1 Pola Persona

**Contoh Prompt:**

```plaintext
Kamu adalah seorang software developer senior. Berikan tips untuk menjaga kesehatan tubuh manusia
```

#### 1.2 Persona Audiens

**Contoh Prompt:**

```plaintext
Jelaskan apa itu algoritma kepada anak berusia 5 tahun
```

#### 1.3 Few-shots

Pola ini berguna untuk tugas yang membutuhkan hasil dengan format tertentu, seperti ekstraksi informasi atau pembuatan konten dengan struktur khusus.

Pola few-shot dibuat dengan menambahkan dua hal, yaitu label deskriptif (Pada contoh: Bahasa Pemrograman) dan beberapa contoh (shots).

**Contoh Prompt:**



