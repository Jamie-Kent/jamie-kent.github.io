---
layout: default
title: Home
---

<div class="text-center mb-16">
  <h1 class="text-5xl font-bold mb-4">{{ site.title }}</h1>
  <p class="text-xl text-gray-600 max-w-2xl mx-auto">{{ site.description }}</p>
</div>

<div class="grid md:grid-cols-2 gap-8 mb-16">
  <!-- Recent Posts -->
  <div class="bg-white border border-gray-200 rounded-lg p-8">
    <h2 class="text-2xl font-bold mb-4">Recent Posts</h2>
    <ul class="space-y-4">
      {% for post in site.posts limit:5 %}
      <li>
        <a href="{{ post.url | relative_url }}" class="text-blue-600 hover:text-blue-800 font-medium">
          {{ post.title }}
        </a>
        <p class="text-sm text-gray-600">{{ post.date | date: "%B %-d, %Y" }}</p>
      </li>
      {% endfor %}
    </ul>
    <a href="/blog" class="inline-block mt-6 text-blue-600 hover:text-blue-800 font-medium">
      View all posts →
    </a>
  </div>
  
  <!-- Categories -->
  <div class="bg-white border border-gray-200 rounded-lg p-8">
    <h2 class="text-2xl font-bold mb-4">Topics</h2>
    <div class="flex flex-wrap gap-2">
      {% assign sorted_categories = site.categories | sort %}
      {% for category in sorted_categories %}
      <a href="/blog#{{ category[0] }}" 
         class="px-3 py-1 bg-blue-100 text-blue-800 rounded hover:bg-blue-200">
        {{ category[0] }} ({{ category[1].size }})
      </a>
      {% endfor %}
    </div>
  </div>
</div>