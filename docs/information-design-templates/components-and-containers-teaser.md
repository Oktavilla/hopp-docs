---
layout: default
title:  "Teaser"
parent: "Components & Containers"
grand_parent: "Information Design Templates"
---

# Teaser
{: .no_toc }

All [content items](../data-models/content-item.md) on the platform comes with a teaser that can promote it in different ways. Teasers are typically shown in lists on the start, category-, tag, contributor- or brand pages in order to internally promote content. Teasers can also be shown inline in content areas or in the recirculation section below content items. A Content Item may have [specific promotion data](../data-models/content-item.md#promotion--indexing-data).

1. TOC
{:toc}

----

## Heading
The platform will use the Promotion Title or fallback to the Content Item Title.

Heading is prefixed with contributor if the content variant is ["Opinion Piece"](../data-models/content-type-article.html#content-variants), there is 1 contributor and ["Contributor In Opinion Piece Heading"](../configuration/content-item-preferences) configuration is set to true.

----

## Image
The platform will use the Promotion Image or fallback to the main image of the Content Item.

----

## Text
The platform will use the Promotion Text or fallback to a short version of the Content Item Lead.

If no Promotion Text is available, the Content Item Lead is sliced after the last word within 80 character. If the text isn't a complete sentence after slicing (e.g. ends with ".", "!" or "?"), the text is suffixed with "…".

----

## Bylines

A standard Teaser byline consists of only the Contributor Name. Although a byline in an Opinion-piece Article Teaser will show both the Name and the Feature Image (falls back to the standard Byline Image) of the Contributor unless there's more than one Contributor. In that case only the Names will be shown. See the [Byline Image Component](components-and-containers-byline-image.md) for more information.  

However, *the default is to not show a byline in teasers*. There's a few situations where it should be shown though:
* For Opinion-piece Article Teasers the default is to show a byline
* Showing bylines might be enabled in the [Product Configuration](../configuration/content-item-teaser-preferences.md) on a Content Variant basis.

----

## Timestamp
Depending on the Product Configuration a timestamp may be shown or not. 

{% include generic-rules/timestamp.md %}

----

## Context Label

Teasers have one (1) context label. The label will display the text of the first item in the list of [Context Labels on Content Item Pages](content-item.md#context-label). It can be a category or a tag.

----

## Sponsors

If one or several brands are related to the Content Item the sponsorship will be clearly marked and the Brands will be represented by their logotypes.

----

## Teaser Presentation

Teasers will display information differently depending on: 
* What type of content it promotes (defined by its [content variant](../data-models/content-item.html#content-variants) and [content type](../data-models/content-item.html)). For video content the platform may show a teaser with a video play button and for a long read article there may be a larger, more engaging, image in the teaser.
* The context it is presented in (see [lists](components-and-containers-list.md))
* [Content Item Display Preferences](../configuration/general-product-preferences.md) 

----

## Internal Ad

Internal Ads are used throughout the site for the purpose of informing users about current offers, events etc. An 
internal ad is simply a teaser for a static page.

