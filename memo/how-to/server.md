- server: 簡易的なWebサーバーを起動させる方法
```bash
# ruby
ruby -rwebrick -e 'WEBrick::HTTPServer.new({:DocumentRoot => "./"}).start'

# python
python3 -m http.server 8000
```
