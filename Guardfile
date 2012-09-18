# -*- coding: utf-8 -*-
# Coffeescriptの監視
guard 'coffeescript', :input => 'coffee', :output => 'dist/js', :bare => true

# SCSSの監視
guard :shell do
  # import以下が編集されたら、main.scssを更新したことにする
  watch(/^(.+\/)*.+(\.scss)$/) {
    |m|
		`sass --scss scss/main.scss dist/css/main.css`
  }
end

# その他のファイルの監視
guard :shell do
  watch(/^(.+\/)*.+(\.html)$/) {
    |m|
    dist = "dist/" + m[0]
        dir = `dirname #{dist}`
        `mkdir -p #{dir}`
    `cp #{m[0]} #{dist}`
    `growlnotify -m "copy #{m[0]} to #{dist}"`
  }
end
