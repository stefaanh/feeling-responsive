---
#     __  __     __     ____       __          ____    __        ______                 __
#    / / / /__  / /_   / __ )___  / /__  ___  / __/___/ /__     / ____/__  ____  ____  / /_
#   / /_/ / _ \/ __/  / __  / _ \/ / _ \/ _ \/ /_/ __  / _ \   / / __/ _ \/ __ \/ __ \/ __/
#  / __  /  __/ /_   / /_/ /  __/ /  __/  __/ __/ /_/ /  __/  / /_/ /  __/ / / / /_/ / /_  
# /_/ /_/\___/\__/  /_____/\___/_/\___/\___/_/  \__,_/\___/   \____/\___/_/ /_/\____/\__/  
#                                                                       
# Use the widgets beneath and the content will be
# inserted automagically in the webpage. To make
# this work, you have to use › layout: frontpage
#
layout: frontpage
header:
  image_fullwidth: yoosun-won-6Lm3EcOXYGY-unsplash.jpg
  unsplash:
    name: Yoosun Won
    username: showkin9
widget3:
  include: "_widget_fav_boek.html"
widget2:
  include: "_widget_activiteit.html"
widget1:
  include: "_widget_uitstap.html"
#
# Use the call for action to show a button on the frontpage
#
# To make internal links, just use a permalink like this
# url: /getting-started/
#
# To style the button in different colors, use no value
# to use the main color or success, alert or secondary.
# To change colors see sass/_01_settings_colors.scss
#
callforaction:
  url: /info/lidmaatschap
  text: Lid worden of op de hoogte blijven is eenvoudig.
  style: alert
permalink: /index.html
#
# This is a nasty hack to make the navigation highlight
# this page as active in the topbar navigation
#
homepage: true
---
