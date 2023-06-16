<p align="center"><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/logo.svg"/></a><br/><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/xxai.svg"/></a></p><p align="center"><a href="https://github.com/xxai-art/doc#readme"><img alt="I18N" src="https://cdn.jsdelivr.net/gh/wactax/img/t.svg"/></a>　<a href="https://groups.google.com/u/0/g/xxai-art"><img alt="Google Groups" src="https://cdn.jsdelivr.net/gh/wactax/img/g-groups.svg"/></a></p>

Adalah disyorkan untuk memasang nodejs, [direnv](https://direnv.net) , [bun](https://github.com/oven-sh/bun) dahulu, dan kemudian `direnv allow` selepas memasuki direktori ( [.envrc](https://github.com/xxai-art/doc/blob/main/.envrc) akan dilaksanakan secara automatik selepas memasuki direktori).

Maksudnya ialah: Terjemahan Cina ke bahasa Jepun, Korea, Inggeris, Inggeris kepada semua bahasa lain. Jika anda hanya mahu menyokong bahasa Cina dan Inggeris, anda boleh menulis `zh: en` .

Maksudnya ialah: Terjemahan Cina ke bahasa Jepun, Korea, Inggeris, Inggeris kepada semua bahasa lain. Jika anda hanya mahu menyokong bahasa Cina dan Inggeris, anda boleh menulis `zh: en` .

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

### Arahan Automasi Terjemahan Dokumen

Lihat repositori kod [xxai-art/doc](https://github.com/xxai-art/doc)

Adalah disyorkan untuk memasang nodejs, [direnv](https://direnv.net) , [bun](https://github.com/oven-sh/bun) dahulu, dan kemudian `direnv allow` selepas memasuki direktori ( [.envrc](https://github.com/xxai-art/doc/blob/main/.envrc) akan dilaksanakan secara automatik selepas memasuki direktori).

Untuk mengelakkan pangkalan kod besar diterjemahkan ke dalam ratusan bahasa, saya mencipta pangkalan kod berasingan untuk setiap bahasa dan mencipta organisasi untuk menyimpan pangkalan kod

Menetapkan pembolehubah persekitaran `GITHUB_ACCESS_TOKEN` dan kemudian menjalankan [create.github.coffee](https://github.com/xxai-art/doc/blob/main/create.github.coffee) akan membuat repositori kod secara automatik.

Sudah tentu, anda juga boleh meletakkannya dalam pangkalan kod.

Rujukan skrip terjemahan [run.sh](https://github.com/xxai-art/doc/blob/main/run.sh)

Kod skrip ditafsirkan seperti berikut:

[bunx](https://bun.sh/docs/cli/bunx) ialah pengganti npx, yang lebih pantas. Sudah tentu, jika anda tidak memasang bun, anda boleh menggunakan `npx` sebaliknya.

`bunx mdt zh` menjadikan `.mdt` dalam direktori zh sebagai `.md` , lihat 2 fail terpaut di bawah

* [coffee_plus.mdt](https://github.com/xxai-doc/zh/blob/main/coffee_plus.mdt)
* [coffee_plus.md](https://github.com/xxai-doc/zh/blob/main/coffee_plus.md)

`bunx i18n` ialah kod teras untuk terjemahan (jika anda hanya memasang `nodejs` , tetapi `bun` dan `direnv` tidak dipasang, anda juga boleh menjalankan `npx i18n` untuk menterjemah).

Ia akan menghuraikan [i18n.yml](https://github.com/xxai-art/doc/blob/main/i18n.yml) , konfigurasi `i18n.yml` dalam dokumen ini adalah seperti berikut:

```
en:
zh: ja ko en
```

Maksudnya ialah: Terjemahan Cina ke bahasa Jepun, Korea, Inggeris, Inggeris kepada semua bahasa lain. Jika anda hanya mahu menyokong bahasa Cina dan Inggeris, anda boleh menulis `zh: en` .

Yang terakhir ialah [gen.README.coffee](https://github.com/xxai-art/doc/blob/main/gen.README.coffee) , yang mengekstrak kandungan antara tajuk utama dan sari kata pertama `README.md` setiap bahasa untuk menjana entri `README.md` . Kod ini sangat mudah, anda boleh melihatnya sendiri.

Google API digunakan untuk terjemahan percuma. Jika anda tidak boleh mengakses Google, sila konfigurasikan dan tetapkan proksi, seperti:

```
export https_proxy=http://127.0.0.1:7890 http_proxy=http://127.0.0.1:7890 all_proxy=socks5://127.0.0.1:7890
```

Skrip terjemahan akan menjana cache yang diterjemahkan dalam direktori `.i18n` , sila semak dengan `git status` dan tambahkannya pada repositori kod untuk mengelakkan terjemahan berulang.

Sila jalankan `bunx i18n` setiap kali anda mengubah suai terjemahan untuk mengemas kini cache.

Jika teks asal dan terjemahan diubah suai pada masa yang sama, cache akan keliru, jadi jika anda ingin mengubah suai, anda hanya boleh mengubah suai satu, dan kemudian jalankan `bunx i18n` untuk mengemas kini cache.
