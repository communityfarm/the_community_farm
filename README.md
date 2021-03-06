# TheCommunityFarm

This RubyGem provides a way to access the contents of various veg boxes from [The Community Farm](https://www.thecommunityfarm.co.uk/) in your Ruby programs. I use it to generate an XML feed of the various boxes which I can then plug into an IFTTT recipe which emails me when the weekly box contents is updated.

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'the_community_farm'
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install the_community_farm

## Usage

```ruby
require 'the_community_farm'
require 'open-uri'

organic_boxes = TheCommunityFarm::OrganicBoxes.new(html: open('https://www.thecommunityfarm.co.uk/boxes/box_display.php').read)

organic_boxes.each do |box|
  puts box
  puts
  box.items.each { |item| puts "- #{item}" }
  puts
end
```

Which will output:

```
All For One

- Potatoes (Valor) (Somerset)
- Carrots (Dirty) (Somerset)
- Cauliflower (Green) (Somerset)
- Cabbage (Pointed) (Cornwall)
- Leeks (Our Field)
- Sweetcorn (Somerset)
- Chillies (Our Field)

Family Provider Large

- Potatoes (Valor) (Somerset)
- Carrots (Dirty) (Somerset)
- Parsnips (Somerset)
- Cauliflower (Green) (Somerset)
- Brussel Sprout Tops (Somerset)
- Cabbage (White) (Our Field)
- Butternut Squash (Somerset)
- Leeks (our field)
- Sweetcorn (Somerset)
- Beetroot (Somerset)
- Apples  (Hereford)
- Bananas (Ecuador)
- Oranges (SPA)

Family Provider Small

- Potatoes (Valor) (Somerset)
- Carrots (Dirty) (Somerset)
- Parsnips (Somerset)
- Cauliflower (Green) (Somerset)
- Leeks (our field)
- Sweetcorn (Somerset)
- Onions (Somerset)
- Chard (Rainbow) (Our Field)
- Chillies (Our field)
- Apples (Hereford)
- Bananas (Ecuador)
- Oranges (SPA)

[snip]
```

## Development

After checking out the repo, run `bin/setup` to install dependencies. Then, run `rake test` to run the tests. You can also run `bin/console` for an interactive prompt that will allow you to experiment.

To install this gem onto your local machine, run `bundle exec rake install`. To release a new version, update the version number in `version.rb`, and then run `bundle exec rake release`, which will create a git tag for the version, push git commits and tags, and push the `.gem` file to [rubygems.org](https://rubygems.org).

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/communityfarm/the_community_farm.

## License

The gem is available as open source under the terms of the [MIT License](http://opensource.org/licenses/MIT).
