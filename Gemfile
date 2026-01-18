source "https://rubygems.org"

gem "jekyll", "~> 4.3"
gem "jekyll-feed", "~> 0.12"
gem "jekyll-seo-tag", "~> 2.8"

# Windows does not include zoneinfo files, so bundle the tzinfo-data gem
# and associated library.
platforms :windows do
  gem "tzinfo", ">= 1", "< 3"
  gem "tzinfo-data"
end

# Note: 
# - wdm gem removed due to Ruby 3.4 compatibility issues
# - google-protobuf is a transitive dependency (from sass-embedded via jekyll-sass-converter)
#   Since we don't use SCSS/SASS files (using plain CSS instead), Jekyll won't process SASS
#   and the dependency loading issue only affects local Windows testing, not GitHub Pages
