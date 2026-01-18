---
layout: default
title: Blog
permalink: /blog/
---

<style>
:root {
    --brand-orange: #FF6B00;
    --brand-gray: #64748B;
    --bg-light: #FFFFFF;
    --text-dark: #0F172A;
}

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body { 
    background-color: var(--bg-light); 
    color: var(--text-dark); 
    font-family: 'Inter', sans-serif; 
    scroll-behavior: smooth; 
    line-height: 1.6;
}

.logo-text-orange { color: var(--brand-orange); }
.text-slate { color: var(--brand-gray); }
.bg-orange { background-color: var(--brand-orange); }

/* Utility Classes */
.max-w-6xl { max-width: 72rem; margin-left: auto; margin-right: auto; }
.max-w-3xl { max-width: 48rem; margin-left: auto; margin-right: auto; }
.max-w-4xl { max-width: 56rem; margin-left: auto; margin-right: auto; }
.mx-auto { margin-left: auto; margin-right: auto; }
.px-6 { padding-left: 1.5rem; padding-right: 1.5rem; }
.py-20 { padding-top: 5rem; padding-bottom: 5rem; }
.py-16 { padding-top: 4rem; padding-bottom: 4rem; }
.py-12 { padding-top: 3rem; padding-bottom: 3rem; }
.py-8 { padding-top: 2rem; padding-bottom: 2rem; }
.pt-20 { padding-top: 5rem; }
.mb-12 { margin-bottom: 3rem; }
.mb-6 { margin-bottom: 1.5rem; }
.mb-4 { margin-bottom: 1rem; }
.mb-3 { margin-bottom: 0.75rem; }
.text-center { text-align: center; }

/* Blog Styles */
.blog-hero {
    background: linear-gradient(135deg, #f8fafc 0%, #ffffff 100%);
}

.post-card {
    transition: all 0.3s ease;
    border: 1px solid #e5e7eb;
    height: 100%;
    display: flex;
    flex-direction: column;
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

.rounded { border-radius: 0.25rem; }
.rounded-lg { border-radius: 0.5rem; }
.rounded-2xl { border-radius: 1rem; }

.shadow-xl {
    box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.1), 0 10px 10px -5px rgba(0, 0, 0, 0.04);
}

.shadow-md {
    box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -2px rgba(0, 0, 0, 0.1);
}

.shadow-lg {
    box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -4px rgba(0, 0, 0, 0.1);
}

/* Grid Layout */
.grid {
    display: grid;
    gap: 2rem;
}

@media (min-width: 768px) {
    .md\:grid-cols-2 { grid-template-columns: repeat(2, 1fr); }
}

@media (min-width: 1024px) {
    .lg\:grid-cols-3 { grid-template-columns: repeat(3, 1fr); }
}

/* Post Card Content */
.post-card-content {
    flex: 1;
    display: flex;
    flex-direction: column;
}

.post-card-footer {
    margin-top: auto;
    padding-top: 1rem;
    border-top: 1px solid #e5e7eb;
}

/* Typography */
h1 { font-size: 3.75rem; font-weight: 900; line-height: 1; letter-spacing: -0.05em; }
h2 { font-size: 2.25rem; font-weight: 900; }
h3 { font-size: 1.5rem; font-weight: 700; line-height: 1.3; }

@media (min-width: 768px) {
    h1 { font-size: 6rem; }
    .featured-post h2 { font-size: 3rem; }
    .md\:text-7xl { font-size: 6rem; }
    .md\:text-5xl { font-size: 3rem; }
}

@media (max-width: 768px) {
    .featured-post { padding: 2rem 1.5rem !important; }
    .featured-post h2 { font-size: 2rem !important; }
    h1 { font-size: 3rem; }
}

a {
    color: inherit;
    text-decoration: none;
    transition: color 0.2s;
}

.text-orange-600 { color: var(--brand-orange); }
.hover\:text-orange-600:hover { color: var(--brand-orange); }
.hover\:text-orange-700:hover { color: #ea580c; }

.bg-white { background-color: white; }
.bg-gray-50 { background-color: #f9fafb; }

.text-gray-800 { color: #1f2937; }
.text-sm { font-size: 0.875rem; }
.text-base { font-size: 1rem; }
.text-lg { font-size: 1.125rem; line-height: 1.75; }
.text-xl { font-size: 1.25rem; line-height: 1.75; }
.font-bold { font-weight: 700; }
.font-medium { font-weight: 500; }
.font-light { font-weight: 300; }
.font-black { font-weight: 900; }

.leading-relaxed { line-height: 1.625; }
.leading-tight { line-height: 1.25; }
.leading-none { line-height: 1; }
.tracking-tighter { letter-spacing: -0.05em; }

.flex { display: flex; }
.items-center { align-items: center; }
.justify-center { justify-content: center; }
.justify-between { justify-content: space-between; }
.gap-4 { gap: 1rem; }
.gap-8 { gap: 2rem; }
.gap-2 { gap: 0.5rem; }
.space-x-3 > * + * { margin-left: 0.75rem; }
.space-x-4 > * + * { margin-left: 1rem; }
.space-x-8 > * + * { margin-left: 2rem; }

.flex-wrap { flex-wrap: wrap; }

.border-t { border-top-width: 1px; }
.border-b { border-bottom-width: 1px; }
.border-gray-100 { border-color: #f3f4f6; }
.border-gray-200 { border-color: #e5e7eb; }

.p-6 { padding: 1.5rem; }
.p-12 { padding: 3rem; }
.px-4 { padding-left: 1rem; padding-right: 1rem; }
.px-6 { padding-left: 1.5rem; padding-right: 1.5rem; }
.px-8 { padding-left: 2rem; padding-right: 2rem; }
.py-1 { padding-top: 0.25rem; padding-bottom: 0.25rem; }
.py-2 { padding-top: 0.5rem; padding-bottom: 0.5rem; }
.py-3 { padding-top: 0.75rem; padding-bottom: 0.75rem; }
.py-4 { padding-top: 1rem; padding-bottom: 1rem; }

.mt-6 { margin-top: 1.5rem; }
.inline-block { display: inline-block; }
.inline-flex { display: inline-flex; }

.bg-opacity-20 { background-color: rgba(255, 255, 255, 0.2); }
.opacity-90 { opacity: 0.9; }

.rounded-full { border-radius: 9999px; }

.transition { transition-property: color, background-color, border-color, text-decoration-color, fill, stroke, opacity, box-shadow, transform; transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1); transition-duration: 150ms; }

.hover\:opacity-90:hover { opacity: 0.9; }
.hover\:bg-gray-100:hover { background-color: #f3f4f6; }
.hover\:bg-orange-600:hover { background-color: #ea580c; }
.hover\:text-orange-500:hover { color: #f97316; }

/* Additional text sizes */
.text-2xl { font-size: 1.5rem; line-height: 2rem; }
.text-3xl { font-size: 1.875rem; line-height: 2.25rem; }
.text-4xl { font-size: 2.25rem; line-height: 2.5rem; }
.text-5xl { font-size: 3rem; line-height: 1; }
.text-6xl { font-size: 3.75rem; line-height: 1; }

/* Max width utilities */
.max-w-2xl { max-width: 42rem; margin-left: auto; margin-right: auto; }

/* Additional utility classes */
.hidden { display: none; }

@media (min-width: 768px) {
    .md\:flex { display: flex; }
    .md\:text-7xl { font-size: 6rem; line-height: 1; }
}

.text-white { color: white; }
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