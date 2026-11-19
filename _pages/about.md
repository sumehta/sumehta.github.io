---
layout: academic
title: home
permalink: /
---
{%- assign domain_labels = "language:Language & LLMs,vision:Vision & Multimodal,graphics:Computer Graphics,recsys:Search & Ranking" | split: "," -%}

<div class="home-intro" id="top" data-label="about">
  <img class="home-photo" src="{{ '/assets/img/prof_pic.jpg' | relative_url }}" alt="Photo of Sneha Mehta" width="160" height="160">
  <div class="home-intro-text">
  <h1 class="sr-only">Sneha Mehta</h1>
  <p class="home-tagline">AI Research Engineer and Writer @<a href="{{ site.substack_url }}">tech_muse</a></p>
  <p>I am interested in developing useful and safe AI agents. I earned my Ph.D. in the Data Mining Group at Virginia Tech, advised by <a href="https://scholar.google.com/citations?user=fMJwG7MAAAAJ&hl=en">Dr. Naren Ramakrishnan</a>, with funding from an NSF Graduate Research Fellowship and a DARPA research grant.</p>
  <p class="home-social">{% include social.html %}</p>
  </div>
</div>

{% if site.data.notable_tweets and site.data.notable_tweets.size > 0 %}
<div class="home-section" id="tweets" data-label="news">
  <h2>News</h2>
  <ul class="home-list">
    {%- for talk in site.data.notable_tweets %}
    <li>
      {% if talk.url %}<a href="{{ talk.url }}">{{ talk.title }}</a>{% else %}<strong>{{ talk.title }}</strong>{% endif %}
      <span class="home-meta">{{ talk.event }}{% if talk.note %} &mdash; {{ talk.note }}{% endif %}</span>
    </li>
    {%- endfor %}
  </ul>
</div>
{% endif %}

<div class="home-section" id="projects" data-label="projects / code">
  <h2>Projects / Code</h2>
  <div class="project-filters" role="group" aria-label="Filter projects by area">
    <button type="button" class="active" data-filter="all">All</button>
    <button type="button" data-filter="language">Language</button>
    <button type="button" data-filter="vision">Vision</button>
  </div>
  <div class="project-grid">
    {%- for p in site.data.projects_showcase %}
    <article class="project-card tag-border-{{ p.domain }}" data-domain="{{ p.domain }}">
      <h3>{% if p.url %}<a href="{{ p.url }}">{{ p.title }}</a>{% else %}{{ p.title }}{% endif %}</h3>
      <p>{{ p.summary }}</p>
    </article>
    {%- endfor %}
  </div>
</div>

<div class="home-section" id="experience" data-label="experience">
  <h2>Experience</h2>
  <ol class="timeline">
    {%- for job in site.data.experience %}
    <li class="timeline-item">
      <div class="timeline-dates">{{ job.dates }}</div>
      <div class="timeline-body">
        <h3 class="timeline-company">{% if job.logo %}<img class="timeline-logo" src="{{ '/assets/img/logos/' | append: job.logo | relative_url }}" alt="" loading="lazy">{% endif %}{{ job.company }}</h3>
        {%- assign meta = "" | split: "" -%}{%- if job.org %}{% assign meta = meta | push: job.org %}{% endif -%}{%- if job.location %}{% assign meta = meta | push: job.location %}{% endif %}
        {%- if meta.size > 0 %}<p class="home-meta">{{ meta | join: " &middot; " }}</p>{% endif %}
        {%- if job.domains %}
        <p class="tags">
          {%- for d in job.domains -%}
            {%- for pair in domain_labels -%}{%- assign kv = pair | split: ":" -%}{%- if kv[0] == d %}<span class="tag tag-{{ d }}">{{ kv[1] }}</span>{% endif -%}{%- endfor -%}
          {%- endfor -%}
        </p>
        {%- endif %}
        <p class="timeline-summary">{{ job.summary }}</p>
      </div>
    </li>
    {%- endfor %}
  </ol>
</div>

