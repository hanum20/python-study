# Python - Simple Web Server

1. `index.html` 생성

   ```
   <html>
   <body>
     Hello my Simple Web Server!
   </body>
   </html>
   ```

2. `app.py` 생성 <- 확인 해보니, 안됨.. Python 3버전... 이런건 좀 사전에 적어달라고...

   ```
   import http.server
   import socketserver
   
   handler = http.server.SimpleHTTPRequestHandler
   
   with socketserver.TCPServer(('', 8080), handler) as httpd:
     print('Server listening on port 8080...')
     httpd.serve_forever()
   ```

   * 해당 파일 없으면 

3. 실행

   ```
   # python 버전 확인
   python -V
   
   # 2.x일 경우
   python -m SimpleHTTPServer
   
   # 3.x일 경우
   python -m http.server
   ```



결론

* 간단한 웹 서버를 구현해 봄
* index.html만 만들고 python 명령으로 서버를 시작하면, 명령이 실행된 디렉토리에서 index.html을 찾아서 바인딩 함.
* 해당 서버로 요청(http://ip-addr:8000)시 구현한 index.html을 리턴.

