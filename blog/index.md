---
layout: default
title: Blog
permalink: /blog/
---

<style>
.blog-hero {
    background: linear-gradient(135deg, #f8fafc 0%, #ffffff 100%);
}
.post-card {
    transition: all 0.3s ease;
    border: 1px solid #e5e7eb;
}
.post-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
    border-color: #FF6B00;
}
.category-tag {
    display: inline-block;
    padding: 0.25rem 0.75rem;
    background-color: #f1f5f9;
    color: #64748B;
    border-radius: 9999px;
    font-size: 0.875rem;
    font-weight: 500;
    transition: all 0.2s ease;
    text-decoration: none;
}
.category-tag:hover {
    background-color: #FF6B00;
    color: white;
    text-decoration: none;
}
.featured-post {
    background: linear-gradient(135deg, #FF6B00 0%, #ff8c42 100%);
    color: white;
    border-radius: 1rem;
}
.rounded-2xl {
    border-radius: 1rem;
}
.shadow-xl {
    box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.1), 0 10px 10px -5px rgba(0, 0, 0, 0.04);
}
@media (max-width: 768px) {
    .featured-post {
        padding: 2rem 1.5rem !important;
    }
    .featured-post h2 {
        font-size: 2rem !important;
    }
}
</style>

<!-- Blog Hero Section -->
<section class="blog-hero py-20 px-6">
    <div class="max-w-6xl mx-auto text-center">
        <h1 class="text-6xl md:text-7xl font-black mb-6 tracking-tighter leading-none">
            <span class="logo-text-orange">Blog</span>
        </h1>
        <p class="text-slate text-xl max-w-2xl mx-auto leading-relaxed font-light">
            Insights on cloud architecture, AI security, MLOps, and infrastructure automation.
        </p>
    </div>
</section>

<!-- Categories Navigation -->
<section class="py-8 px-6 bg-white border-b border-gray-200">
    <div class="max-w-6xl mx-auto">
        <div class="flex flex-wrap justify-center gap-4">
            <a href="/blog/" class="category-tag {% unless page.category %}bg-orange text-white{% endunless %}">All Articles</a>
            <a href="/blog/#automation" class="category-tag">Automation</a>
            <a href="/blog/#productivity" class="category-tag">Productivity</a>
            <a href="/blog/#business" class="category-tag">Business Growth</a>
            <a href="/blog/#platform" class="category-tag">Platform & Product</a>
            <a href="/blog/#security" class="category-tag">Security</a>
            <a href="/blog/#cloud" class="category-tag">Cloud Architecture</a>
        </div>
    </div>
</section>

<!-- Featured Article (if available) -->
{% assign featured_post = site.posts.first %}
{% if featured_post %}
<section class="py-16 px-6">
    <div class="max-w-6xl mx-auto">
        <div class="featured-post rounded-2xl p-12 shadow-xl">
            <div class="max-w-3xl">
                <div class="mb-4">
                    {% for category in featured_post.categories limit: 1 %}
                    <span class="inline-block px-4 py-1 bg-white bg-opacity-20 text-white rounded-full text-sm font-medium mb-4">
                        {{ category }}
                    </span>
                    {% endfor %}
                </div>
                <h2 class="text-4xl md:text-5xl font-black mb-4 leading-tight">
                    <a href="{{ featured_post.url }}" class="text-white hover:opacity-90 transition">
                        {{ featured_post.title }}
                    </a>
                </h2>
                {% if featured_post.excerpt %}
                <p class="text-white text-lg mb-6 opacity-90 leading-relaxed">
                    {{ featured_post.excerpt | strip_html | truncatewords: 30 }}
                </p>
                {% endif %}
                <div class="flex items-center justify-between">
                    <div class="flex items-center space-x-4 text-white opacity-90">
                        <time datetime="{{ featured_post.date | date_to_xmlschema }}" class="text-base">
                            {{ featured_post.date | date: "%B %d, %Y" }}
                        </time>
                    </div>
                    <a href="{{ featured_post.url }}" 
                       class="px-6 py-3 bg-white text-orange-600 font-bold rounded-lg hover:bg-gray-100 transition shadow-lg">
                        Read Article →
                    </a>
                </div>
            </div>
        </div>
    </div>
</section>
{% endif %}

<!-- All Blog Posts Grid -->
<section class="py-16 px-6 bg-gray-50">
    <div class="max-w-6xl mx-auto">
        <h2 class="text-4xl font-black text-gray-800 mb-12 text-center">Latest Articles</h2>
        
        {% if site.posts.size > 0 %}
        <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
            {% for post in site.posts %}
            <article class="post-card bg-white rounded-lg p-6" style="display: flex; flex-direction: column; height: 100%;">
                <div style="flex: 1; display: flex; flex-direction: column;">
                    <div class="mb-4">
                        {% if post.categories %}
                            {% for category in post.categories limit: 1 %}
                            <span class="category-tag">{{ category }}</span>
                            {% endfor %}
                        {% endif %}
                    </div>
                    
                    <h3 class="text-2xl font-bold text-gray-800 mb-3 leading-tight">
                        <a href="{{ post.url }}" class="hover:text-orange-600 transition">
                            {{ post.title }}
                        </a>
                    </h3>
                    
                    {% if post.excerpt %}
                    <p class="text-slate mb-4 leading-relaxed" style="flex: 1;">
                        {{ post.excerpt | strip_html | truncatewords: 20 }}
                    </p>
                    {% endif %}
                </div>
                
                <div class="flex items-center justify-between pt-4 border-t border-gray-100">
                    <time datetime="{{ post.date | date_to_xmlschema }}" class="text-sm text-slate">
                        {{ post.date | date: "%B %d, %Y" }}
                    </time>
                    <a href="{{ post.url }}" class="text-orange-600 font-medium text-sm hover:text-orange-700">
                        Read more →
                    </a>
                </div>
            </article>
            {% endfor %}
        </div>
        {% else %}
        <div class="text-center py-16">
            <p class="text-slate text-lg mb-6">No blog posts yet. Check back soon!</p>
            <a href="/#contact" class="bg-orange px-6 py-3 rounded text-white hover:bg-orange-600 transition shadow-md inline-block">
                Contact Us
            </a>
        </div>
        {% endif %}
    </div>
</section>

<!-- Newsletter CTA Section (Zapier-style) -->
<section class="py-16 px-6 bg-white">
    <div class="max-w-3xl mx-auto text-center">
        <h2 class="text-3xl font-black text-gray-800 mb-4">Stay Updated</h2>
        <p class="text-slate mb-8 text-lg">
            Get the latest insights on cloud architecture, AI security, and automation delivered to your inbox.
        </p>
        <a href="/#contact" class="bg-orange px-8 py-4 rounded-lg text-white font-bold hover:bg-orange-600 transition shadow-lg inline-block">
            Get in Touch
        </a>
    </div>
</section>