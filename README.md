# SimpleSlug

[![Build Status](https://travis-ci.org/leschenko/simple_slug.png?branch=master)](https://travis-ci.org/leschenko/simple_slug)
[![Dependency Status](https://gemnasium.com/leschenko/simple_slug.png)](https://gemnasium.com/leschenko/simple_slug)

Simple friendly url generator for ActiveRecord models with history.

## Installation

Add this line to your application's Gemfile:

    gem 'simple_slug'

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install simple_slug

## Usage

Add basic slugs to your model:

```ruby
class User < ActiveRecord::Base
  simple_slug :full_name
end
```

Or with custom slug column and history:

```ruby
class User < ActiveRecord::Base
  simple_slug :full_name, slug_column: 'my_slug_column', history: true
end
```

If you want to control when slug is generated, define `should_generate_new_slug?` method:

```ruby
class User < ActiveRecord::Base
  simple_slug :full_name

  def should_generate_new_slug?
    true
  end
end
```

## Contributing

1. Fork it ( http://github.com/leschenko/simple_slug/fork )
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
