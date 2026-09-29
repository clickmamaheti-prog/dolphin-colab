# 🐬 Dolphin Uncensored di Google Colab (Gratis)

Notebook siap pakai untuk menjalankan model **dolphin-mistral** (uncensored) di Google Colab dengan GPU gratis, lalu mengeksposnya sebagai **API publik** via Cloudflare Tunnel.

## Cara pakai (3 langkah)

1. **Klik untuk buka di Colab:**

   [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/clickmamaheti-prog/dolphin-colab/blob/main/dolphin_colab.ipynb)

2. Pilih **Runtime → Change runtime type → T4 GPU → Save**

3. **Runtime → Run all** — di cell 4 akan muncul URL API publik kamu 🎉

## Pakai API dari luar Colab

```python
from openai import OpenAI

client = OpenAI(base_url="URL_TUNNEL/v1", api_key="ollama")
r = client.chat.completions.create(
    model="dolphin-mistral",
    messages=[{"role": "user", "content": "halo"}],
)
print(r.choices[0].message.content)
```

Kompatibel dengan semua library/tool yang support OpenAI API.

## Catatan

| | |
|---|---|
| ⏱️ Durasi | Sesi gratis Colab max ~12 jam; jalankan ulang semua cell jika sesi mati (URL berubah) |
| 🔒 Keamanan | Endpoint publik tanpa auth — jangan sebarkan URL tunnel |
| 🔄 Model lain | Ubah dropdown di cell 3 (`dolphin3`, `llama3.1:8b`, dll) |
| 💰 Biaya | Rp 0 — GPU T4 gratis dari Colab |
