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

# bootswatch反映のサンプル

## bootswatchからthemeファイルを落としてくる

https://bootswatch.com/

Ceruleanを使う

```
$ wget https://bootswatch.com/cerulean/variables.less
$ wget https://bootswatch.com/cerulean/bootswatch.less
$ mv variables.less bootswatch.less app/assets/stylesheets/
```

## application.cssのrequire_treeを違うディレクトリにする
自動で読み込まれると読み込む順番の関係でエラーになってしまうため、assets pipelineのrequire_treeの対象を移動する

```
$ mkdir app/asserts/stylesheets/autoload
$ mv app/asserts/stylesheets/* app/asserts/stylesheets/autoload
$ vi app/asserts/stylesheets/application.css
--- application.css
- *= require_tree .
+ *= require_tree ./autoload
---
```

## bootswatchを読み込むようにする

```
$ vi app/asserts/stylesheets/bootstrap_and_overrides.css.less
--- bootstrap_and_overrides.css.less
+ @import "cerulean/bootswatch";
+ @import "cerulean/variables";
---
```
