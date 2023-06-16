<p align="center"><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/logo.svg"/></a><br/><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/xxai.svg"/></a></p><p align="center"><a href="https://github.com/xxai-art/doc#readme"><img alt="I18N" src="https://cdn.jsdelivr.net/gh/wactax/img/t.svg"/></a>　<a href="https://groups.google.com/u/0/g/xxai-art"><img alt="Google Groups" src="https://cdn.jsdelivr.net/gh/wactax/img/g-groups.svg"/></a></p>

# xxAI.seni

Sebahagian daripada kod tapak web adalah sumber terbuka, dialu-alukan untuk membantu mengoptimumkan terjemahan.

## kod bahagian hadapan

* [kod bahagian hadapan](https://github.com/xxai-art/web)
* [Pek bahasa untuk tapak secara keseluruhan](https://github.com/xxai-art/web/tree/main/i18n)
* [Pek bahasa untuk modul log masuk](https://github.com/wacpkg/user/tree/main/ui.i18n)
* [Dokumentasi Berbilang Bahasa Laman Web](https://github.com/xxai-doc)

Bahasa pengaturcaraan bahagian hadapan ialah [@w5/coffee_plus](http://npmjs.com/@w5/coffee_plus) , yang menambahkan beberapa ciri berdasarkan sintaks coffeescript, lihat [./coffee_plus.md](./coffee_plus.md) .

## Pengantarabangsaan laman web dan dokumen

Bina pada 3 projek berikut

* [@w5/mdt](https://www.npmjs.com/package/@w5/mdt)

  Akhiran ialah `.mdt` , anda boleh menggunakan sintaks yang serupa dengan `<+ ./coffee_plus/import.js>` untuk merujuk kepada fail luaran dan menjana penurunan nilai dengan akhiran `.md` .

* [@w5/trmd](https://www.npmjs.com/package/@w5/trmd)

  Terjemahan Markdown tidak akan menterjemah kod dan pautan, dan akan menyimpan ayat terjemahan yang disimpan. Jika terjemahan diubah suai tetapi teks asal tidak diubah suai, melaksanakannya sekali lagi tidak akan menimpa pengubahsuaian terjemahan.

* [@w5/i18n](https://www.npmjs.com/package/@w5/i18n)

  Fail bahasa untuk menterjemah tapak web yang dihasilkan `yaml` .
