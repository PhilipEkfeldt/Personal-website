---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Bird's Eye View Layout Prediction"
subtitle: "Final Project - NYU Deep Learning DS GA 1008"
summary: ""
authors: ["admin", "Marina Zavalina", "Shreyas Chandrakaladharan"]
tags: ["machine learning", "computer vision"]
categories: ["machine learning", "computer vision"]
date: 2020-05-11T00:40:59-04:00
commentable: false
# Optional external URL for project (replaces project detail page).
#external_link: "https://github.com/mmarinated/ssl_project"

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false

# Custom links (optional).
#   Uncomment and edit lines below to show custom links.
# links:
# - name: Follow
#   url: https://twitter.com
#   icon_pack: fab
#   icon: twitter

url_code: "https://github.com/mmarinated/ssl_project"
url_pdf: "/pdfs/DL_project/Report.pdf"
url_slides: ""
url_video: "https://www.youtube.com/watch?v=h6EQ-l9OZIc&t=1s"

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides: ""
---

In this project we focus on Bird's Eye View (BEV) prediction based on monocular photos taken by the cameras on top of the car. We present a Maximum Mean Discrepancy Variational Auto Encoder (MMD VAE) model to predict the BEV road layout. We also contribute an approach combining Image Warping, U-Net and Post-processing to predict the bounding boxes (BB) on the BEV layout. Our models achieve **0.81 test threat score on the road layout prediction task and 0.072 test threat score on the BB prediction task**. Animations below visualize the predictions of our final models.

### Video: 

{{< youtube h6EQ-l9OZIc >}}
