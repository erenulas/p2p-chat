# P2P Chat
It is a p2p chat application that uses centralized index approach. It consists of two parts a registry application and a chat application. Registry application keeps track of the peers, and chat application allows peers to communicate with each other.
* Registry application can achieve following operations:
    * **Account Creation**<br/>
    Accounts can be created on registry. Each user is identified by a unique username.
    * **Login and Logout**<br/>
    When a user logs in, registry saves its ip address and port number into database and this entry stays in the database until the user logs out or disconnected.<br/>As long as user is online, a 'HELLO' message is sent to registry at every second to indicate that the user is still connected. If the registry hasn't received a 'HELLO' message from a user in 3 seconds, it considers user as disconnected and removes its entry from online peers.
    * **Search**<br/>
    A user can search another online user using that user's username to retrieve the ip address and the port number of the user.
* Chat application can achieve following operations:
    * **Communication with Registry**<br/>
    Chat application sends messages to registry to achieve account creation, login, logout, and search operations.
    * **Chat**<br/>
    When a user wants to chat with another user, a chat request is sent to the other user. User should send an 'OK' message to accept or a 'REJECT' message to reject. However, if user is already chatting with someone else, then a 'BUSY' message will be sent automatically.

## How to Use It?
* Clone the repo.
* Run 'registry.py'.
* Run 'peer.py'.
* Chat!
