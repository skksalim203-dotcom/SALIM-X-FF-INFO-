# ⚡ KAWSARxFFINFO — Free Fire Player Info Website

একটি সুন্দর, দ্রুত এবং সম্পূর্ণ Free Fire প্লেয়ার তথ্য ওয়েবসাইট।

---

## 📁 ফাইল স্ট্রাকচার

```
kawsarxffinfo/
├── server.py              ← মেইন Flask সার্ভার (Python)
├── requirements.txt       ← Python dependencies
├── proto/                 ← Protobuf ফাইল (পরিবর্তন করবেন না)
│   ├── FreeFire_pb2.py
│   ├── main_pb2.py
│   └── AccountPersonalShow_pb2.py
├── templates/
│   └── index.html         ← মেইন ওয়েবপেজ (HTML)
└── static/
    ├── css/style.css      ← ডিজাইন
    └── js/script.js       ← JavaScript লজিক
```

---

## ⚙️ সেটআপ / How to Run

### ১. Python ইনস্টল করুন (3.8+)

### ২. Dependencies ইনস্টল করুন:
```bash
pip install -r requirements.txt
```

### ৩. Environment Variables সেট করুন:

`server.py` চালানোর আগে আপনার Free Fire অ্যাকাউন্টের credentials
`FF_CREDS_ME`, `FF_CREDS_BD`, `FF_CREDS_IND` environment variable-এ দিন:

**Windows:**
```cmd
set FF_CREDS_ME=uid=YOUR_UID&password=YOUR_PASSWORD
set FF_CREDS_BD=uid=YOUR_UID&password=YOUR_PASSWORD
set FF_CREDS_IND=uid=YOUR_UID&password=YOUR_PASSWORD
```

**Linux/Mac:**
```bash
export FF_CREDS_ME="uid=YOUR_UID&password=YOUR_PASSWORD"
export FF_CREDS_BD="uid=YOUR_UID&password=YOUR_PASSWORD"
```

### ৪. সার্ভার চালু করুন:
```bash
python server.py
```

### ৫. ব্রাউজারে খুলুন:
```
http://localhost:5000
```

---

## 🌐 API Endpoints

| Endpoint | বিবরণ |
|----------|-------|
| `GET /` | মেইন ওয়েবসাইট |
| `GET /get?uid=UID` | প্লেয়ার ইনফো |
| `GET /get?uid=UID&region=BD` | নির্দিষ্ট রিজিয়ন |
| `GET /status` | টোকেন স্ট্যাটাস |

---

## 🖼️ কিভাবে PNG দেখায়

- `EquippedOutfit` (পোশাকের ID লিস্ট) → প্রতিটি ID দিয়ে ছবি দেখায়
- `EquippedWeapon` (অস্ত্রের ID লিস্ট) → প্রতিটি ID দিয়ে ছবি দেখায়
- `EquippedSkills` (স্কিলের ID লিস্ট) → প্রতিটি ID দিয়ে ছবি দেখায়
- ছবি সোর্স: `https://cdn.jsdelivr.net/gh/ShahGCreator/icon@main/PNG/{ID}.png`

---

## 🚀 Production (Gunicorn)

```bash
gunicorn -w 2 -b 0.0.0.0:5000 server:app
```

---

## ⚠️ গুরুত্বপূর্ণ নোট

- এই টুল শুধু **পাবলিক** প্লেয়ার তথ্য দেখায়
- API কাজ করতে হলে **credentials** লাগবে
- Made by **KAWSARxFF** ⚡
