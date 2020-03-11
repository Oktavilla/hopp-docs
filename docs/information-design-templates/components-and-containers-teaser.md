---
layout: default
title:  "Teaser"
parent: "Components & Containers"
grand_parent: "Information Design Templates"
---

# Teaser

All [content items](../data-models/content-item.md) on the platform comes with a teaser that can promote it in different ways. Teasers are typically shown in [lists](part-list.md) on the start, category-, tag, contributor- or brand pages in order to internally promote content. Teasers can also be shown inline in content areas or in the recirculation section below content items.

## Teaser Content

A Content Item may have [specific teaser data](../data-models/content-item.md#teaser-data). If none, or only partial, teaser data are present the platform will use the following fallbacks:

* **What if there's no image?**  
  In this case the platform will fallback to the main image of the Content Item. 
  What the main image is will vary depending on the Content Type.
* **What if there's no text?**  
  In this case the platform will fallback to the Content Items Lead.
* **What if there's no heading?**  
  In this case the platform will fallback to the Content Items Title.

## Teaser Presentation

Teasers will display information differently depending on: 
* What type of content it promotes (defined by its [content variant](../data-models/content-item.html#content-variants) and [content type](../data-models/content-item.html)). For video content the platform may show a teaser with a video play button and for a long read article there may be a larger, more engaging, image in the teaser.
* The context it is presented in (see [containers](part-container.md) and [lists](part-list.md))
* [Content Item Display Preferences](../configuration/#content-item-display-preferences) 

## Internal Ad

Internal Ads are used throughout the site for the purpose of informing users about current offers, events etc. An internal ad is simply a teaser for a static page.