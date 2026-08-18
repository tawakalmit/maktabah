<script>
  import Doa from './Doa.svelte'
  import { onMount } from 'svelte'

  const navItems = [{ id: 'home', label: 'Home', path: '/', icon: '⌂' }]

  const menuList = [
    {
      id: 1,
      label: 'Al Quran',
      url: 'https://alquran.tawakalmit.my.id',
      type: 'external',
      meta: 'alquran.tawakalmit.my.id'
    },
    {
      id: 2,
      label: 'Hadiah',
      url: 'https://hadiah.tawakalmit.my.id',
      type: 'external',
      meta: 'hadiah.tawakalmit.my.id'
    },
    {
      id: 3,
      label: 'Doa selesai mengaji',
      url: '/doa-selesai-mengaji',
      type: 'internal',
      meta: 'Halaman baru di project ini'
    }
  ]

  let route = location.pathname || '/'
  let theme = 'light'

  const setTheme = (t) => {
    theme = t
    if (t === 'dark') document.documentElement.setAttribute('data-theme', 'dark')
    else document.documentElement.removeAttribute('data-theme')
    localStorage.setItem('theme', t)
  }

  const toggleTheme = () => setTheme(theme === 'dark' ? 'light' : 'dark')

  const navigate = (path) => {
    history.pushState({}, '', path)
    route = path
  }

  const isActive = (path) => route === path || (route === '/doa-selesai-mengaji' && path === '/')

  onMount(() => {
    const saved = localStorage.getItem('theme')
    setTheme(saved === 'dark' ? 'dark' : 'light')
    window.addEventListener('popstate', () => {
      route = location.pathname || '/'
    })
  })
</script>

<main class="page">
  {#if route === '/' || route === ''}
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
          <button class="card action-btn" on:click={() => navigate(item.url)}>
            <div class="label">{item.id}. {item.label}</div>
          </button>
        {/if}
      {/each}
    </section>
  {:else if route === '/doa-selesai-mengaji'}
    <section class="doa-content">
      <Doa />
    </section>
  {:else}
    <div class="doa-content">Halaman tidak ditemukan. <button on:click={() => navigate('/')} class="inline-btn">Kembali</button></div>
  {/if}

  <nav class="bottom-nav" aria-label="Navigation utama">
    {#each navItems as item}
      <button class:active={isActive(item.path)} class="nav-item" on:click={() => navigate(item.path)}>
        <span class="nav-icon">{item.icon}</span>
        <span>{item.label}</span>
      </button>
    {/each}
  </nav>
</main>
