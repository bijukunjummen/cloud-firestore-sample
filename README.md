# Chat Room/Messages sample using Firestore and Java

## Run locally

### Start Cloud Firestore emulator

```shell
gcloud components install cloud-firestore-emulator
gcloud beta emulators firestore start --host-port=:8662
```

### Start application

```shell
./gradlew bootRun
```
# Create chat rooms

```sh
curl -v -X POST  \
  -H "Content-type: application/json" \
  -H "Accept: application/json" \
   http://localhost:8080/chatrooms \
   -d '{
   "id": "some-room",
   "name": "some-room"
}'
```

# Get Chat Room

```sh
curl -v http://localhost:8080/chatrooms/some-room
```

# Get Messages from room

```sh
curl -v http://localhost:8080/messages/some-room
```

# Add a messsage to a room

```sh
curl -v -X POST \
  -H "Content-type: application/json" \
  -H "Accept: application/json" \
   http://localhost:8080/messages/some-room \
   -d '{
   "payload": "hello world"
}'
```
