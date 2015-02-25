# Watir Cheat Sheet
##Starting up

To get started, create a browser and goto a URL!

```ruby
require 'watir'

browser = Watir::Browser.new :ff #firefox
browser.goto 'http://google.com'
```
##Finding Elements
###By tags
```ruby
#type element
browser.element #grab first element return type element
browser.element id: 'title' #grab element with id='title', return type element

#type tag
browser.text_field id: 'name' #grab text_field element with id='name', return type text_feild
browser.p #return type p etc..

#by CSS(must be element) Can be very powerful!
browser.css '.page-header h1' #'.class' '#id'
```

	