# Capybara Cheat Sheet
##Starting up

To get started, create a browser and goto a URL!

```ruby
require 'capybara'
session = Capybara::Session.new :selenium

session.visit 'http://lacedeamon.spartaglobal.com/example_forms'
```
##Filling Forms
```ruby
ession.fill_in 'name', with: 'Jimmy' #textfields
session.choose('Choice 1') #radio
session.select('Choice 2', from: 'select-choice') #dropdownlist
session.fill_in 'textarea', with: 'test text for testing text'

session.check 'checkbox' #checkbox
session.click_button 'Submit'
```

	