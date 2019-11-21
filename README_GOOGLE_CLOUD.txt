Read this: https://cloud.google.com/community/tutorials/docker-compose-on-container-optimized-os

1. Launch new virtual machine, in this case g1-small (1 vCPU, 1,7 GB memory)
2. Modify ~/.bashrc and execute source ~/.bashrc

Add this lines to ~/.bashrc
# Put your fun stuff here.
alias docker-compose='docker run --rm \
    -v /var/run/docker.sock:/var/run/docker.sock \
    -v "$PWD:$PWD" \
    -w="$PWD" \
    docker/compose:latest'

and after that
source ~/.bashrc


3. Open shh teminal an execute Run 

   docker-compose up -d --build
   docker exec gs-api "node" "server/load_data.js"

   See this: https://blog.patricktriest.com/text-search-docker-elasticsearch/
