### link_thumbnailer
---
https://github.com/gottfrois/link_thumbnailer

```
gem 'link_thumbnailer'
bundle
gem install link_thumbnailer
rails g link_thumbnailer:install

```

```ruby
require 'link_thumbnailer'

object = LinkThumbnailer.generate('http://stackoverflow.com')
object.title
object.favicon
object.description
object.images.first.src.to_s

object.to_json

# config/initializers/link_thumbnailer.rb
LinkThumbnailer.configure do |config|
  # config.redirect_limit = 3
  # config.user_agent = 'link_thumbnailer'
  # config.verify_ssl = true
  # config.http_open_timeout = 5
  # config.blacklist_urls = [
  #   %r{^http://ad\.doubleclick\.net/},
  #   %r{^http://b\.socrecardresearch\.com/},
  #   %r{^http://pixel\.quantserve\.com/},
  #   %r{^http://s7\.addthis\.com/}
  # ]
  # config.atributes = [:title, :images, :description, :videos, :favicon]
  # config.graders = [
  #   ->(description){ ::LinkThumbnailer::Graders::Length.new(description) },
  #   ->(description){ ::LinkThumbnailer::Graders::HtmlAttribute.new(description, :class) },
  #   ->(description){ ::LinkThumbnailer::Graders::HtmlAttribute.new(description, :id) },
  #   ->(description){ ::LinkThumbnailer::Graders::Position.new(description, wight: 3) },
  #   ->(description){ ::LinkThumbnailer::Graders::LinkDensity.new(description) },
  # ]
  # config.description_min_length = 25
  # config.positive_regex /article|body|content|entry|hentry|main|page|pagination|post|text|blog|stroy/i
  # config.negative_regex = /cinbx|cinnebt|com-|contact|foot|footer|footnote|masthead|media|meta|outbrain|promo|related|scroll|shoutbox|sidebar|sponsor|shopping|tags|rool|widget|modal/i
  # config.image_limit = 5
  # config.image_stats = true
  # config.raise_on_invalid_format = false
  # config.max_concurrency = 20
  # config.encoding = 'utf-8'
end


object = LinkThumbnailer.generate('http://stackoberflow.com', redirect_limit: 5, user_agent: 'foo')

begin
  LinkThumbnailer.generate('http://foo.com')
rescue LinkThumbnailer::Exceptions => e
end

```

```
```
