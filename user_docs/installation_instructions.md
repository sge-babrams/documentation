## Installation

### Gems

Installing via gem is the preferred method it one exists.

**Standard Installation**

`gem install sensu-plugin-disk-checks`

**Secure Installation**

Add the public key (if you haven’t already) as a trusted certificate

```
gem cert --add <(curl -Ls https://raw.githubusercontent.com/sensu-plugins/sensu-plugins.github.io/master/certs/sensu-plugins.pem)
gem install sensu-plugins-disk-checks -P MediumSecurity
```

You can also download the key from certs/ within each repository.

**Note:**
If the gem has an alpha tag then you will need to use the *--prerelease* flag or the gem will not be found.

#### Bundler

Add *sensu-plugins-disk-checks* to your Gemfile and run `bundle install` or `bundle update`

#### Chef

Using the Sensu **sensu_gem** LWRP
```
sensu_gem 'sensu-plugins-disk-checks' do
  options('--prerelease') # only needed if it is in an alpha state
  version '0.0.1.alpha.1'
end
```

Using the Chef **gem_package** resource
```
gem_package 'sensu-plugins-disk-checks' do
  options('--prerelease') # only needed if it is in an alpha state
  version '0.0.1.alpha.1'
end
```

## Usage

In a proper gem environment plugins can be executed directly from the command line. If you want to check the disk usage you could use the **check-disk-usage** plugin.  This will only work for ruby scripts.  Scripts in other langauges will still need to be called directly do to binstubs not being automatically created.

`check-disk-usage.rb -w 80 -c 90`

Depending on ruby environment you may need to call ruby directly

`/opt/sensu/embedded/bin/ruby check-disk-usage.rb -w 80 -c 90`

For details check the header file of a given plugin.
