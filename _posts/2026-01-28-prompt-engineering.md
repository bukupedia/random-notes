---
layout: post
title: "Prompt Engineering"
categories: AI
---

Prompt engineering adalah suatu disiplin ilmu dalam merancang sebuah prompt untuk membimbing model Generative AI menghasilkan respons yang sesuai dengan keinginan.

Prompt engineering pada dasarnya merupakan cara menyusun pertanyaan yang lebih baik untuk diajukan kepada model Generative AI. Lebih dari itu, prompt engineering sebenarnya mempelajari cara membentuk pemikiran dan menyusunnya menjadi sebuah pertanyaan terstruktur sehingga dapat mengurangi risiko hasil keluaran yang salah.

## Daftar Isi
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

```markdown
Peran: Bertindaklah sebagai **mentor karier untuk software developers.**
Objektif: **Susunlah panduan mengenai apa saja yang perlu ditulis pada bagian "About" di profil LinkedIn.**
Konteks: **Panduan ini ditujukan khusus untuk fresh graduate yang baru lulus kuliah.**
Batasan: Pastikan panduan tersebut memiliki **batasan maksimal empat paragraf.**
```

## Pola-pola dalam Prompt Engineering

### 1. Pola Dasar <a id="pola-dasar"></a>

#### 1.1 Pola Persona <a id="pola-persona"></a>

**Contoh Prompt:**

```plaintext
Kamu adalah seorang software developer senior. Berikan tips untuk menjaga kesehatan tubuh manusia
```

#### 1.2 Persona Audiens <a id="persona-audiens"></a>

**Contoh Prompt:**

```plaintext
Jelaskan apa itu algoritma kepada anak berusia 5 tahun
```

#### 1.3 Few-shots <a id="few-shots"></a>

Pola ini berguna untuk tugas yang membutuhkan hasil dengan format tertentu, seperti ekstraksi informasi atau pembuatan konten dengan struktur khusus.

Pola few-shot dibuat dengan menambahkan dua hal, yaitu label deskriptif (Pada contoh: Bahasa Pemrograman) dan beberapa contoh (shots).

**Contoh Prompt:**

