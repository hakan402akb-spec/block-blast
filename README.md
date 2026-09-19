# Block Blast — Android (APK)

Oyunun tamamı `app/src/main/assets/index.html` içinde. Uygulama bunu tam ekran bir
WebView'de açar, internet gerektirmez.

## Yol 1 — Bilgisayarsız, GitHub ile (önerilen, ~5 dk)

1. github.com'da yeni (boş, public veya private) bir repo aç.
2. Bu klasördeki **tüm dosyaları** o repoya yükle (Add file → Upload files → sürükle-bırak → Commit).
3. Repodaki **Actions** sekmesine gir, iş akışını çalıştırmaya izin ver (Enable workflows).
   Yükleme ile birlikte "Build APK" otomatik başlar; başlamazsa Actions → Build APK → Run workflow.
4. 3-5 dakika sonra çalışan işin en altındaki **Artifacts → BlockBlast-APK** bağlantısından zip'i indir.
5. Zip'ten çıkan `app-release.apk` dosyasını telefona at ve kur.
   (Telefonda "Bilinmeyen kaynaklardan yükleme" izni gerekir.)

## Yol 2 — Android Studio ile

1. Android Studio → Open → bu klasörü seç, Gradle senkronizasyonunu bekle.
2. Build → Build Bundle(s)/APK(s) → Build APK(s).
3. APK: `app/build/outputs/apk/release/app-release.apk`

## Yol 3 — Terminal (Android SDK kuruluysa)

```bash
./gradlew assembleRelease
# APK: app/build/outputs/apk/release/app-release.apk
```

## Notlar

- APK, Android'in debug anahtarıyla imzalanır; kendin kurup oynamak için yeterlidir.
  Google Play'e yüklemek istersen kendi keystore'unla imzalaman gerekir.
- Oyunu güncellemek için sadece `app/src/main/assets/index.html` dosyasını değiştirip
  yeniden derlemen yeterli.
- Paket adı: `com.blockblast.game` · Min Android 5.0 (API 21)
