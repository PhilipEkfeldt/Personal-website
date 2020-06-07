---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Dark Matter and Stellar Stream Detection"
subtitle: "Capstone Project"
summary: ""
authors: ["admin", "Tony Xu", "Brian Kelly", "Ademola Oladosu"]
tags: ["physics", "machine learning"]
categories: ["physics", "machine learning"]
commentable: false
date: 2019-12-13T23:14:10-04:00

# Optional external URL for project (replaces project detail page).
#external_link: ""

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: "center"
  preview_only: false

# Custom links (optional).
#   Uncomment and edit lines below to show custom links.
# links:
# - name: Follow
#   url: https://twitter.com
#   icon_pack: fab
#   icon: twitter

url_code: ""
url_pdf: "/pdfs/capstone_2019/Report.pdf"
url_poster: "/pdfs/capstone_2019/Poster.pdf"
url_slides: ""
url_video: ""

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides: ""
---
Stellar stream and dark matter detection are active areas of research in astrophysics. Historically, this detection has been a manual process and has led to the discovery
of stellar streams such as GD-1 and Palomar 5. If astrophysicists initially have strong confidence that certain stars are part of a stellar stream, probabilistic methods
may determine the likelihood that an adjacent star also belongs to the same stellar stream. Using machine learning methods, we seek to develop an automated process
that finds additional stars that are part of the stellar stream. After initially trying standardized classification methods, we establish an ensemble of a subset of kNN
methods (ESkNN) as an effective means of classifying stars from simulated streams and real streams. Since these methods generally fail to capture non-linearities in the
data, we also use a feedforward neural network approach that we expected to help capture non-linear properties. Our evaluation metric for these two metrics is the F1
score. The best model produced by ESkNN method had an F1 score of 0.75, when evaluated on GD-1 stars. The deep learning method (DeepSets) achieved an F1
score of 0.66. While both approaches can be tuned to prefer precision or recall, the ESkNN tends towards highly precise results (99%) whereas the DeepSets method
tends towards results with high recall. We also attempt a metric learning approach that could help uncover a distance learning metric that is an improvement upon Euclidean distance.