[![Contoh prompt dengan menggunakan pola few-shots](https://raw.githubusercontent.com/bukupedia/random-notes/refs/heads/main/media/2026-01-28-few-shots.jpeg)](https://raw.githubusercontent.com/bukupedia/random-notes/refs/heads/main/media/2026-01-28-few-shots.jpeg)

#### 1.4 Chain-of-Thought <a id="chain-of-thought"></a>

Pola ini membimbing model menghasilkan respons melalui contoh. Mirip dengan pola few-shots, Perbedaannya, few-shot hanya menyediakan contoh, sedangkan chain-of-thought lebih detail. Jadi, selain memberikan contoh, pada pola chain-of-thought, kita juga menambahkan langkah-langkah untuk memandu model menyelesaikan tugas.

**Contoh Prompt:**

[![Contoh prompt dengan pola chain-of-thought](https://raw.githubusercontent.com/bukupedia/random-notes/refs/heads/main/media/2026-01-28-chain-of-thought.jpeg)](https://raw.githubusercontent.com/bukupedia/random-notes/refs/heads/main/media/2026-01-28-chain-of-thought.jpeg)

Pola chain-of-thought dibuat dengan memberikan contoh beserta dengan tahapan-tahapan pengerjaan untuk menghasilkan hasil akhir. Dengan begitu, model dapat meniru proses yang dicontohkan untuk menghasilkan jawaban yang lebih akurat.

#### 1.5 Pola ReAct <a id="pola-react"></a>

Pola ReAct adalah pengembangan lanjutan dari pola chain-of-thought. Selain membimbing model menghasilkan respons melalui contoh dan proses bertahap, kita juga membimbing model untuk mengambil tindakan (action) mengakses tools eksternal jika membutuhkan informasi yang tidak dimiliki oleh model.

Alih-alih hanya memberikan jawaban akhir menggunakan asumsi, pola ReAct meminta model Generative AI mengakses tools eksternal untuk mendapatkan informasi yang dibutuhkan sebelum menghasilkan respons (misalnya, mencari dan mengambil data dari situs web, menonton video, atau mengambil data dari API). Dengan ini, model mampu memberikan respons yang lebih akurat.

**Contoh Prompt:**

[![Contoh prompt dengan pola ReAct](https://raw.githubusercontent.com/bukupedia/random-notes/refs/heads/main/media/2026-01-28-react.jpeg)](https://raw.githubusercontent.com/bukupedia/random-notes/refs/heads/main/media/2026-01-28-react.jpeg)

### 2. Adaptive Prompting <a id="adaptive-prompting"></a>

adalah berbagai cara yang bisa kita gunakan untuk menyempurnakan prompt sehingga respons model menjadi lebih tepat sasaran.

#### 2.1 Question Refinement <a id="question-refinement"></a>

Pola question refinement memanfaatkan pengetahuan model Generative AI dengan meminta model memperbaiki atau menyempurnakan pertanyaan kita terlebih dahulu jika diperlukan. Pola ini memungkinkan model membantu kita menemukan pertanyaan yang lebih tepat untuk mendapatkan jawaban yang lebih relevan. 

Selain itu, pola question refinement juga memberi kesempatan untuk merefleksikan proses berpikir kita sendiri dan mengidentifikasi informasi penting yang mungkin terlewat.

**Contoh Prompt:**

```plaintext
Pada setiap pertanyaan yang saya ajukan, tolong sarankan versi pertanyaan yang lebih baik untuk digunakan. Kemudian, di akhir, tanyakan kepada saya versi mana yang ingin saya gunakan.
```

#### 2.2 Alternative Approaches <a id="alternative-approaches"></a>

Dengan pola ini, kita dapat meminta model Generative AI untuk menawarkan beragam opsi pertanyaan alternatif. Beragam pertanyaan ini membantu kita merefleksikan apa yang sebenarnya ingin kita capai dan memungkinkan untuk memilih pertanyaan yang paling relevan dengan kebutuhan.

**Contoh Prompt:**

```plaintext
Setiap kali saya mengajukan pertanyaan, berikan daftar alternatif pertanyaan yang dapat mencapai tujuan yang sama, tetapi dengan formulasi yang lebih baik. Sertakan juga perbandingan kelebihan dan kekurangan antara pertanyaan saya dan daftar alternatif yang Anda berikan
```

#### 2.3 Cognitive Verifier <a id="cognitive-verifier"></a>

Pola ini melibatkan proses meminta model Generative AI untuk memecah pertanyaan utama menjadi bagian-bagian yang lebih kecil melalui serangkaian pertanyaan tambahan.

Dengan pola cognitive verifier, model Generative AI memiliki kesempatan untuk mengumpulkan lebih banyak konteks dari pertanyaan sebelum menghasilkan jawaban akhir yang akurat dan relevan.

**Contoh Prompt:**

```plaintext
Setiap kali saya mengajukan pertanyaan, mohon ajukan beberapa pertanyaan tambahan yang dapat membantu Anda memahami dengan lebih jelas apa yang saya maksud. Pastikan semua informasi yang nanti saya berikan digunakan sebelum memberikan jawaban akhir.
```

#### 2.4 Flipped Interaction <a id="flipped-interaction"></a>

Pola flipped interaction adalah pola alur interaksi dengan model Generative AI dibalik. Alih-alih meminta model memecah pertanyaan seperti dalam Cognitive Verifier, kita menjelaskan objektif tugas terlebih dahulu, lalu meminta model mengajukan pertanyaan untuk memahami masalah dengan lebih baik.

Pola ini dibuat dengan cara:

1. Menentukan objektif tugas (contoh: "Buat kode testing untuk halaman Tambah Buku").
2. Meminta model untuk menanyakan serangkaian pertanyaan terkait objektif tugas (contoh: "Ajukan saya pertanyaan terkait skrip testing yang saya inginkan").
3. Menentukan batasan dari pertanyaan yang perlu diajukan model (contoh: Tanyakan sampai Anda dapat membuat kode testing untuk berbagai skenario yang saya inginkan). Ini krusial untuk menghindari model terus bertanya tanpa henti.

**Contoh Prompt:**

[![Contoh prompt menggunakan pola flipped interaction](https://raw.githubusercontent.com/bukupedia/random-notes/refs/heads/main/media/2026-01-28-flipped-interaction-prompt.jpeg)](https://raw.githubusercontent.com/bukupedia/random-notes/refs/heads/main/media/2026-01-28-flipped-interaction-prompt.jpeg)

[![Contoh interaksi yang dihasilkan menggunakan pola flipped interaction pada salah satu model Generative AI](https://raw.githubusercontent.com/bukupedia/random-notes/refs/heads/main/media/2026-01-28-flipped-interaction-result.jpeg)](https://raw.githubusercontent.com/bukupedia/random-notes/refs/heads/main/media/2026-01-28-flipped-interaction-result.jpeg)

### 3. Pola Konsistensi Hasil <a id="pola-konsistensi-hasil"></a>

Mengenal berbagai pola yang digunakan untuk memastikan konsistensi dari respons yang dihasilkan oleh model Generative AI.

#### 3.1 Tail Generation <a id="tail-generation"></a>

Pola tail generation dibuat dengan langkah berikut.

1. Memberikan peraturan yang harus dipatuhi model selama menghasilkan respons.
2. Meminta model untuk selalu mengakhiri responsnya dengan mengulang aturan yang telah kita tetapkan.

**Contoh Prompt:**

```plaintext
Setiap kali saya bertanya tentang JavaScript, pastikan pada akhir jawaban kamu selalu menegaskan bahwa bahasa pemrograman JavaScript berbeda dengan bahasa pemrograman Java. Di akhir setiap respons, Sebutkan ulang aturan yang saya berikan.

Pertanyaan: Apa perbedaan let dan const di JavaScript?
```

#### 3.2 Pola Template <a id="pola-template"></a>

Pola template dibuat dengan cara:

1. Menggunakan delimiter dengan label yang dapat membantu model memahami keinginan kita.
2. Menggunakan pola tail generation untuk memastikan konsistensi respons model.

**Note:**
Delimiter adalah tanda yang kita gunakan untuk membedakan atau menandai bagian tertentu di dalam prompt.

Delimiter dapat berupa tanda apa saja, misalnya tanda kurung sudut (<...>), kurung siku ([...]), tanda petik dua ("..."), atau tanda khusus lainnya.

Tujuannya adalah agar model Generative AI dapat mengidentifikasi bagian di dalam delimiter, lalu memproses informasi/perintah tersebut secara terpisah. Alhasil, bagian itu tidak dianggap sebagai teks biasa, melainkan instruksi tambahan yang perlu diikuti sebagai bagian dari instruksi utama.

**Contoh Prompt:**

```plaintext
Berikan saya data pengguna dummy hanya dalam format JSON yang saya minta. Tidak perlu memberikan bentuk format lain selain yang saya minta. Berikut ini adalah bentuk formatnya:

[
{
"id": value,
"nama": value,
"pertanyaan": <Jika id ganjil, tanyakan tentang pemrograman web; jika id genap, tanyakan tentang pemrograman mobile>
}
]

Di akhir setiap respons, sebutkan ulang aturan yang saya berikan.
```

### 4. Iterative Prompt Development <a id="iterative-prompt-development"></a>

Iterative Prompt Development, yaitu mindset yang harus dimiliki oleh seorang prompt engineer dalam merancang prompt yang ia buat. di mana pada dasarnya sebuah prompt tidak harus selalu bersifat final dalam satu kali percobaan, melainkan senantiasa dapat disempurnakan secara iteratif melalui observasi respons dari model Generative AI.

Penyempurnaan prompt bisa berupa revisi pada prompt awal atau memberikan feedback kepada model Generative AI pada interaksi berikutnya. Pada feedback, kita jelaskan kepada model mengenai apa saja yang perlu diperbaiki dari respons yang ia hasilkan.
