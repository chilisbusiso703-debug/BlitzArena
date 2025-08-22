# BlitzArena
Sports news and updates 
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>BlitzArena — Sports News & Live Updates</title>
  <meta name="description" content="BlitzArena: Fast, fearless, fan-first sports coverage. Soccer, Basketball, UFC, Rugby, Premier League, LaLiga, Bundesliga." />
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&display=swap" rel="stylesheet">
  <!-- Tailwind via CDN (no build tools needed) -->
  <script src="https://cdn.tailwindcss.com"></script>
  <script>
    tailwind.config = {
      theme: {
        extend: {
          fontFamily: { sans: ['Inter', 'ui-sans-serif', 'system-ui'] },
          colors: {
            brand: {
              DEFAULT: '#111827',
            }
          }
        }
      }
    }
  </script>
  <!-- Lucide icons -->
  <script type="module" src="https://unpkg.com/lucide@latest/dist/umd/lucide.js"></script>
  <style>
    /* Smooth scrolling */
    html { scroll-behavior: smooth; }
    /* Hide scrollbar in ticker */
    .no-scrollbar::-webkit-scrollbar { display: none; }
    .no-scrollbar { -ms-overflow-style: none; scrollbar-width: none; }
  </style>
</head>
<body class="bg-gradient-to-b from-white to-slate-50 text-slate-900 font-sans">
  <!-- Header -->
  <header class="sticky top-0 z-50 border-b border-slate-200 bg-white/90 backdrop-blur">
    <div class="mx-auto flex max-w-7xl items-center justify-between gap-4 px-4 py-3">
      <div class="flex items-center gap-3">
        <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 6v6l4 2"/></svg>
        <span class="text-xl font-extrabold tracking-tight">BlitzArena</span>
        <span class="hidden rounded-full bg-slate-900 px-2 py-0.5 text-xs font-semibold text-white sm:inline">LIVE</span>
      </div>
      <nav class="hidden items-center gap-6 md:flex">
        <a href="#top" class="text-sm font-medium text-slate-700 hover:text-black">Top</a>
        <a href="#soccer" class="text-sm font-medium text-slate-700 hover:text-black">Soccer</a>
        <a href="#basketball" class="text-sm font-medium text-slate-700 hover:text-black">Basketball</a>
        <a href="#ufc" class="text-sm font-medium text-slate-700 hover:text-black">UFC</a>
        <a href="#rugby" class="text-sm font-medium text-slate-700 hover:text-black">Rugby</a>
        <a href="#trending" class="text-sm font-medium text-slate-700 hover:text-black">Trending</a>
      </nav>
      <div class="flex items-center gap-2">
        <input id="search" placeholder="Search teams, leagues, players" class="hidden w-60 rounded-xl border border-slate-200 bg-white px-3 py-2 text-sm outline-none ring-0 focus:border-slate-300 md:block" />
        <button id="mobileMenuBtn" class="inline-flex h-9 w-9 items-center justify-center rounded-xl border border-slate-200 md:hidden">
          <svg id="menuIcon" xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"/></svg>
        </button>
      </div>
    </div>
    <!-- Mobile nav -->
    <div id="mobileNav" class="hidden border-t border-slate-200 bg-white px-4 py-3 md:hidden">
      <div class="mb-3 flex items-center gap-2">
        <input id="msearch" placeholder="Search teams, leagues, players" class="w-full rounded-xl border border-slate-200 bg-white px-3 py-2 text-sm outline-none ring-0 focus:border-slate-300" />
      </div>
      <div class="flex flex-wrap gap-2">
        <a href="#soccer" class="rounded-xl border border-slate-200 px-3 py-1.5 text-sm">Soccer</a>
        <a href="#basketball" class="rounded-xl border border-slate-200 px-3 py-1.5 text-sm">Basketball</a>
        <a href="#ufc" class="rounded-xl border border-slate-200 px-3 py-1.5 text-sm">UFC</a>
        <a href="#rugby" class="rounded-xl border border-slate-200 px-3 py-1.5 text-sm">Rugby</a>
        <a href="#trending" class="rounded-xl border border-slate-200 px-3 py-1.5 text-sm">Trending</a>
      </div>
    </div>
  </header>

  <!-- Main -->
  <main class="mx-auto max-w-7xl px-4 pb-16 pt-6">
    <!-- Ticker -->
    <section class="mb-6">
      <div class="w-full overflow-hidden rounded-2xl bg-black text-white">
        <div class="flex items-center gap-2 px-4 py-2">
          <span class="text-sm font-semibold">Live Ticker</span>
        </div>
        <div class="relative flex whitespace-nowrap py-2">
          <div id="ticker" class="no-scrollbar flex gap-8 px-4 animate-[marquee_22s_linear_infinite] will-change-transform"></div>
        </div>
      </div>
    </section>

    <!-- Ad Leaderboard -->
    <section class="mb-6">
      <div class="w-full rounded-2xl border border-dashed border-slate-300 bg-slate-50 p-6 text-center text-sm text-slate-500">Leaderboard Ad 970x90 (replace with AdSense later)</div>
    </section>

    <!-- Top Stories -->
    <section id="top" class="grid grid-cols-1 gap-6 md:grid-cols-2">
      <!-- Filled by JS from data -->
    </section>

    <!-- Latest Feed + Sidebar -->
    <section class="mt-8 grid grid-cols-1 gap-6 lg:grid-cols-3">
      <div class="lg:col-span-2">
        <div class="mb-3 flex items-center justify-between">
          <h2 class="text-xl font-extrabold tracking-tight">Latest</h2>
          <div class="hidden gap-2 md:flex">
            <button data-filter="all" class="filter-btn rounded-xl border px-3 py-1.5 text-sm">All</button>
            <button data-filter="soccer" class="filter-btn rounded-xl border px-3 py-1.5 text-sm">Soccer</button>
            <button data-filter="basketball" class="filter-btn rounded-xl border px-3 py-1.5 text-sm">Basketball</button>
            <button data-filter="ufc" class="filter-btn rounded-xl border px-3 py-1.5 text-sm">UFC</button>
            <button data-filter="rugby" class="filter-btn rounded-xl border px-3 py-1.5 text-sm">Rugby</button>
          </div>
        </div>
        <div class="mb-4 flex items-center gap-2">
          <input id="feedSearch" placeholder="Search headlines" class="w-full rounded-xl border border-slate-200 bg-white px-3 py-2 text-sm outline-none ring-0 focus:border-slate-300" />
          <button class="rounded-xl border border-slate-200 px-3 py-2 text-sm">Search</button>
        </div>
        <div id="feed" class="grid grid-cols-1 gap-6 md:grid-cols-2"></div>
        <div class="mt-6 w-full rounded-2xl border border-dashed border-slate-300 bg-slate-50 p-6 text-center text-sm text-slate-500">In-Feed Ad 728x90</div>
      </div>
      <aside class="space-y-6">
        <div class="w-full rounded-2xl border border-dashed border-slate-300 bg-slate-50 p-6 text-center text-sm text-slate-500">Sidebar Ad 300x600</div>
        <div class="rounded-2xl border border-slate-200 bg-white">
          <div class="border-b px-4 py-3"><h3 class="flex items-center gap-2 text-base font-bold">Trending Now</h3></div>
          <div id="trending" class="space-y-4 p-4"></div>
        </div>
        <div class="rounded-2xl border border-slate-200 bg-white">
          <div class="border-b px-4 py-3"><h3 class="text-base font-bold">Get the Blitz</h3><p class="mt-1 text-xs text-slate-500">Breaking scores, sharp analysis, weekend previews.</p></div>
          <form id="newsletter" class="p-4">
            <input type="email" required placeholder="you@example.com" class="mb-2 w-full rounded-xl border border-slate-200 px-3 py-2 text-sm outline-none focus:border-slate-300" />
            <button class="w-full rounded-xl bg-slate-900 px-4 py-2 text-sm font-semibold text-white">Subscribe</button>
            <p id="nsMsg" class="mt-2 hidden text-xs text-green-700">You're in! Check your email to confirm.</p>
          </form>
        </div>
      </aside>
    </section>
  </main>

  <!-- Footer -->
  <footer class="mt-16 border-t bg-white">
    <div class="mx-auto grid max-w-7xl grid-cols-1 gap-8 px-4 py-10 md:grid-cols-4">
      <div>
        <div class="flex items-center gap-2">
          <span class="text-lg font-bold">BlitzArena</span>
        </div>
        <p class="mt-2 text-sm text-slate-600">Fast, fearless, and fan-first sports coverage across the globe.</p>
      </div>
      <div>
        <h4 class="font-semibold">Sections</h4>
        <ul class="mt-2 space-y-2 text-sm text-slate-700">
          <li><a href="#soccer" class="hover:underline">Soccer</a></li>
          <li><a href="#basketball" class="hover:underline">Basketball</a></li>
          <li><a href="#ufc" class="hover:underline">UFC</a></li>
          <li><a href="#rugby" class="hover:underline">Rugby</a></li>
        </ul>
      </div>
      <div>
        <h4 class="font-semibold">Leagues</h4>
        <ul class="mt-2 space-y-2 text-sm text-slate-700">
          <li>Premier League</li>
          <li>LaLiga</li>
          <li>Bundesliga</li>
          <li>Champions League</li>
        </ul>
      </div>
      <div>
        <h4 class="font-semibold">Get the Blitz</h4>
        <p class="text-sm text-slate-600">Join our weekly newsletter.</p>
        <a href="#newsletter" class="mt-2 inline-block rounded-xl bg-slate-900 px-4 py-2 text-sm font-semibold text-white">Subscribe</a>
      </div>
    </div>
    <div class="border-t py-4 text-center text-xs text-slate-500">© <span id="year"></span> BlitzArena Media. All rights reserved.</div>
  </footer>

  <!-- Data & Scripts -->
  <script>
    // Mock ticker entries
    const TICKER = [
      { tag: 'FT', text: 'EPL: City 2–1 United' },
      { tag: 'FT', text: 'NBA: Bulls 104–98 Kings' },
      { tag: 'LIVE', text: 'UFC: Main Card starting soon' },
      { tag: 'FT', text: 'URC: Sharks 17–14 Stormers' },
      { tag: 'FT', text: 'LaLiga: Barça 3–0 Sevilla' },
      { tag: 'FT', text: 'Bundesliga: Dortmund 2–2 Leverkusen' },
    ];

    // Mock articles (extend any time)
    const ARTICLES = [
      {
        id: 1,
        title: 'Last-Minute Stunner Seals Derby Thriller',
        dek: 'An injury-time rocket flips the table and sets social feeds ablaze.',
        cat: 'soccer',
        league: 'premier-league',
        author: 'By Staff',
        time: '3m ago',
        img: 'https://images.unsplash.com/photo-1522770179533-24471fcdba45?q=80&w=1600&auto=format&fit=crop',
        featured: true,
        trend: 87,
      },
      {
        id: 2,
        title: 'Rising Rookie Drops Career-High — Team Surges Late',
        dek: 'The arena erupts as a first-year phenom rewrites the script.',
        cat: 'basketball',
        league: 'nba',
        author: 'By J. Dlamini',
        time: '18m ago',
        img: 'https://images.unsplash.com/photo-1517649763962-0c623066013b?q=80&w=1600&auto=format&fit=crop',
        featured: true,
        trend: 73,
      },
      {
        id: 3,
        title: 'Captain’s Ton Lights Up Night Session',
        dek: 'Clinical stroke play and ice-cool leadership in a statement win.',
        cat: 'rugby',
        league: 'urc',
        author: 'By Sports Desk',
        time: '32m ago',
        img: 'https://images.unsplash.com/photo-1521417531039-25c71c139b37?q=80&w=1600&auto=format&fit=crop',
        featured: false,
        trend: 64,
      },
      {
        id: 4,
        title: 'Powerhouse Pack Dominates Breakdown',
        dek: 'Ruthless rucks and surgical set-pieces decide a bruising contest.',
        cat: 'rugby',
        league: 'rugby-championship',
        author: 'By L. van Wyk',
        time: '54m ago',
        img: 'https://images.unsplash.com/photo-1521417531039-25c71c139b37?q=80&w=1600&auto=format&fit=crop',
        featured: false,
        trend: 51,
      },
      {
        id: 5,
        title: 'Underdog Sweep Sends Shockwaves Through Bracket',
        dek: 'Seed-busting drama as a dark horse runs the table.',
        cat: 'ufc',
        league: 'ufc',
        author: 'By M. Khumalo',
        time: '1h ago',
        img: 'https://images.unsplash.com/photo-1511512578047-dfb367046420?q=80&w=1600&auto=format&fit=crop',
        featured: false,
        trend: 44,
      },
      {
        id: 6,
        title: 'LaLiga Title Race Tightens After Shock Away Win',
        dek: 'Table shaken as underdogs steal points on the road.',
        cat: 'soccer',
        league: 'laliga',
        author: 'By Staff',
        time: '2h ago',
        img: 'https://images.unsplash.com/photo-1518081461904-9d8f136351c1?q=80&w=1600&auto=format&fit=crop',
        featured: false,
        trend: 58,
      },
      {
        id: 7,
        title: 'Bundesliga New Boy Nets Brace on Debut',
        dek: 'Dream start lights up Saturday slate.',
        cat: 'soccer',
        league: 'bundesliga',
        author: 'By T. Müller',
        time: '3h ago',
        img: 'https://images.unsplash.com/photo-1521412644187-c49fa049e84d?q=80&w=1600&auto=format&fit=crop',
        featured: false,
        trend: 62,
      },
    ];

    // Helpers
    const $ = (sel) => document.querySelector(sel);
    const $$ = (sel) => Array.from(document.querySelectorAll(sel));

    // Render ticker
    function renderTicker() {
      const el = $('#ticker');
      el.innerHTML = '';
      TICKER.concat(TICKER).forEach((t) => {
        const item = document.createElement('div');
        item.className = 'flex items-center gap-3 text-sm';
        const badge = document.createElement('span');
        badge.className = 'rounded bg-white/10 px-2 py-0.5 text-white';
        badge.textContent = t.tag;
        const text = document.createElement('span');
        text.textContent = t.text;
        item.appendChild(badge);
        item.appendChild(text);
        el.appendChild(item);
      });
    }

    // Render cards
    function articleCard(a) {
      return `
        <div class="overflow-hidden rounded-2xl border border-slate-200 bg-white shadow-sm transition hover:shadow-lg">
          <div class="relative h-44 w-full overflow-hidden">
            <img src="${a.img}" alt="${a.title}" class="h-full w-full object-cover" />
            <div class="absolute left-3 top-3 flex items-center gap-2">
              <span class="rounded bg-black/70 px-2 py-0.5 text-xs font-semibold text-white capitalize">${a.cat}</span>
              ${a.featured ? '<span class="rounded bg-white/90 px-2 py-0.5 text-xs font-semibold text-black">Featured</span>' : ''}
            </div>
          </div>
          <div class="p-4">
            <h3 class="line-clamp-2 text-lg font-semibold leading-snug">${a.title}</h3>
            <p class="mt-1 line-clamp-2 text-sm text-slate-600">${a.dek}</p>
            <div class="mt-3 flex items-center justify-between text-xs text-slate-500">
              <span>${a.time}</span>
              <span>${a.author}</span>
            </div>
          </div>
        </div>`;
    }

    function renderTop() {
      const top = ARTICLES.filter(a => a.featured);
      $('#top').innerHTML = top.map(articleCard).join('');
    }

    function renderFeed(filter = 'all', q = '') {
      let list = ARTICLES.slice();
      if (filter !== 'all') list = list.filter(a => a.cat === filter);
      if (q) {
        const qq = q.toLowerCase();
        list = list.filter(a => a.title.toLowerCase().includes(qq) || a.dek.toLowerCase().includes(qq));
      }
      $('#feed').innerHTML = list.map(articleCard).join('');
    }

    function renderTrending() {
      const list = ARTICLES.slice().sort((a,b) => b.trend - a.trend).slice(0,5);
      $('#trending').innerHTML = list.map((a,i) => `
        <div class="flex items-center gap-3">
          <div class="flex h-8 w-8 items-center justify-center rounded-full bg-slate-100 text-sm font-bold">${i+1}</div>
          <div>
            <div class="line-clamp-2 text-sm font-semibold leading-snug">${a.title}</div>
            <div class="text-xs text-slate-500 capitalize">${a.cat} • ${a.time}</div>
          </div>
        </div>`).join('');
    }

    // Interactions
    function wireUp() {
      // Mobile menu
      const mbtn = $('#mobileMenuBtn');
      const mnav = $('#mobileNav');
      mbtn.addEventListener('click', () => mnav.classList.toggle('hidden'));

      // Filters
      $$('.filter-btn').forEach(btn => {
        btn.addEventListener('click', () => {
          $$('.filter-btn').forEach(b => b.classList.remove('bg-slate-900','text-white'));
          btn.classList.add('bg-slate-900','text-white');
          renderFeed(btn.dataset.filter, $('#feedSearch').value);
        });
      });

      // Search boxes sync
      const search = $('#search');
      const msearch = $('#msearch');
      const feedSearch = $('#feedSearch');
      [search, msearch, feedSearch].forEach(input => {
        if (!input) return;
        input.addEventListener('input', (e) => {
          const v = e.target.value;
          if (input !== search && search) search.value = v;
          if (input !== msearch && msearch) msearch.value = v;
          if (input !== feedSearch && feedSearch) feedSearch.value = v;
          renderFeed(document.querySelector('.filter-btn.bg-slate-900')?.dataset.filter || 'all', v);
        });
      });

      // Newsletter (fake submit)
      $('#newsletter').addEventListener('submit', (e) => {
        e.preventDefault();
        document.getElementById('nsMsg').classList.remove('hidden');
        e.target.reset();
      });

      // Footer year
      document.getElementById('year').textContent = new Date().getFullYear();
    }

    // Init
    renderTicker();
    renderTop();
    renderFeed('all','');
    renderTrending();
    wireUp();
  </script>

  <!-- Simple marquee animation -->
  <style>
    @keyframes marquee { from { transform: translateX(0); } to { transform: translateX(-50%); } }
  </style>
</body>
</html>