<div class="home-section" id="publications" data-label="publications">
  <h2>Publications</h2>
  <p class="home-note">Also on <a href="https://scholar.google.com/citations?user={{ site.scholar_userid }}">Google Scholar</a>.</p>
  <ul class="home-list">
    <li>
      <a href="https://arxiv.org/abs/2310.16303">URL-BERT: Training Webpage Representations via Social Media Engagements</a>
      <span class="home-meta">Qamar, Verma, El-Kishky, Binnani, <strong>Mehta</strong>, Berg-Kirkpatrick &mdash; arXiv, 2023</span>
    </li>
    <li>
      <a href="https://proceedings.neurips.cc/paper_files/paper/2022/file/09723c9f291f6056fd1885081859c186-Paper-Datasets_and_Benchmarks.pdf">TweetNERD: End to End Entity Linking Benchmark for Tweets</a>
      <span class="home-meta">Mishra, Saini, Makki, <strong>Mehta</strong>, Haghighi, Mollahosseini &mdash; NeurIPS Datasets &amp; Benchmarks, 2022</span>
    </li>
    <li>
      <a href="https://arxiv.org/abs/2204.02531">Improving Zero-Shot Event Extraction via Sentence Simplification</a>
      <span class="home-meta"><strong>Mehta</strong>, Rangwala, Ramakrishnan &mdash; CASE @ EMNLP, 2022</span>
    </li>
    <li>
      <a href="https://aclanthology.org/2022.wnut-1.7">NTULM: Enriching Social Media Text Representations with Non-Textual Units</a>
      <span class="home-meta">Li, Mishra, El-Kishky, <strong>Mehta</strong>, Kulkarni &mdash; W-NUT @ COLING, 2022</span>
    </li>
    <li>
      <a href="https://aclanthology.org/2022.mrl-1.12">Towards Improved Distantly Supervised Multilingual Named-Entity Recognition for Tweets</a>
      <span class="home-meta">Eskander, Mishra, <strong>Mehta</strong>, et al. &mdash; MRL @ EMNLP, 2022</span>
    </li>
    <li>
      <a href="https://vtechworks.lib.vt.edu/items/64cf6c78-7eca-48aa-9326-2bbaa1c20d94">Towards Explainable Event Detection and Extraction</a>
      <span class="home-meta"><strong>Mehta</strong> &mdash; Ph.D. thesis, Virginia Tech, 2021</span>
    </li>
    <li>
      <a href="https://ojs.aaai.org/index.php/AAAI/article/view/6369">Simplify-Then-Translate: Automatic Preprocessing for Black-Box Translation</a>
      <span class="home-meta"><strong>Mehta</strong>, Azarnoush, Chen, Saluja, Misra, Bihani, Kumar &mdash; AAAI, 2020</span>
    </li>
    <li>
      <a href="https://arxiv.org/abs/1912.00835">Low Rank Factorization for Compact Multi-Head Self-Attention</a>
      <span class="home-meta"><strong>Mehta</strong>, Rangwala, Ramakrishnan &mdash; arXiv, 2019</span>
    </li>
    <li>
      <a href="https://doi.org/10.1145/3308558.3313659">Event Detection Using Hierarchical Multi-Aspect Attention</a>
      <span class="home-meta"><strong>Mehta</strong>, Islam, Rangwala, Ramakrishnan &mdash; The Web Conference (WWW), 2019</span>
    </li>
    <li>
      <a href="https://doi.org/10.1145/3301275.3302301">Photo Sleuth: Combining Human Expertise and Face Recognition to Identify Historical Portraits</a>
      <span class="home-meta">Mohanty, Thames, <strong>Mehta</strong>, Luther &mdash; ACM IUI, 2019 &middot; <strong>Best Paper Award</strong></span>
    </li>
    <li>
      <a href="https://crowd.cs.vt.edu/wp-content/uploads/2016/10/exploratory-study-human_camera_ready.pdf">An Exploratory Study of Human Performance in Image Geolocation Tasks</a>
      <span class="home-meta"><strong>Mehta</strong>, North, et al. &mdash; GroupSight @ HCOMP, 2016</span>
    </li>
  </ul>
  <p class="home-note home-patent"><strong>Patent:</strong> Automatic Preprocessing for Black Box Translation &mdash; Mehta, Kumar, Bihani, Chen, Misra, Semeniakin, Saluja, Bonaci. U.S. Pat. Ser. No. 62/896,552.</p>
</div>

