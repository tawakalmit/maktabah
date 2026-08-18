<script>
  const doaSections = [
    {
      arabic: `رَبِّ انْفَعْنَا بِمَا عَلَّمْتَنَا * رَبِّ عَلِّمْنَا الَّذِي يَنْفَعُنَا
رَبِّ فَقِّهْنَا وَفَقِّهْ أَهْلَنَا * وَقَرَابَاتٍ لَنَا فِي دِينِنَا`,
      latin: `Rabbinfa'na bima 'allamtana * Rabbi 'allimnalladzii yanfa'unaa
Rabbi faqqihnaa wa faqqih ahlanaa * wa qaraabaatil-lanaa fii diininaa`,
      translation: `Ya Tuhanku, berikanlah kemanfaatan atas apa yang Engkau ajarkan kepada kami. Ya Tuhanku, ajarkanlah kepada kami apa yang bermanfaat bagi kami.
Ya Tuhanku, berilah pemahaman (agama) kepada kami dan berilah pemahaman kepada keluarga kami, serta kerabat-kerabat kami dalam agama kami.`
    },
    {
      arabic: `تَوَسَّلْنَا بِتَعَلُّمٍ * تَوَسَّلْنَا بِتَعْلِيْمٍاَنْ تَرْزُقَنَا الوَاسِعَةَ * وَاَنْ تَرْزُقَنَا الأَمَانَةَ`,
      latin: `Tawassalnaa bi ta'allumin, tawassalnaa bi ta'liimin * An tarzuqonal waasi'ah, wa an tarzuqonal amaanah`,
      translation: `Kami bertawasul dengan belajar, kami bertawasul dengan mengajar. Agar Engkau memberikan kami rezeki yang luas, dan agar Engkau memberikan kami sifat amanah.`
    },
    {
      arabic: `صَلَّى اللهُ رَبُّنَا عَلَى النُّوْرِ الْمُبِيْنِ * أَحْمَدَ الْمُصْطَفَى سَيِّدِ الْمُرْسَلِيْنَوَعَلَى آلِهِ وَصَحْبِهِ أَجْمَعِيْنَ`,
      latin: `Shollallahu robbunaa ‘alan-nuuril mubiinAhmadal mushthofaa sayyidil mursaliinWa ‘alaa aalihii wa shohbihii ajma’iin`,
      translation: `Semoga Allah, Tuhan kami, mencurahkan rahmat kepada cahaya yang nyata. Yaitu Nabi Ahmad (Muhammad) pilihan, pemimpin para Rasul. Dan juga kepada keluarga serta para sahabat beliau semuanya.`
    },
  ]
</script>

<div class="doa-page">
  <div class="top-bar">
    <a class="back-btn" href="/">← Kembali</a>
  </div>

  <h1>Doa Selesai Mengaji</h1>
  {#each doaSections as section}
    <div class="prayer-block">
      <p class="arabic">{section.arabic}</p>

      <div class="section">
        <h2>Transliterasi (Latin)</h2>
        <p>{section.latin}</p>
      </div>

      <div class="section">
        <h2>Terjemahan</h2>
        <p>{section.translation}</p>
      </div>
    </div>
  {/each}
</div>
