
the server port is 50052 and client port is 50051

grpc-dump should forward client request from 50051 to 50052

```
grpc-dump --port=50051 --destination=localhost:50052
```
