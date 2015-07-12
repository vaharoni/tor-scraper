THIS REPO IS INCOMPLETE

The objective is to create a pool of docker containers running tor and privoxy, each with a different country exit,
and expose a service allowing proxying HTTP requests from different countries dynamically. 

= Installation
  
  - Install Docker
  - $ sudo docker run -d -P --name tor -h tor eg5846/tor-docker

  Make sure to install Tor on both dev machine and server:
  
  # On Mac
  brew install tor
  
  # On Ubuntu
  sudo apt-get install tor
