# ResolvFiber

Resolv is a thread-aware DNS resolver library written in Ruby.  Resolv can
handle multiple DNS requests concurrently without blocking the entire Ruby
interpreter.

ResolvFiber is a fiber which wraps this DNS resolution.

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'resolv_fiber'
```

And then execute:

    $ bundle install

Or install it yourself as:

    $ gem install resolv

## Usage


```ruby
fiber = ::ResolvFiber.getaddresses_fiber(hostname)
while fiber.alive?
  result = fiber.resume
end

puts result
```

## Development

After checking out the repo, run `bin/setup` to install dependencies. Then, run `rake test` to run the tests. You can also run `bin/console` for an interactive prompt that will allow you to experiment.

To install this gem onto your local machine, run `bundle exec rake install`. To release a new version, update the version number in `version.rb`, and then run `bundle exec rake release`, which will create a git tag for the version, push git commits and tags, and push the `.gem` file to [rubygems.org](https://rubygems.org).

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/kudop/resolv_fiber.

