module BundlerHack
    def __materialize__
      if name == 'grpc' || name == 'google-protobuf'
        Bundler.settings.temporary(force_ruby_platform: true) do
          super
        end
      else
        super
      end
    end
  end
  Bundler::LazySpecification.prepend(BundlerHack)
source 'https://rubygems.org'
# gem 'http_parser.rb', git: "git@github.com:tmm1/http_parser.rb.git"
group :jekyll_plugins do
    gem 'jekyll'
    gem 'jekyll-archives'
    gem 'jekyll-diagrams'
    gem 'jekyll-email-protect'
    gem 'jekyll-feed'
    gem 'jekyll-github-metadata'
    gem 'jekyll-paginate-v2'
    gem 'jekyll-responsive-image'
    gem 'jekyll-scholar'
    gem 'jekyll-sitemap'
    gem 'jekyll-target-blank'
    gem 'jekyll-twitter-plugin'
    gem 'jemoji'
    gem 'unicode_utils'
    gem 'webrick'
    gem 'wdm', '>= 0.1.0' if Gem.win_platform?
end
