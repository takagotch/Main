### Main
---
https://github.com/ahoward/main

```
gem install main
main.rb

```

```ruby
require 'main'
Main {
  mode 'install' do
    def run() 'installing...' end
  end
  mode 'uninstall' do
    def run() puts 'uninstalling...' end
  end
}


require 'main'
Main {
  argument('foo'){
    cast :int
  }
  keyword('bar'){
    arity 2
    cast :float
    defaults 0.0, 1.0
  }
  option('foobar'){
    argument :optional
    description 'the foobar option is very handy'
  }
  environment('BARFOO'){
    cast :list_of_bool
    synosis 'export barfoo=value'
  }
  def run
    p params['foo'].value
    p params['bar'].values
    p params['foobar'].value
    p params['BARFOO'].value
  end
}

```

```
```
