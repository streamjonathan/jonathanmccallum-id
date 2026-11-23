---
title: "Sarankan seorang seniman"
slug: suggest-an-artist
---

Aku senang sekali mendengar tentang musisi dan seniman yang mengikuti Yesus. Kalau kamu kenal seseorang yang kamu ingin aku tuliskan, wawancarai, atau buatkan video reaksi, beri tahu aku di sini.

Satu nama dan satu tautan saja sudah cukup — dan beberapa kata tentang kenapa dia. Aku membaca semua yang masuk. Terima kasih banyak.

Kenal seseorang? Ketuk fotonya, formulir akan terisi sendiri — lalu tambahkan beberapa kata tentang kenapa dia, dan kirim.

<div class="suggest-carousel" role="list" aria-label="Musisi dan seniman yang bisa kamu sarankan">
{% for artist in suggest_carousel %}
  <button type="button" class="suggest-pick" role="listitem" data-artist="{{ artist.name }}" data-link="{{ artist.profile }}" title="Sarankan {{ artist.name }}">
    <img src="{{ artist.img }}" alt="{{ artist.name }}" loading="lazy" width="150" height="150">
    <span class="suggest-pick__name">{{ artist.name }}</span>
    <span class="suggest-pick__note">{{ artist.note }}</span>
  </button>
{% endfor %}
</div>

<p class="suggest-carousel__more">Atau sarankan orang baru di bawah — siapa pun yang menurutmu harus aku dengar.</p>

Situs ini bukan untuk orang di bawah 18 tahun.

<form id="suggest-form" class="suggest-form">
  <label for="suggest-artist">Nama seniman</label>
  <input id="suggest-artist" name="artist" type="text" maxlength="200" placeholder="Siapa yang harus aku lihat?" required>

  <label for="suggest-link">Tautan profil media sosial</label>
  <input id="suggest-link" name="link" type="url" maxlength="500" placeholder="https://www.instagram.com/…" required>

  <fieldset class="suggest-kinds">
    <legend>Apa yang harus aku lakukan dengan mereka?</legend>
    <label><input type="checkbox" name="kind" value="write"> Tulis tentang mereka</label>
    <label><input type="checkbox" name="kind" value="interview"> Wawancarai mereka</label>
    <label><input type="checkbox" name="kind" value="reaction"> Buat video reaksi tentang mereka</label>
  </fieldset>

  <label for="suggest-why">Kenapa dia?</label>
  <textarea id="suggest-why" name="why" rows="3" maxlength="500" placeholder="Beberapa kata saja cukup…"></textarea>

  <label for="suggest-name">Namamu <span class="optional">(opsional)</span></label>
  <input id="suggest-name" name="fromName" type="text" maxlength="100" placeholder="Supaya aku bisa berterima kasih">

  <label for="suggest-from-link">Tautan profil media sosialmu <span class="optional">(opsional)</span></label>
  <input id="suggest-from-link" name="fromLink" type="url" maxlength="500" placeholder="https://www.instagram.com/…">

  <button id="suggest-button" type="button">Kirim saran</button>

  <p id="suggest-result" aria-live="polite"></p>
</form>
