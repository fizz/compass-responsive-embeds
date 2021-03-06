# Compass Responsive Embeds

This extension helps embedding videos and iframes in responsive designs.

It provides a `responsive-embed` mixin to apply on an element containing an embed, to scale it while keeping its ratio.

See the blogs posts from [Anders M. Andersen](http://amobil.se/2011/11/responsive-embeds/) and [A List Apart](http://www.alistapart.com/articles/creating-intrinsic-ratios-for-video/) for more information.

## Installation

Add this line to your application's Gemfile:

    gem 'compass-responsive-embeds'

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install compass-responsive-embeds

Add to a project:

    // rails: compass.config, other: config.rb
    require 'compass-responsive-embeds'

    // command line
    compass install compass-responsive-embeds

## Usage

In your html template:

    <div class="embed-16-9">
      <iframe src="http://www.youtube.com/embed/J---aiyznGQ" frameborder="0" allowfullscreen></iframe>
    </div>
    <div class="embed-4-3">
      <script async class="speakerdeck-embed" data-id="4eb80921b029470054011d3f" data-ratio="1.3333333333333333" src="//speakerdeck.com/assets/embed.js"></script>
    </div>

In your stylesheet:

    @import 'compass-responsive-embeds';

    // 16/9 embed
    .embed-16-9 {
      @include responsive-embed(16/9);
    }

    // 4/3 embed
    .embed-4-3 {
      @include responsive-embed(4/3);
    }

    // default 1 ratio for a square embed
    @embed-1-1 {
      @include responsive-embed;
    }

You can use any ratio, as long as the result can be converted to percentages.

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request

