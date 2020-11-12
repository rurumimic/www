# History

## HTTP/0.9

- HTTP/0.9는 나중에 붙여진 버전이다.
- GET 메소드만 있다.
- 헤더가 없다.
- HTML 파일만 전송된다.
- 상태와 오류 코드도 없다.

```
GET /mypage.html
```

```html
<HTML>
A very simple HTML page
</HTML>
```

## HTTP/1.0

- Header (option)
- Response codes
- Redirects
- Erros
- Conditional requests
- Encoding
- Compression
- Request methods

### First request

```
GET /mypage.html HTTP/1.0
User-Agent: NCSA_Mosaic/2.0 (Windows 3.1)
```

```html
200 OK
Date: Tue, 15 Nov 1994 08:12:31 GMT
Server: CERN/3.0 libwww/2.17
Content-Type: text/html
<HTML> 
  A page with an image
  <IMG SRC="/myimage.gif">
</HTML>
```

### Second Request

```
GET /myimage.gif HTTP/1.0
User-Agent: NCSA_Mosaic/2.0 (Windows 3.1)
```

```
200 OK
Date: Tue, 15 Nov 1994 08:12:32 GMT
Server: CERN/3.0 libwww/2.17
Content-Type: text/gif
(image content)
```

## HTTP/1.1

- Header
  - Host: virtual hosting 가능
  - Upgrade
  - cacheability
- 커넥션 재사용
- OPTIONS 메소드
- Range 요청
- Transfer-Encoding 압축
- Pipelining: 클라이언트는 모든 요청을 동시에 전송
  - 서버는 순서대로 응답해야 함
    - Head Of Line blocking: 요청이 오래 걸려 다른 요청들도 지연됨
  - 파이프라이닝을 제대로 구현한 서버와 프락시가 부족하거나 동작하지 않음

## 진화

### 보안

- SSL 1.0: 넷스케이프 커뮤니케이션에서 만듦
- SSL 2.0, 3.0, 3.1: e-커머스 웹 사이트 토대
- TLS 1.0, 1.1, 1.2
- TLS 1.3 개발 중

### 복잡한 애플리케이션

- WebDAV
- CardDAV
- CalDAV
- REST: REpresentational State Transfer
- Server-sent events
- WebSocket

### 보안 모델 완화

- same-origin
- Cross-Origin Resource Sharing
- Content Security Policy
