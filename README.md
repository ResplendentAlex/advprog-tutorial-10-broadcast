# advprog-tutorial-10

## Experiment 2.1: Original code, and how it run
![3 Clients 1 Server](3Clients1Server.png)
The application can be run by going into the `src` direction and then running the `cargo run` command in the terminal. However, because the clients are dependent on the server, the client can only run if the server is already run. Therefore, it is only normal that we should run the server before running the client. Once the clients are up, we can send messages through the client which is then sent to and received by the server. The server, in turn, would broadcast the message to other clients that are connected to the server, thus allowing communication between clients.

## Experiment 2.2: Modifying Port
There are two parts of the code that we need to change, namely the one in `server.rs` and the one in `client.rs`
1. For the one in the server side of the code, the change is as follows:
![Modified Server Code](ServerModification.png)
From the image above, we change the listener to listen to port `8080` instead of `2000` as required by the experiment.

2. For the on in the client side of the code, the change is as follows:
![Modified Client Code](ClientModification.png)
Now, since the server is listening to port `8080`, we need to connect the client's WebSocket (`ws://` protocol) to port `8080` as well so that any messages sent would be sent to port `8080` instead of port `2000`.

## Experiment 2.3: Small Changes, add IP and Port
![Small Changes](SmallChanges.png)
The image above shows results after modification in the client and server side. As we can see that there's an additional "Alex's Computer" added into the output as the message is sent from my device. The changes for client and server side code is as follows:
1. Server side changes:
![Server Side](ServerChange.png)
Address of the sender is added to the message broadcasted by the server to other users. This allows other users to easily identify who sent the message to server.

2. Cient side changes:
![Client Side](ClientChange.png)
The change here is not very significant as it only shows whose device is the message sent from, in this case, my device which is Alex's computer.

The reason why changes are made in the server instead of the client is in consideration of possible cases where certain connected clients in the future may not receive the formatted address. However, with the current modifications, as in the server, it assures that the message sent would always be in the desired format, thus the modification. 