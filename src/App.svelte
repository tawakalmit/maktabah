<script>
  const menuList = [
    {
      id: 1,
      label: 'Al Quran',
      url: 'https://alquran.tawakalmit.my.id',
      type: 'external'
    },
    {
      id: 2,
      label: 'Hadiah',
      url: 'https://hadiah.tawakalmit.my.id',
      type: 'external'
    },
    {
      id: 3,
      label: 'Doa selesai mengaji',
      url: '/doa-selesai-mengaji/',
      type: 'internal'
    }
  ]
</script>

<main class="page">
  <header class="hero">
    <h2 class="title">Maktabah</h2>
  </header>

  <section class="menu">
    {#each menuList as item}
      {#if item.type === 'external'}
        <a class="card" href={item.url} target="_blank" rel="noopener noreferrer">
          <div class="label">{item.id}. {item.label}</div>
        </a>
      {:else}
        <a class="card action-btn" href={item.url}>
          <div class="label">{item.id}. {item.label}</div>
        </a>
      {/if}
    {/each}
  </section>
</main>
