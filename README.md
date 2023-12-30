```markdown
# 🚀 Socket.IO Video Chat Server

Welcome to the Socket.IO Video Chat Server! This server facilitates real-time video communication using Socket.IO for seamless, peer-to-peer connections. Let's dive into the details:

## 🌐 Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) installed on your machine.

### Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/your-username/socket-io-video-chat.git
   ```

2. Navigate to the project directory:

   ```bash
   cd socket-io-video-chat
   ```

3. Install dependencies:

   ```bash
   npm install
   ```

## ⚙️ Configuration

Update the `config.js` file to customize the server settings.

```javascript
const { Server } = require("socket.io");

const io = new Server(8000, {
  cors: true,
});
```

## 🚀 Usage

### Running the Server

Start the Socket.IO server by running:

```bash
npm start
```

The server will be live on [http://localhost:8000](http://localhost:8000).

## 🎉 Features

- **User Authentication:** Connect users based on their email addresses.
- **Room Joining:** Users can join specific chat rooms.
- **Real-Time Events:** Handles various real-time events, such as user joining, calls, call acceptance, and negotiation.

## 📚 API Documentation

### `room:join`

```javascript
socket.on("room:join", (data) => {
  // Handles user joining a room
});
```

### `user:call`

```javascript
socket.on("user:call", ({ to, offer }) => {
  // Initiates an incoming call to the specified user
});
```

### `call:accepted`

```javascript
socket.on("call:accepted", ({ to, ans }) => {
  // Notifies when a call has been accepted
});
```

### `peer:nego:needed`

```javascript
socket.on("peer:nego:needed", ({ to, offer }) => {
  // Initiates peer negotiation
});
```

### `peer:nego:done`

```javascript
socket.on("peer:nego:done", ({ to, ans }) => {
  // Finalizes peer negotiation
});
```

## 🧠 Theories

In the realm of real-time video communication, it's crucial to understand the underlying protocols and architectures. Here are some key concepts relevant to the Socket.IO Video Chat Server:

### TCP vs. UDP

- **TCP:**
  - Ensures no packet loss during transmission.
  - Requires a server for communication.
  - Ideal for file-sending applications.

- **UDP:**
  - May encounter packet loss.
  - Doesn't require a dedicated server.
  - Suited for video streaming applications.

### Ice/Turn Servers and Session Descriptions

- Ice/Turn servers play a vital role in informing Wi-Fi routers about a laptop's public IP address.
- Each laptop generates a session description, facilitating its exchange through Node.js (socket) with the help of signaling.
- WebRTC establishes a peer-to-peer (p2p) connection, preventing third-party connections. Mesh architecture is avoided due to scalability concerns.

### Selective Forwarding Unit (SFU) Server Architecture

- SFU allows third-party connections, overcoming the limitation of a pure p2p connection.
- In this setup, each laptop/client shares its session description with a virtual server acting as an SFU.
- The SFU server then distributes the collected session descriptions to every client, creating a grid similar to the one seen in video call frames.

Understanding these principles enhances the comprehension of the Socket.IO Video Chat Server architecture and its ability to support both peer-to-peer and third-party connections.

## 🤖 Contribution

Feel free to contribute and enhance this video chat server. Create issues, submit pull requests, and let's make this project even more awesome together!

Happy coding! 🚀👩‍💻👨‍💻
```
