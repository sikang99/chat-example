# chat-example
chatting examples using websockets (gorilla & base), written in go


### History
- 2019/07/10 [Building a live chat with Go, NATS, Redis and Websockets](https://www.ribice.ba/goch/)
- 2019/03/14 [Go Websocket Tutorial](https://tutorialedge.net/golang/go-websocket-tutorial/)
- [How to Use Websockets in Golang: Best Tools and Step-by-Step Guide](https://yalantis.com/blog/how-to-build-websockets-in-go/)
- 2017/08/02 [**A Million WebSockets and Go**](https://www.freecodecamp.org/news/million-websockets-and-go-cc58418460bb/)
- 2016/12/20 [Build a Realtime Chat Server With Go and WebSockets](https://scotch.io/bar-talk/build-a-realtime-chat-server-with-go-and-websockets)


### Information
- [Go Web Examples](https://gowebexamples.com/): [Websockets](https://gowebexamples.com/websockets/)
- [WebSocket을 이용하여 클라이언트 애플리케이션 작성하기](https://developer.mozilla.org/ko/docs/WebSockets/Writing_WebSocket_client_applications)
- [Golang과 websocket을 활용한 서버 프로그래밍 (장애 없는 서버 런칭 도전기)](https://aidanbae.github.io/gallery/golang-meetup/])
- [golang과 websocket을 활용한 서버프로그래밍 - 장애없는 서버 런칭 도전기](https://www.slideshare.net/SangikBae/golang-websocket-109095156)
- [simple websocket example with golang](http://bl.ocks.org/tmichel/7390690)



### Open Source (Product)
- [gorilla/websocket](https://github.com/gorilla/websocket) - A fast, well-tested and widely used WebSocket implementation for Go.
    - [chat example](https://github.com/gorilla/websocket/tree/master/examples/chat)
- [**LockGit/gochat**](https://github.com/LockGit/gochat) - goim, online chat, im server write by golang
- [**tinode/chat**](https://github.com/tinode/chat) - Instant messaging server; backend in Go; iOS, Android, web, command line clients; chatbots
- [oikomi/FishChatServer](https://github.com/oikomi/FishChatServer) - FishChatServer
- [oikomi/FishChatServer2](https://github.com/oikomi/FishChatServer2) - FishChatServer2
- [coyim/coyim](https://github.com/coyim/coyim) - coyim - a safe and secure chat client, XMPP
- [**keybase/client**](https://github.com/keybase/client) - Keybase Go Library, Client, Service, OS X, iOS, Android, Electron
- [knadh/niltalk](https://github.com/knadh/niltalk) - A multi-room disposable chat service written in Go that uses WebSockets for live communication


### Open Source (Examples)
- [stinkyfingers/chat](https://github.com/stinkyfingers/chat) - A simple chat application example in Go using WebSocket
- [waylau/goChat](https://github.com/waylau/goChat) - Golang chat.This example application shows how to use WebSockets
- [tyrchen/chatroom](https://github.com/tyrchen/chatroom) - very simple chatroom for learning goroutine and channel
- [domluna/websocket-golang-chat](https://github.com/domluna/websocket-golang-chat) - Simple chat using golang and websockets
- [campoy/chat](https://github.com/campoy/chat) - A good demonstration of Go composition of types and processes.


### Open Source (WebSockets Examples)
- [aidanbae/websocket-example](https://github.com/aidanbae/websocket-example) - 2018, 7월 고랭 코리아 밋업 발표자료


### Changelogs
- 2020/02/26 : niltalk working
    - redis docker problem : connection error
- 2020/02/25 : test some more examples
    - change `code.google.com/p/go.net/websocket` into `golang/go/x/websocket`
    - use port=4000 in all examples
- 2020/02/24 : start to coding with a [chat example](https://github.com/gorilla/websocket/files/465536/chat1.zip)
