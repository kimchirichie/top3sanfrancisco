---
layout: default
---

<section class="hero mb-5">
  <div class="hero-inner">
    <h1>{{ site.title }}</h1>
    <h2>{{ site.description }}</h2>
  </div>
</section>

<main class="container">
  <div class="row mb-5">
    <div class="col-12 col-md-4">
      <img
        src="{{ '/assets/images/landing/profile.jpg' | relative_url }}"
        alt="Rick Sin"
        class="border border-light rounded-circle"
      >
      
    </div>
    <div class="col">
      <h2>I'm Rick</h2>
      <p>I blog about the most interesting places in San Francisco,<br> so you can enjoy San Francisco as locals do.</p>        
      <p>When I first explored San Francisco, I did not have any real idea about what San Francisco was like, and how to explore it in the short time I had. This blog is for those out there, who have no idea what its like to be in San Francisco, but need that local knowledge.</p>
      <p>Maybe you are moving here and trying to find which neighborhood to move to. Perhaps you're looking for the best boba places in town. This blog is going to answer all of those questions. If you cant find the answer, shoot me an <a href="mailto:kimchirichie@gmail.com">email</a></p>        
    </div>
  </div>
  <div class="row">
    <div class="col">
      {%- if site.posts.size > 0 -%}
        <h2>{{ page.list_title | default: "My Latest Blog Posts" }}</h2>
        <div class="card-columns">
          {%- for post in site.posts -%}

            <div class="card">
              <a class="post-link" href="{{ post.url | relative_url }}">
                {%- if post.splash -%}
                  <img class="card-img-top" src="{{ post.splash | relative_url }}" />
                {%- endif -%}
                <div class="card-body">
                  <h5>{{ post.title | escape }}</h5>
                  {%- if site.show_excerpts -%}
                    {{ post.excerpt }}
                  {%- endif -%}
                </div>
              </a>
              <div class="card-footer">
                <span class="text-muted"><i class="fas fa-tags"></i>&nbsp;
                  {%- for tag in post.tags -%}
                    <span class="badge badge-pill badge-secondary">{{ tag }}</span>&nbsp;
                  {%- endfor -%}
                </span><br>
                {%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%}
                <span class="text-muted"><i class="far fa-calendar-alt"></i>&nbsp;{{ post.date | date: date_format }}</span><br>
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
  </div>
</main>