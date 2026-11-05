# MOOPI Desktop — yig'ilma

Bu VSCodium'ning forki. Faqat shu narsalar o'zgargan:

- `prepare_vscode.sh` (stable blok): mahsulot nomi "MOOPI Desktop", buyruq nomi `moopi`, bundle id
  `uz.moopi.desktop`, ma'lumot papkasi `.moopi-desktop`, Windows identifikatorlari (yangi GUID'lar).
- `src/stable/resources/`: MOOPI belgisi (macOS icns, Windows ico/bmp, Linux png/svg, server png).
- `.github/workflows/*`: `APP_NAME: MOOPI-Desktop`, `BINARY_NAME: moopi`.

Yig'ish: GitHub Actions → "CI - Build - macOS" / "Windows" / "Linux" (workflow_dispatch yoki master'ga push),
natija artifact sifatida. Imzolash: `publish-stable-macos` workflow'i `CERTIFICATE_OSX_*` secret'lari bo'lsa
Apple Developer ID bilan imzolaydi va notarizatsiya qiladi; ularsiz macOS yig'ilmasi imzosiz chiqadi.

Upstream bilan yangilash: `git fetch upstream && git merge upstream/master` (konfliktlar faqat yuqoridagi fayllarda).
Claude Code kengaytmasi bu yig'ilmaga kirmaydi: u Open VSX'dan o'rnatiladi (MOOPI kengaytmasi bilan birga,
/Users/mnekboyev/moopi-desktop repo'sidagi `dev/run.sh` kabi).
