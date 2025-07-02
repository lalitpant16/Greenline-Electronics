1. Header and Footer

HTML and Css are changed for header and footer
Js is written to open and close menu on hover

-----------------+-------------------+--------------------+----------------------------+------------------------+----------------

2. Product Image Carousel

Purpose: Enhance the product page with a Swiper-powered image carousel, replacing Dawn's default gallery.

Files Used

snippets/custom-product-media-gallery.liquid: Renders product media and initializes Swiper

Theme Setting

Section: main-product.liquid

Setting: Enable Media Swiper (boolean)

If enabled: renders custom Swiper gallery

If disabled: falls back to Dawn’s native layout

Key Features

Swipe and thumbnail navigation

Zoom functionality

Responsive design (1–4 thumbnails)

Installation

{%- if section.settings.enable_media_swiper -%}
  {% render 'custom-product-media-gallery', product: product %}
{%- else -%}
  {% section 'product-media' %}
{%- endif -%}

Dependencies

{{ 'https://cdn.jsdelivr.net/npm/swiper@11/swiper-bundle.min.css' | stylesheet_tag }}
{{ 'https://cdn.jsdelivr.net/npm/swiper@11/swiper-bundle.min.js' | script_tag }}

-----------------+-------------------+--------------------+----------------------------+------------------------+----------------

3. Customer Reviews Section

PurposeDisplay product-specific reviews using a metafield.

Metafield Details

Namespace: custom

Key: customer_reviews

Type: List (Single line text)

Format: Name##Review text##Rating

Example: Lalit##This is an awesome product##5

Notes: Rating (1–5) is rendered as filled stars

Section: sections/product-customer-reviews.liquid

Supports responsive margin settings

-----------------+-------------------+--------------------+----------------------------+------------------------+----------------

4. “You May Also Like” Section

PurposeDisplay manually selected product recommendations using a metafield.

Metafield Details

Namespace: custom

Key: you_may_also_like_products

Type: List (Product reference)

Implementation

Section: sections/you-may-also-like.liquid

Uses default product-card snippet (supports swatches, badges, quick add)

-----------------+-------------------+--------------------+----------------------------+------------------------+----------------

5. Free‑Shipping Progress Bar

PurposeShow visual progress toward a free-shipping threshold in the cart drawer.

File Used

snippets/progress-bar.liquid: Structure & styles only

Theme Setting

Theme Settings → Cart Drawer → Free-shipping threshold (numeric)

Functionality

A JS function updateFreeShippingProgress() should:

Recalculate bar width on item add/remove

Run on quantity update or cart refresh

-----------------+-------------------+--------------------+----------------------------+------------------------+----------------

6. Custom Discount Field

PurposeProvide a clean coupon input inside the cart drawer with instant feedback and validation.

Key Features

Inline discount input field

Apply button with loading/disabled states

Success/error messages

Updates cart drawer on apply

Implementation Notes

Snippet: snippets/cart-drawer-discount.liquid


-----------------+-------------------+--------------------+----------------------------+------------------------+----------------


Faced some issues on discount section on the cart drawer, where the cart was not updating at the time of applying the coupon code, i took help from various docs, AI Tools like chat GPT.


-----------------+-------------------+--------------------+----------------------------+------------------------+----------------



