# GID AK RESÈS POU PWODWI APK ANDROID POU MIKENSON TOP UP FF

Dokiman sa a gen tout konfigirasyon, kòd, ak etap kle pou transfòme aplikasyon **MIKENSON TOP UP FF** la an yon fichye **APK Android** pare pou enstale sou nenpòt telefòn Android.

---

## 1. Fichye `manifest.json` (Pou PWA ak Konvètisè APK)
Mete fichye sa a nan rasin pwojè w la (akote `index.html`):

```json
{
  "name": "MIKENSON TOP UP FF",
  "short_name": "MikensonTopUp",
  "description": "Achte Dyaman Free Fire, Kat Merù, Netflix ak Peman MonCash/NatCash an Ayiti",
  "start_url": "/",
  "display": "standalone",
  "background_color": "#10131a",
  "theme_color": "#00e5ff",
  "orientation": "portrait",
  "icons": [
    {
      "src": "/icons/icon-192.png",
      "sizes": "192x192",
      "type": "image/png"
    },
    {
      "src": "/icons/icon-512.png",
      "sizes": "512x512",
      "type": "image/png"
    }
  ]
}
```

---

## 2. Metòd 1 : PWABuilder (San Pwogramasyon — Pi Rapid)
1. **Mete sit la sou Vercel / Netlify / GitHub Pages**.
2. Ale sou [pwabuilder.com](https://www.pwabuilder.com/).
3. Antre URL sit la epi klike sou **Start**.
4. Klike sou **Package for Stores** > **Android**.
5. Klike sou **Generate Package** pou telechaje dosye APK / AAB pare a.

---

## 3. Metòd 2 : Capacitor (APK Natif via Android Studio)

### Etap nan Tèminal:
```bash
# 1. Inisyalize pwojè a
npm init -y

# 2. Enstale Capacitor
npm install @capacitor/core @capacitor/cli @capacitor/android

# 3. Konfigire Capacitor
npx cap init "MIKENSON TOP UP FF" "com.mikensontopup.app" --web-dir dist

# 4. Ajoute sipò Android
npx cap add android

# 5. Kopye fichye web yo epi ouvri Android Studio
npx cap copy
npx cap open android
```

### Konfigirasyon Pèmisyon (`AndroidManifest.xml`):
Asire w liy sa yo prezan pou pèmèt entènèt ak telechajman resi:
```xml
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE" />
<uses-permission android:name="android.permission.READ_MEDIA_IMAGES" />
```

### Jenerasyon APK nan Android Studio:
1. Ale nan meni **Build** > **Build Bundle(s) / APK(s)** > **Build APK(s)**.
2. Lè konpilasyon an fini, klike sou **locate**.
3. Fichye `app-debug.apk` ou a pare pou voye sou telefòn ou via WhatsApp, Telegram, oswa kab USB!
