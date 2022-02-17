
## ` $ date `
<span style='color:#fff; font-family: Dejavu Sans Mono; font-size: 1.1em;'>- Path: /home/marcosranes/Desktop/Tutorials/Shopify</span>
```
Tue Jan  4 03:26:49 PM -03 2022
```
 
# How to create a custom section for your Shopify theme
 
## In order to have a section we need to deal with three things:
1. Add a new .json template with, for example, page.json and paste the following
```json
{
  "sections": {
    "main": {
      "type": "main-page",
      "settings": {
      }
    }
  },
  "order": [
    "main"
  ]
}
```
 
2. In the Sections directory, add a new .liquid section called main-page, as an exemple main-page.liquid pasting the following
```html
<link rel="stylesheet" href="{{ 'section-main-page.css' | asset_url }}" media="print" onload="this.media='all'">
<link rel="stylesheet" href="{{ 'component-rte.css' | asset_url }}" media="print" onload="this.media='all'">

<noscript>{{ 'section-main-page.css' | asset_url | stylesheet_tag }}</noscript>
<noscript>{{ 'component-rte.css' | asset_url | stylesheet_tag }}</noscript>

<div class="page-width page-width--narrow">
  <h1 class="main-page-title page-title h0">
    {{ page.title | escape }}
  </h1>
  <div class="rte">
    {{ page.content }}
  </div>
</div>

{% schema %}
{
  "name": "t:sections.main-page.name",
  "tag": "section",
  "class": "spaced-section"
}
{% endschema %}
```
It's enough to reach a deal between the two files.
  
3. After that a new file pages.liquid
```html
<link rel="stylesheet" href="{{ 'component-rte.css' | asset_url }}" media="print" onload="this.media='all'">
<link rel="stylesheet" href="{{ 'section-main-page.css' | asset_url }}" media="print" onload="this.media='all'">

<noscript>{{ 'component-rte.css' | asset_url | stylesheet_tag }}</noscript>
<noscript>{{ 'section-main-page.css' | asset_url | stylesheet_tag }}</noscript>

<div class="page-width page-width--narrow">
  <h2 class="page-title">
    {%- if section.settings.page.title != blank -%}
      {{ section.settings.page.title | escape }}
    {%- else -%}
      Page title
    {%- endif -%}
  </h2>
  <div class="rte">
    {%- if section.settings.page.content != blank -%}
      {{ section.settings.page.content }}
    {%- else -%}
      <div class='page-placeholder-wrapper placeholder'>
        {{ 'page' | placeholder_svg_tag: 'page-placeholder' }}
      </div>
    {%- endif -%}
  </div>
</div>

{% schema %}
{
  "name": "Pages-BUTTONS",
  "tag": "section",
  "class": "spaced-section",
  "settings": [
    {
      "type": "page",
      "id": "page",
      "label": "Pages-BUTTONS"
    }
  ],
  "presets": [
    {
      "name": "Pages-BUTTONS"
    }
  ]
}
{% endschema %}

```
