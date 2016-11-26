# slim-railsのサンプル

## erbからslimに変換する

```
$ for i in app/views/**/*.erb; do bundle exec erb2slim $i ${i%erb}slim && rm $i; done
  remove app/views/layouts/application.html.erb? y
  remove app/views/layouts/mailer.html.erb? y
  remove app/views/layouts/mailer.text.erb? y
```


# twitter-bootstrap-railsのサンプル

## bootstrap-railsのインストール

```
$ rails g bootstrap:install
```

## therubyracerを有効にする
--- Gemfile
gem 'therubyracer'

$ bundle install

## bootstrapを反映

```
$ rails g bootstrap:install less
$ rails g bootstrap:layout application fluid
$ rails g bootstrap:themed posts -f
```

