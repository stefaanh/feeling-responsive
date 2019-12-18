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
  image_fullwidth: yifei-chen-575975-unsplash.jpg
  #  caption: 'Foto door YIFEI CHEN op Unsplash'

widget1:
  title: "Activiteiten"
  url: '/activiteiten'
  image: activiteiten-curtis-macnewton-317636-unsplash.jpg
  text: 'Lezingen zijn een van de kernactiviteiten van Het Beleefde Genot. Lees meer over onze uitgangspunten op onze Info pagina.'
widget2:
  title: "Eerstkomend: over Orhan Pamuk"
  image: onderwerp/orhan-pamuk.jpg
  url: '/activiteit/eenzaamheid-is-bedreigend'
  text: '<em>Eenzaamheid is bedreigend.</em> In zijn romans behandelt hij vooral de tegenstellingen Oost-West, Islam-Christendom en zeker traditie-moderniteit. - ‘Wij zijn onszelf, en dat is al complex genoeg...'
widget3:
  title: "Een nieuw jaar"
  url: '/aankondiging/licht-en-ideeen-in-2019/'
  image: sharon-mccutcheon-576867-unsplash.jpg
  text: '<em>Licht & ideeën in 2019!</em><br/>
Allereerst onze beste wensen voor het nieuwe jaar! Zoals u intussen al gemerkt hebt is 2019 een goed gestoffeerd jaar. Lees verder'
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
