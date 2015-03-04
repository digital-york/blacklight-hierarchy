source "https://rubygems.org"

# Declare gem dependencies in blacklight-hierarchy-facets.gemspec.
gemspec

# Declare any dependencies that are still in development here instead of in
# your gemspec. These might include edge Rails or gems from your path or
# Git. Remember to move these dependencies to your gemspec before releasing
# your gem to rubygems.org.

# load local rails test instance Gemfile (engine cart adds this automagically)
file = File.expand_path("Gemfile", ENV['ENGINE_CART_DESTINATION'] || ENV['RAILS_ROOT'] || File.expand_path("../spec/internal", __FILE__))
if File.exists?(file)
  puts "Loading #{file} ..." if $DEBUG # `ruby -d` or `bundle -v`
  instance_eval File.read(file)
else
  gem 'rails', ENV['RAILS_VERSION']
  # explicitly include sass-rails to get compatible sprocket dependencies
  if ENV['RAILS_VERSION'] and ENV['RAILS_VERSION'] =~ /^4.2/
    gem 'sass-rails', ">= 5.0.0.beta1"
  else
    gem 'sass-rails', "< 5.0"
  end
end
