autoscale: true

# [fit] *Crash Course*

# [fit] Ruby on Rails

![fit filtered](suncoast.png)

---

# [fit] Gavin Stark

## [fit] Instructor - Suncoast Developers Guild

## [fit] Co Organizer of The Tampa Ruby Brigade

---

# [fit] Riley

![left original 45%](riley.png)

---

# [fit] Tampa Ruby Brigade

## [fit] > 10 Years Old

-

## meetup.com/tamparb

![fit filtered](tamparuby.jpg)

---

# [fit] Suncoast <br> Developers <br> Guild

-
-
-
-

## suncoast.io

![left fit filtered](suncoast-logo.png)

^ A collective of software engineers and programmers in the Tampa Bay Area.

^ Our purpose is to promote a sense of community among local technology organizations and their members

---

![stretch](rails-logo.png)

---

# About the Web

- HTML pages delivered to your browser
- Delivered via HTTP/TLS protocol
- JavaScript/CSS/image and other assets
- Cookies
- Links followed and forms submitted
- Recently: websockets

---

# HTTP protocol

- Basis for everything we do on the web
- *(H)yper(t)ext (T)ransport (P)rotocol*
- Tim Berners-Lee at CERN in 1989
- _(now Sir Tim Berners-Lee)_
- Yes, you can be knighted for inventing a protocol

---

# Who uses Rails anyway?

- 500px
- Airbnb
- Dribble
- Funny or Die
- Genius (Rap Genius)
- GitHub

---

# Who uses Rails anyway?

- Goodreads
- Groupon
- LivingSocial
- Hulu
- Kickstarter
- Shopify
- Square
- Urban Dictionary

---

# Brief history of Rails

- _David Heinemeier Hansson_ contracted to build Basecamp
- Convinced 37 Signals to allow him to code it in `Ruby`
- **Extracted** from that code base

---

![fit](linux-magazine.jpg)

---

# Opinionated Software

- Convention over Configuration
- Don't Repeat Yourself
- Testing built-in
- Environments built in (dev, test, prod)
- Database migrations

^ Lets just skip over the "bikeshedding" that typically happens
^ DRY: Every piece of knowledge must have a single, unambiguous, authoritative representation within a system
^ Testing built in means that it is more likely to happen
^ Default, smart, tries to be secure-by-default defaults for development, test, and production
^ Migrations: How do we keep track of the changing state of the database over time. As we change code
^             we also change the database, migrations keeps these in sync.

---

# Application patterns

- Everything in a familiar place
- ActiveRecord
- Extends Ruby
- DSL

^ Every Rails app follows a common folder structure
^ Any Rails app you pick up will feel familiar
^ ActiveRecord allows us to think about our data in objects instead of piles of SQL statements
^ Rails extends Ruby with new features, several of which have been brought back to Ruby itself
^ "Domain Specific Langauge" - using a programming language's syntax to allow programmers to
^                              author code in a way that feels familiar to the domain (business,
^                              type of problem, etc.)

---

-
-
-

## Dynamic Data on the Web

![fit](sql-right-in-html.jpg)

---

# Dynamic Data on the Web

```xml
<cfoutput>
  <cfquery name="myQuery" datasource="#myDatabase#">
    SELECT name, balance FROM accounts where status = 'active'
  </cfquery>
  <cfloop query="myQuery">
    #name# - #balance# <br/>
  </cfloop>
</cfoutput>
```

---

# ActiveRecord

- Based on the “Active Record” pattern
- Defines objects around database records
- Defines query interfaces
- Defines relationships between objects (tables)

---

# ActiveRecord

- Typically used to map tables to objects
- Determines attributes by reflection
- Base class exposes creating, find, update, delete API

---

# ActiveRecord

```ruby
class Account < ActiveRecord::Base
  has_many :transfers
  belongs_to :customer

  scope :active -> { where(status: "active") }

  def available_to_withdraw
    balance - pending
  end
end
```

---

# Database Migrations


---

```ruby
class CreateBooks < ActiveRecord::Migration
  def change
    create_table :books do |t|
      t.string :title
      t.string :author_name
      t.datetime :date_published

      t.timestamps null: false
    end
  end
end
```

---

# Testing

- Built into framework, generates test files for generated models, controllers.
- Can generate tests for:
  - Models
  - Controllers
  - Integration
  - e-mail

---

# [fit] Let's make an app

---

# But first...

- Installing Rails isn't as easy as it should be
- especially on Windows … _(Rails Installer)_
- Others:
  - ruby-install
  - rvm
  - homebrew (mac)
  - third party repo with an up-to-date ruby (2.4 or later)
- Fortunately, we can use a cloud based environment for this course

---

# Code Anywhere

- Login to `codeanywhere.com`
- Register for free account
- Click: *Create a new project*

---

# Code Anywhere

- Enter a projct name (`Food Truck`)
- Open Project
- Choose `git from URL`
- Enter this as the URL:
  - `https://github.com/suncoast-devs/food-truck.git`
- Enter a container name ('Food Truck')
- Type `ruby` into "Search Stack"
- Choose the `ruby` entry that mentions `Ubuntu` in the last column

---

# [fit] Lets code!!

---

# Cheat sheet:

-
-
-

# [fit] `https://gist.github.com/gstark/4818d620286dbccb0d0f`

or (shorter URL)

# [fit] `http://bit.ly/2GjwjIn`

---

