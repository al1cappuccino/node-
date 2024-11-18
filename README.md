# node-
node program


1. Ensure your Keplr wallet has some NIL


Go to the faucet to obtain NIL in your Keplr wallet

Link to Nillion Faucet

2. Installing Docker


To install the verifier you will first need to install Docker for your respective platform.

Link to docker

3. Verifying Docker install


You should now be able to run the following to get the version number of your Docker installation:

Getting the Docker version
docker --version
Which should return a version number like the following:

Docker version 27.1.1, build 63125853e3
Running the hello world container
Now check everything is working:

docker container run --rm hello-world
This will print out “Hello from Docker!”


4. Getting the verifier image


To get the verifier's docker image, pull it from Docker Hub:

docker pull nillion/verifier:v1.0.1

5. Initialising the verifier


Create a directory to store your verifier's data:

mkdir -p nillion/verifier
Then initialise the verifier:

docker run -v ./nillion/verifier:/var/tmp nillion/verifier:v1.0.1 initialise
This outputs registration details. Enter them below:

Verifier account id
Verifier public key

complete verifier connection
Link

6. Funding the verifier


In order to challenge secrets on the Nillion chain, the verifier account must be funded with Nil. You can get these using the Nillion faucet:

Link to Nillion Faucet

7. Running the verifier


Now run your verifier:

docker run -v ./nillion/verifier:/var/tmp nillion/verifier:v1.0.1 verify --rpc-endpoint "https://testnet-nillion-rpc.lavenderfive.com"
Your verifier is now running. It pause for a cool down period before starting to challenge secrets.


8. Backup your verifier's credentials


Your verifier's credentials are in nillion/verifier/credentials.json.

These should be backed up because you are the only one with access to them.
