
the server port is 50052 and client port is 50051

grpc-dump should forward client request from 50051 to 50052


```
grpc-dump --port=50051 --destination=localhost:50052 | jq .
```






python client get picky? in those 4 command, only the last one works (grpc_dump can dump the request/response)

```
✗ http_proxy=localhost:12345 python greeter_client.py
E0619 00:36:52.389945000 4728600000 http_proxy.cc:62]                  'localhost' scheme not supported in proxy URI
Greeter client received: Hello, you!
✗ HTTP_PROXY=localhost:12345 python greeter_client.py
Greeter client received: Hello, you!
✗ HTTP_PROXY=http://localhost:12345 python greeter_client.py
Greeter client received: Hello, you!


✗ http_proxy=http://localhost:12345 python greeter_client.py
Greeter client received: Hello, you!
```