<div class="home-section" id="education" data-label="education">
  <h2>Education</h2>
  <ul class="home-list">
    <li><strong>Virginia Tech</strong><span class="home-meta">Ph.D., Computer Science &mdash; advised by <a href="https://scholar.google.com/citations?user=fMJwG7MAAAAJ&hl=en">Naren Ramakrishnan</a></span></li>
    <li><strong>BITS Pilani</strong><span class="home-meta">B.E., Computer Science &amp; Engineering; M.Sc., Mathematics</span></li>
    <li><strong><a href="https://www.hri.res.in/">Harish-Chandra Research Institute</a></strong><span class="home-meta"><a href="https://www.hri.res.in/~spim/">Summer Programme in Mathematics (SPIM)</a>, 2012</span></li>
  </ul>
</div>

<div class="home-section" id="contact" data-label="contact">
  <h2>Contact</h2>
  <p>Find me on the platforms below, or read my writing on <a href="https://techmuse2.substack.com">Substack</a>.</p>
  <p class="home-social">{% include social.html %}</p>
</div>

<script>
  (function () {
    var reduceMotion = window.matchMedia('(prefers-reduced-motion: reduce)').matches;

    // Project filters: cards slide to their new spots (FLIP) and newly shown ones fade in.
    var cards = Array.prototype.slice.call(document.querySelectorAll('.project-card'));
    document.querySelectorAll('.project-filters button').forEach(function (btn) {
      btn.addEventListener('click', function () {
        var f = btn.dataset.filter;
        document.querySelectorAll('.project-filters button').forEach(function (b) { b.classList.toggle('active', b === btn); });
        var before = new Map();
        cards.forEach(function (c) { if (!c.hidden) before.set(c, c.getBoundingClientRect()); });
        cards.forEach(function (c) { c.hidden = f !== 'all' && c.dataset.domain !== f; });
        if (reduceMotion || !Element.prototype.animate) return;
        cards.forEach(function (c) {
          if (c.hidden) return;
          var first = before.get(c), last = c.getBoundingClientRect();
          if (first) {
            var dx = first.left - last.left, dy = first.top - last.top;
            if (dx || dy) c.animate([{ transform: 'translate(' + dx + 'px,' + dy + 'px)' }, { transform: 'none' }],
                                    { duration: 380, easing: 'cubic-bezier(.2,.8,.2,1)' });
          } else {
            c.animate([{ opacity: 0, transform: 'scale(.92)' }, { opacity: 1, transform: 'none' }],
                      { duration: 320, easing: 'ease-out' });
          }
        });
      });
    });

    // Title bar drag: grab a section's striped title bar to nudge the window; it springs back on release.
    document.querySelectorAll('.home-section').forEach(function (sec) {
      var startX, startY, pid = null;
      function onBar(e) { return e.clientY - sec.getBoundingClientRect().top <= 26; }
      sec.addEventListener('pointerdown', function (e) {
        if (e.pointerType === 'touch' || e.button !== 0 || !onBar(e)) return;
        if (e.target.closest('a, button')) return;
        pid = e.pointerId; startX = e.clientX; startY = e.clientY;
        sec.setPointerCapture(pid); sec.classList.add('is-dragging');
        e.preventDefault();
      });
      sec.addEventListener('pointermove', function (e) {
        if (e.pointerId !== pid) return;
        // Rubber-band: the window follows the pointer but resists, staying within a few pixels.
        var dx = e.clientX - startX, dy = e.clientY - startY;
        function band(d) { return 28 * Math.tanh(d / 90); }
        sec.style.transform = 'translate(' + band(dx) + 'px,' + band(dy) + 'px)';
      });
      function release(e) {
        if (e.pointerId !== pid) return;
        pid = null;
        var from = sec.style.transform || 'none';
        sec.classList.remove('is-dragging'); sec.style.transform = '';
        if (!reduceMotion && Element.prototype.animate && from !== 'none') {
          sec.animate([{ transform: from }, { transform: 'none' }],
                      { duration: 450, easing: 'cubic-bezier(.3, 1.6, .5, 1)' });
        }
      }
      sec.addEventListener('pointerup', release);
      sec.addEventListener('pointercancel', release);
    });

  })();
</script>
