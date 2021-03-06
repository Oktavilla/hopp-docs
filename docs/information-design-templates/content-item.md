---
layout: default
title:  "Content Item Page"
nav_order: 3
parent: "Information Design Templates"
---

# Content Item Page
{: .no_toc }

There is one template for each [Content Variant](../data-models/content-item.md#content-variants). Exactly what fields and data that is available is defined by the [Content Type Schema](../data-models/content-item.md).

Besides content this page may also feature recirculation, [display ads](components-and-containers-ad.md), internal ads (static page teasers) and product services teasers (e.g for subscriptions).

1. TOC
{:toc}

----

## Context Label

A Content Item may have a set of "context labels" above the title. What these labels show depends on the [Product Configuration](../configuration/content-item-context-label-preferences.md) and the [Meta Data](../data-models/content-item.md#meta-data) of the Content Item.

<div class="example">
  <div class="example-context-label-group">
    <div class="example-context-label-part">
      <span class="example-context-label">Root Category {% include example-reference.html number="1" %}</span>
    </div>
    <div class="example-context-label-part">
      <span class="example-context-label">Category {% include example-reference.html number="2" %}</span>
    </div>
    <div class="example-context-label-part">
      <span class="example-context-label">Tag, Tag {% include example-reference.html number="3" %}</span>
    </div>
    <div class="example-context-label-part">
      <span class="example-context-label">Tag {% include example-reference.html number="3" %}</span>
    </div>
  </div>
  <div class="example-title">
    {% include example-title.html %}
  </div>
  <div class="example-body">
    {% include example-text.html %}
  </div>
</div>

The Content Item Root Category {% include example-reference.html number="1" %}and [Category](../data-models/category.md) {% include example-reference.html number="2" %} will always be shown as the first two labels unless exceptions are made in the [Product Configuration](../configuration/content-item-context-label-preferences.md). Showing the Root Category may be turned off and the  the current Category may be specifically exempt from being shown in context labels. The Root Category is never shown if the current Category is excluded. 

There may also be additonal labels {% include example-reference.html number="3" %} showing the most relevant tags of the Content Item. Both exemptions and additional labels are defined in the [Product Configuration](../configuration/content-item-context-label-preferences.md).

The platform determines what tags to show in additional labels {% include example-reference.html number="3" %} by looking at:   
A. The list of Tag Groups defined in the Context Label Product Configuration.  
B. Available tags on the Content Item.  
C. The maximum number of labels to show as defined in the Context Label Product Configuration.  

That data will be processed in this order:
1. The platform will look at the first group in (A).
2. We look for tags on the Content Item (B) that belong to that group. 
3. If no tag is matched we try the next group in (A) and try (2) again.
4. If one or more tags match we will show a label.
5. If the maximum number of labels (C) is reached we stop.
6. If we have run though all groups in (A) we stop.
7. We try the next group in (A) and try (2) again.

This will result in 0-(C) additional labels.

----

## Title

The title on the Content Item Page will always be based on the main Title field.
Promotion & Indexing Data will never be used in this context.

Title is prefixed with contributor if the content variant is ["Opinion Piece"](../data-models/content-type-article.html#content-variants), there is 1 contributor and ["Contributor In Opinion Piece Heading"](../configuration/content-item-preferences) configuration is set to true.

----

## Lead

The lead on the Content Item Page will always be based on the main Lead field.
Promotion & Indexing Data will never be used in this context.

----

## Timestamp

If a timestamp is shown on a content item is determined by preferences in the Product Configuration. 

{% include generic-rules/timestamp.md %}

----

## Sponsorship

When a content item has a relationship to one or several [brands](../data-models/brand.md) that is called a sponsorship.

<div class="example">
  <div class="example-sponsor">
    <div class="example-group-header">Sponsored by {% include example-reference.html number="1" %}</div>
    <div class="example-sponsor-brand">
      {% include example-image.html image_size="55" %}
    </div>
    <div class="example-sponsor-brand">
      {% include example-image.html image_size="55" %}
    </div>
    {% include example-reference.html number="2" fixed="true" %}
  </div>
  <div class="example-title">
    {% include example-title.html %}
  </div>
  <div class="example-body">
    {% include example-text.html %}
  </div>
</div>

* The list of sponsors will be clearly marked {% include example-reference.html number="1" %}.
* The sponsors is represented by their Brand Logos {% include example-reference.html number="2" %} and link to their [Brand Pages](brand.md).

----

## Byline

Content Items have a byline showing all [Contributors](../data-models/contributor.md). How these are rendered depends of the Content Type and Variant. 

* By default every contributor will be represented by their name, role and byline image. They will be linked to their [Contributor Page](contributor.md).
* Content Items of the [Opinion Piece](../data-models/content-type-article#content-variants) Article Variant will show a more prominent byline in the article header. These bylines will also default to using the Contributor Feature Image if available.

Feature Images and regular Byline Images are rendered a bit differently. See the [Byline Image Component](components-and-containers-byline-image.md) for more information. 

----

## Sharing

Every Content Item have "share buttons". These services are supported by default:

* Facebook
* Twitter
* E-mail

----

## Meta Data Tags

### Social Media

The Content Item Templates come with dedicated social media meta data tags that guarantees great presentation on social media platforms. 
The content of these tags will be derived from the [Promotion Data](../data-models/content-item.md#promotion--indexing-data). If none, or only partial, promotion data is present the platform will use the following fallbacks:

* **Title**  
  The platform will use Promotion Title or fallback to the Content Items Title.
* **Description**  
  The platform will use Promotion Text or fallback to the Content Items Lead.
* **Image**  
  The platform will use Promotion Image or fallback to the main image of the Content Item. 
  What the main image is will vary depending on the Content Type.

### Search Engines

The Content Item Templates come with dedicated search engine meta data tags that guarantees the content will be indexed correctly and presented well in search engines. The content of these tags will be derived from the appropriate fields of the Content Item:

* **Title**  
  The platform will use the [Indexing Title](../data-models/content-item.md#promotion--indexing-data) if present. Otherwise it will fallback to the Content Items Title.
* **Description**  
  The platform will use the Content Items Lead.
* **Content Language**  
  The platform will use the Content Items Language.

----

## Recirculation

There are two "areas" for recirculation on content items. 

### Inline recirculation

There may be a [Curated Content Mix](../configuration/curated-content-mix.md#recirculation-mix-inside-article-content-items) configured to be shown inside the Content Item Body. It will be rendered after block six on Articles and below the body on Content Item Types that lack a body with content blocks or has less than 7 blocks in total.

### Below content recirculation

A [Curated Content Mix](../configuration/curated-content-mix.md#recirculation-content-mix) can be configured to be shown underneath the body of the Content Item. There can be [different Content Mixes](../configuration/curated-content-mix.md#recirculation-content-mix-for-specific-categories) and different Layouts for different Content Items depending on in what Category they're published.

----

## Ads

See [display ads](components-and-containers-ad.md).

