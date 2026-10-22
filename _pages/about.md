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
  <p>I train and evaluate language and multimodal models that run in products used by hundreds of millions of people, most recently Meta AI on <a href='https://www.facebook.com/watch/?v=1611593950703542'>Ray-Ban Smart Glasses</a> and <a href='https://www.meta.com/vr-glasses/'>Quest and VR devices</a>, and before that TikTok Search and Twitter.</p>
  <p>I started on feature-film pipelines at <a href="https://www.dreamworks.com/movies/penguins-of-madagascar">DreamWorks Animation</a>, earned a Ph.D. in machine learning at Virginia Tech, and now work on post-training, RL, and agentic systems.</p>
  <p>I also write about AI research on my blog, <a class="substack-link" href="{{ site.substack_url }}">{% include substack_icon.html %}tech_muse on Substack</a>.</p>
  <p class="home-social">{% include social.html %}</p>
  </div>
</div>

<div class="home-section" id="interests" data-label="research interests">
  <h2>Research interests</h2>
  <p>My work has spanned three ways machines make sense of the world: <span class="interest interest-language">language</span>, from LLM post-training and agentic tool use to information extraction and translation; <span class="interest interest-vision">vision</span>, from multimodal assistants and video understanding to face recognition; and <span class="interest interest-graphics">graphics</span>, rendering and simulating worlds for feature animation.</p>
  <p>Next, I want to bring these together in <strong>world models</strong>: systems that understand the world the way people do, by combining sight, sound, language, and other senses into a single picture they can reason about, predict from, and act in.</p>
</div>

<div class="home-section" id="experience" data-label="experience">
  <h2>Experience</h2>
  <ol class="timeline">
    {%- for job in site.data.experience %}
    <li class="timeline-item">
      <div class="timeline-dates">{{ job.dates }}</div>
      <div class="timeline-body">
        <h3>{{ job.company }}</h3>
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

<div class="home-section" id="projects" data-label="projects">
  <h2>Projects</h2>
  <div class="project-filters" role="group" aria-label="Filter projects by area">
    <button type="button" class="active" data-filter="all">All</button>
    <button type="button" data-filter="language">Language</button>
    <button type="button" data-filter="vision">Vision</button>
  </div>
  <div class="project-grid">
    {%- for p in site.data.projects_showcase %}
    <article class="project-card tag-border-{{ p.domain }}" data-domain="{{ p.domain }}">
      <h3>{% if p.url %}<a href="{{ p.url }}">{{ p.title }}</a>{% else %}{{ p.title }}{% endif %}</h3>
      <p class="home-meta">{{ p.org }}{% if p.year %} &middot; {{ p.year }}{% endif %}</p>
      <p>{{ p.summary }}</p>
    </article>
    {%- endfor %}
  </div>
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

<div class="home-section" id="recognition" data-label="recognition &amp; education">
  <h2>Recognition &amp; education</h2>
  <div class="two-col">
    <ul class="home-list home-list-bullets">
      <li><a href="https://blog.twitch.tv/en/2020/01/15/introducing-our-2020-twitch-research-fellows/">Twitch (Amazon) Research Fellowship</a></li>
      <li><a href="https://crowd.cs.vt.edu/category/awards/">Best Paper Award, ACM IUI 2019</a></li>
      <li>Finalist, <a href="https://github.com/sumehta/odni-dac">ODNI Xpress Challenge</a></li>
      <li>Mitacs Globalink Research Grant</li>
    </ul>
    <ul class="home-list">
      <li><strong>Virginia Tech</strong><span class="home-meta">Ph.D., Computer Science &mdash; advised by <a href="https://scholar.google.com/citations?user=fMJwG7MAAAAJ&hl=en">Naren Ramakrishnan</a></span></li>
      <li><strong>BITS Pilani</strong><span class="home-meta">B.E., Computer Science &amp; Engineering; M.Sc., Mathematics (ranked 1st in class)</span></li>
    </ul>
  </div>
</div>

{% if site.data.notable_tweets and site.data.notable_tweets.size > 0 %}
<div class="home-section" id="tweets" data-label="talks &amp; posts">
  <h2>Talks &amp; posts</h2>
  <ul class="home-list">
    {%- for talk in site.data.notable_tweets %}
    <li>
      <a href="{{ talk.url }}">{{ talk.title }}</a>
      <span class="home-meta">{{ talk.event }}{% if talk.note %} &mdash; {{ talk.note }}{% endif %}</span>
    </li>
    {%- endfor %}
  </ul>
</div>
{% endif %}

<div class="home-section" id="writing" data-label="writing">
  <h2>Writing</h2>
  <p class="home-note">I write about AI research on Substack at <a href="https://techmuse2.substack.com">tech_muse</a>. <a href="https://techmuse2.substack.com/subscribe">Subscribe</a> for new posts.</p>
</div>

<div class="home-section" id="contact" data-label="contact">
  <h2>Contact</h2>
  <p>Find me on the platforms below, or read my writing on <a href="https://techmuse2.substack.com">Substack</a>.</p>
  <p class="home-social">{% include social.html %}</p>
</div>

<script>
  document.querySelectorAll('.project-filters button').forEach(function (btn) {
    btn.addEventListener('click', function () {
      var f = btn.dataset.filter;
      document.querySelectorAll('.project-filters button').forEach(function (b) { b.classList.toggle('active', b === btn); });
      document.querySelectorAll('.project-card').forEach(function (c) {
        c.hidden = f !== 'all' && c.dataset.domain !== f;
      });
    });
  });
</script>
