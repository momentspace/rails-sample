# slim-railsのサンプル

## erbからslimに変換する

```
for i in app/views/**/*.erb; do bundle exec erb2slim $i ${i%erb}slim && rm $i; done
  remove app/views/layouts/application.html.erb? y
  remove app/views/layouts/mailer.html.erb? y
  remove app/views/layouts/mailer.text.erb? y
```

