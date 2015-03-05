# Watir Cheat Sheet
##Starting up

To get started, create a browser and goto a URL!

```ruby
require 'watir'

browser = Watir::Browser.new :ff #firefox
browser.goto 'http://google.com'

browser.refresh
browser.quit
browser.back
```
##Finding Elements
```ruby
#Type Element
browser.element #grab first element return type element
browser.element id: 'title' #grab element with id='title', return type element

#Type Tag
browser.text_field id: 'name' #grab text_field element with id='name', return type text_feild
browser.p #return type p etc..

#By CSS(must be element) Can be very powerful!
browser.element(css: '.page-header h1') #'.class' '#id'

#Type Table
browser.table[0][0] #row#cell

#Type Link
browser.link href "/writing/articles"
browser.link text: 'About'

#Type Iframe
browser.iframe(id: "omnibarDD").link(href: "/personal/login/login").click

#Array
browser.ps #plural will grab array of element of all p's in this case
```
#Waitings
##Selenium Wait
```ruby
browser.driver.manager.timeouts.implicit_wait = 3 #wait 3 seconds
```
##Explicit Wait
```ruby
browser.select_list(id: 'blah').wait_until_present
browser.text_field(id: 'blash').when_present.set('hellowworld') #allows you to chain
browser.button(value: 'Submit').wait_while_present #useful for loading icons
```
#Iteractions
```ruby
element.set 'Hello World' #send keys
element.send_keys 'Hello World'

element.html #returns html as string
element.text #shows text as string
element.value #shows value as string

element.button(name: 'login').click

browser.checkbox(:value 'checkbox1').set #tick checkbox
browser.checkbox(:value 'checkbox1').clear #clear checkbox and textfiels
browser.checkbox(:value 'checkbox1').checked? # checks if checked

browser.select_list(id: 'list').select 'option1'
browser.select_list(id: 'list').clear
puts browser.select_list(id: 'list').options #list all options

browser.radio(value: 'radio1').set
browser.radio(value: 'radio1').clear
```
