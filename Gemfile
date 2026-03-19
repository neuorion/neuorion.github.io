source "https://rubygems.org"

# Use github-pages gem so local build matches GitHub Pages (Jekyll 3.x) and
# avoids sass-embedded/google-protobuf issues on Windows.
gem "github-pages", group: :jekyll_plugins

# Ruby 3+ removed webrick from stdlib; required for `jekyll serve`
gem "webrick"

# Windows: zoneinfo and tzinfo for correct time handling
platforms :windows do
  gem "tzinfo", ">= 1", "< 3"
  gem "tzinfo-data"
end
