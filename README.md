[![Code Climate](https://codeclimate.com/github/IcaliaLabs/sepomex-rb/badges/gpa.svg)](https://codeclimate.com/github/IcaliaLabs/sepomex-rb)
[![Test Coverage](https://codeclimate.com/github/IcaliaLabs/sepomex-rb/badges/coverage.svg)](https://codeclimate.com/github/IcaliaLabs/sepomex-rb/coverage)
[![Issue Count](https://codeclimate.com/github/IcaliaLabs/sepomex-rb/badges/issue_count.svg)](https://codeclimate.com/github/IcaliaLabs/sepomex-rb)

# Sepomex-rb

A super simple Ruby wrapper to consume the Sepomex API at [http://sepomex-api.herokuapp.com/api/v1/zip_codes](http://sepomex-api.herokuapp.com/api/v1/zip_codes)

## Table of contents
- [Quick start](#quick-start)
- [Usage](#usage)
- [Bug tracker & feature request](#bug-tracker-&-feature-request) 
- [Development](#development)
- [Contributing](#contributing)
- [Heroes](#heroes)
- [License](#license)

## Quick Start

Add this line to your application's Gemfile:

```ruby
gem 'sepomex'
```

And then execute:

```console
% bundle
```

Or install it yourself as:

```
% gem install sepomex
```

## Usage

```ruby
zip_codes = Sepomex::ZipCode.where

=> #<Sepomex::ZipCode id=53, d_codigo="01184", d_asenta="Nelli Campo Bello", d_tipo_asenta="Unidad habi...
```

You can specify the page to request as an option on the method.

```ruby
zip_codes = Sepomex::ZipCode.where(page: 2)

=> #<Sepomex::ZipCode id=53, d_codigo="01184", d_asenta="Nelli Campo Bello", d_tipo_asenta="Unidad habi...
```

You can also filter by code:

```ruby
zip_codes = Sepomex::ZipCode.where(page: 2, cp: "67173")

=> #<Sepomex::Collection:0x007fcb9bab50e0 @total_pages=1, @total_objects=8, @per_page=50, @collection=[#<Sepomex::ZipCode id=89510, d_codigo="67173", d_asenta="Contry los Nogales", d_tipo_asenta="Colonia", d_mnpio="Guadalupe", d_estado="Nuevo León", d_ciudad="Guadalupe", d_cp="67171", c_estado="19", c_oficina="67171", c_cp="", c_tipo_asenta="09", c_mnpio="026", id_asenta_cpcons="1725", d_zona="Urbano", c_cve_ciudad="04">...
```

Filtering by State

```ruby
nuevo_leon_zipcodes = Sepomex::ZipCode.where(state: "Nuevo León")

=> #<Sepomex::ZipCode id=85801, d_codigo="64000", d_asenta="La Finca", d_tipo_asenta="Colonia", d_mnpio="Monterrey", d_estado="Nuevo León", d_ciudad="Monterrey", d_cp="64008", c_estado="19", c_oficina="64008", c_cp="", c_tipo_asenta="09", c_mnpio="039", id_asenta_cpcons="3429", d_zona="Urbano", c_cve_ciudad="07">, #<Sepomex::ZipCode id=85802, d_codigo="64000", d_asenta="Monterrey Centro", d_tipo_asenta="Colonia", d_mnpio="Monterrey", d_estado="Nuevo León", d_ciudad="Monterrey", d_cp="64008", c_estado="19", c_oficina="64008", c_cp="", c_tipo_asenta="09", c_mnpio="039", id_asenta_cpcons="0001", d_zona="Urbano", c_cve_ciudad="07">...
```

Filtering by Colony

```ruby

colony_zip_codes = Sepomex::ZipCode.where(colony: "Prados de la Sierra")

=>#<Sepomex::ZipCode id=87890, d_codigo="66230", d_asenta="Prados de La Sierra", d_tipo_asenta="Colonia", d_mnpio="San Pedro Garza García", d_estado="Nuevo León", d_ciudad="San Pedro Garza García", d_cp="66231", c_estado="19", c_oficina="66231", c_cp="", c_tipo_asenta="09", c_mnpio="019", id_asenta_cpcons="0887", d_zona="Urbano", c_cve_ciudad="02">
```

Filtering by City

``ruby

city_zip_codes = Sepomex::Zipcode.where(city: "Monterrey")

=> #<Sepomex::ZipCode id=85801, d_codigo="64000", d_asenta="La Finca", d_tipo_asenta="Colonia", d_mnpio="Monterrey", d_estado="Nuevo León", d_ciudad="Monterrey", d_cp="64008", c_estado="19", c_oficina="64008", c_cp="", c_tipo_asenta="09", c_mnpio="039", id_asenta_cpcons="3429", d_zona="Urbano", c_cve_ciudad="07">...
```

## Bug tracker & feature request

Have a bug or a feature request? [Please open a new issue](https://github.com/IcaliaLabs/sepomex-rb/issues). Before opening any issue, please search for existing issues.


## Development

After checking out the repo, run `bin/setup` to install dependencies. Then, run `bin/console` for an interactive prompt that will allow you to experiment.

To install this gem onto your local machine, run `bundle exec rake install`. To release a new version, update the version number in `version.rb`, and then run `bundle exec rake release` to create a git tag for the version, push git commits and tags, and push the `.gem` file to [rubygems.org](https://rubygems.org).

## Contributing

1. Fork it ( https://github.com/[my-github-username]/sepomex/fork )
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create a new Pull Request

## Heroes

**Abraham Kuri**

+ [http://twitter.com/kurenn](http://twitter.com/kurenn)
+ [http://github.com/kurenn](http://github.com/kurenn)
+ [http://klout.com/#/kurenn](http://klout.com/#/kurenn)

**Oscar Elizondo**

+ [http://twitter.com/oehinojosa](http://twitter.com/oehinojosa)
+ [http://github.com/oelizondo](http://github.com/oelizondo)


## Copyright and license

Code and documentation copyright 2015 Icalia Labs. Code released under [the MIT license](LICENSE).
