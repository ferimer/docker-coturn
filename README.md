# CoTURN container

Based on: https://meetrix.io/blog/webrtc/turnserver/long_term_cred.html

Changes: Uses alpine instead Ubuntu

## Execute

docker run --name coturn -e TURN_SECRET=mysecret -e TURN_SERVER_NAME=coturn -e TURN_REALM=mydomain.tld -e TURN_PORT_END=10100 -p 3478:3478 -p 10000-10100:10000-10100 -d ferimer/coturn

## Generate test users

To test whether our coturn server works as a perfect turn server, first we need to generate username and password.

docker exec -it coturn /generate_user.sh

After generate the user and password:

Now go to trickle ice page to test our turn server.

