# advprog-tutorial-10

## Experiment 2.1: Original code, and how it run
![3 Clients 1 Server](3Clients1Server.png)
The application can be run by going into the `src` direction and then running the `cargo run` command in the terminal. However, because the clients are dependent on the server, the client can only run if the server is already run. Therefore, it is only normal that we should run the server before running the client. Once the clients are up, we can send messages through the client which is then sent to and received by the server. The server, in turn, would broadcast the message to other clients that are connected to the server, thus allowing communication between clients.