---
layout: default
---

<div>
  {%- if page.title -%}
    <h1 class="page-heading">{{ page.title }}</h1>
  {%- endif -%}

  {{ content }}

  {%- if site.posts.size > 0 -%}

    <h2 class="post-list-heading">{{ page.list_title | default: "Posts" }}</h2>

    <div class="card-columns">

      {%- for post in site.posts -%}
        <div class="card">

          <a class="post-link" href="{{ post.url | relative_url }}">

            {%- if post.splash -%}
              <img class="card-img-top" src="{{ post.splash | relative_url }}" />
            {%- endif -%}
            
            <div class="card-body">
              <h3>
                  {{ post.title | escape }}
              </h3>
              {%- if site.show_excerpts -%}
                {{ post.excerpt }}
              {%- endif -%}
            </div>

          </a>
          
          <div class="card-footer">
            {%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%}
            <span class="text-muted">{{ post.date | date: date_format }}</span>          
          </div>

        </div>
      {%- endfor -%}

    </div>

    <p class="feed-subscribe">
      <a href="{{ 'feed.xml' | relative_url }}">
        <svg class="svg-icon orange"><use xlink:href="{{ 'assets/minima-social-icons.svg#rss' | relative_url }}"></use></svg><span>Subscribe</span>
      </a>
    </p>
  {%- endif -%}

</div>