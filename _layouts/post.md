---
layout: default
comments: true
---

<main class="page-content" aria-label="Content">
  <div class="container">
    <div class="row">
      <div class="col-md-8">
        <article class="post h-entry" itemscope itemtype="http://schema.org/BlogPosting">

          <header class="post-header">
            {%- if page.splash -%}
              <img class="post-splash w-100" src="{{ page.splash | relative_url }}" />
            {%- endif -%}
            <h1 class="post-title p-name" itemprop="name headline">{{ page.title | escape }}</h1>
            <p class="post-meta">
              <time class="dt-published" datetime="{{ page.date | date_to_xmlschema }}" itemprop="datePublished">
                {%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%}
                {{ page.date | date: date_format }}
              </time>
              {%- if page.author -%}
                • <span itemprop="author" itemscope itemtype="http://schema.org/Person"><span class="p-author h-card" itemprop="name">{{ page.author | escape }}</span></span>
              {%- endif -%}</p>
          </header>

          <div class="post-content e-content" itemprop="articleBody">
            {{ content }}
          </div>

          {%- if site.disqus.shortname -%}
            {%- include disqus_comments.html -%}
          {%- endif -%}

          <a class="u-url" href="{{ page.url | relative_url }}" hidden></a>
        </article>
      </div>
      <div class="col-md-4">
        
      </div>
    </div>
  </div>
</main>