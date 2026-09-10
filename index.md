---
layout: default
---
{% comment %}
Keep README as the book's single source. GitHub resolves its relative issue
links within the current repository; Pages needs that repository's full URL.
{% endcomment %}
{% capture book %}{% include_relative README.md %}{% endcapture %}
{% assign issues = site.github.repository_url | append: '/issues/' %}
{% assign github_files = site.github.repository_url | append: '/blob/' | append: site.github.source.branch | append: '/.github/' %}
{{ book | replace: '../../issues/', issues | replace: '.github/', github_files }}
