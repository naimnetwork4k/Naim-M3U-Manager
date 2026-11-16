# Naim M3U Playlist & Channel Manager — GitHub APK files

এই ফোল্ডারটি আপনার GitHub screenshot-এর মতো সাজানো হয়েছে:

- `.github/workflows/Naim-LiveTVHD.yml` — GitHub Actions দিয়ে APK build
- `www/index.html` — আপনার দেওয়া Naim LiveTVHD ওয়েব অ্যাপ
- `www/icon.png` — অ্যাপের লোগো
- `www/1000273307 (1).png` — লোগোর মূল ছবি
- `package.json` এবং `capacitor.config.json` — Capacitor Android app configuration
- `assets/icon.png` — Android launcher icon তৈরির উৎস

## GitHub-এ কীভাবে বসাবেন

1. ZIP Extract করুন।
2. আপনার `Naim-LiveTVHD-apps` repository-এর `main` branch-এর root-এ যান।
3. ZIP-এর ভেতরের সব ফাইল ও folder upload করুন। `www` folder-টি repository root-এ থাকবে; `www`-এর ভেতরে আরেকটি `www` করবেন না।
4. আগের `package.json`, `capacitor.config.json` এবং `.github/workflows/Naim-LiveTVHD.yml` থাকলে নতুন ফাইল দিয়ে Replace করুন।
5. `www/index.html`, `www/icon.png` এবং `www/1000273307 (1).png`-ও নতুন ফাইল দিয়ে Replace করুন।
6. Commit changes করুন।
7. GitHub-এর **Actions** tab খুলুন। **Build Naim LiveTVHD APK** workflow চলবে। না চললে workflow খুলে **Run workflow** চাপুন।
8. সবুজ Success হলে run-এর নিচে **Artifacts** থেকে `Naim-LiveTVHD-APK` ডাউনলোড করুন। ZIP Extract করে `app-debug.apk` ইনস্টল করুন।

## গুরুত্বপূর্ণ

- এটি Debug APK; Play Store-এ প্রকাশের জন্য আলাদা signed release build লাগবে।
- Android 6.0+ লক্ষ্য করে তৈরি; সব ফোনে শতভাগ চলার নিশ্চয়তা দেওয়া যায় না।
- লাইভ চ্যানেল চলা নির্ভর করে stream URL, অনুমতি, নেটওয়ার্ক, codec ও provider-এর availability-এর ওপর। বন্ধ বা মেয়াদোত্তীর্ণ URL APK ঠিক করতে পারবে না।
- আপনার ওয়েব অ্যাপের CDN-ভিত্তিক player library ও Supabase Cloud Sync-এর জন্য Internet প্রয়োজন।
- Supabase-এর `anon`/publishable key ছাড়া `service_role` key কখনো অ্যাপে দেবেন না।
