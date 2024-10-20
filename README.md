# 📧 Distributed Node Network with Email Authentication

A **fully decentralized, peer-to-peer (P2P) distributed network** that allows for secure file and email handling. Each node is authenticated via email, and the system allows seamless communication and data replication between the user's nodes. This solution is entirely self-hosted and does not rely on third-party services.

## 🚀 Features

- **Email-Based Authentication**: Each node is verified via email, ensuring secure ownership and control.
- **Peer-to-Peer (P2P) Communication**: Nodes discover each other and communicate directly using WebRTC and WebSockets.
- **Distributed Storage**: Files (e.g., email attachments) are distributed across nodes, providing redundancy and resilience.
- **Local Hosting**: Each machine acts as a local server, serving files and processing email attachments.
- **Secure and Private**: All communication remains within the user's local network and devices—no third-party servers involved.

## 📂 Project Structure

```bash
.
├── browser-extension/       # Chrome Extension to facilitate distributed node handling
│   ├── background.js        # P2P logic for node discovery and communication
│   ├── popup.html           # UI for displaying discovered nodes and file sharing
│   ├── popup.js             # Script for managing attachments and peer interaction
│   └── manifest.json        # Manifest configuration for the Chrome Extension
├── node-server/             # Python server to handle email fetching and attachment storage
│   ├── main.py              # Main server logic for email checking, file serving, and P2P discovery
├── icons/                   # Icons for the browser extension
└── README.md                # This README file

🛠️ Setup and Installation
Follow the instructions below to set up the distributed network on your devices.

Prerequisites
Python 3.6+
Google Chrome (for the extension)
IMAP and SMTP Credentials for your email provider
1. Clone the Repository
bash
Copy code
git clone https://github.com/your-username/distributed-node-network.git
cd distributed-node-network
2. Install Dependencies
Navigate to the node-server directory and install the required Python packages:

bash
Copy code
cd node-server
pip install -r requirements.txt
3. Configure Email Settings
Update the following settings in the main.py file inside the node-server/ directory:

python
Copy code
IMAP_SERVER = 'imap.your-email-server.com'
SMTP_SERVER = 'smtp.your-email-server.com'
EMAIL_ADDRESS = 'your-email@domain.com'
EMAIL_PASSWORD = 'your-email-password'
These settings are required for sending authentication emails and checking for incoming emails.

4. Run the Node Server
Start the Python server that will handle email checking, file storage, and P2P discovery:

bash
Copy code
python main.py
Your local node server is now running! It will send an authentication email when initialized.

5. Install the Browser Extension
Navigate to the browser-extension/ folder and load the Chrome extension:

Open Chrome and go to chrome://extensions/.
Enable "Developer mode" in the top right corner.
Click "Load unpacked" and select the browser-extension/ directory from the cloned repository.
The extension will be installed and ready for use.
6. Authenticate the Node
When the Python server starts, it will send an authentication email. Check your inbox, and click the confirmation link to authenticate the node.

7. Discover Nodes
Once authenticated, the extension will begin discovering other authenticated nodes in the network. It will display them in the extension popup, allowing you to access files from any node.

🌐 How It Works
Authentication via Email
Each node starts as a local server and sends an authentication email to the user's registered email address.
The user receives a link in their email inbox to confirm the node.
Once authenticated, the node can participate in the distributed network and discover other nodes.
Peer-to-Peer Communication
Nodes communicate using WebRTC and WebSockets, allowing them to share files and information directly without needing a centralized server. The network is resilient: if one node goes offline, others continue to serve files.

Data Distribution and File Sharing
Files (like email attachments) are distributed across multiple nodes.
Each node stores part of the data, ensuring redundancy and availability.
Users can fetch files from any available node, making the system efficient and reliable.
🔒 Security
Email Authentication: Ensures that only the rightful owner can operate each node in the network.
Local Communication: Data is served locally on your machine, and P2P connections are encrypted.
No Third-Party Services: The solution is entirely self-hosted, meaning no external dependencies for file storage or email handling.
📝 Usage
Checking Emails
The Python server will periodically check your inbox for new emails with attachments. Attachments will be stored locally on the node and made available for download via the P2P network.

Accessing Files
Use the Chrome extension to view other authenticated nodes. You can download files (attachments) from other nodes directly via the extension's popup interface.

Managing Nodes
View connected nodes in the browser extension.
Files are replicated across nodes for redundancy, ensuring that your data is always available as long as at least one node is online.
📈 Future Enhancements
End-to-End Encryption for Attachments: Enhance the security by adding optional encryption for the files stored and transferred between nodes.
Improved Peer Discovery: Implement advanced peer discovery mechanisms, such as using DHT (Distributed Hash Table) for more scalable node discovery.
🤝 Contributing
Contributions are welcome! Please fork the repository and create a pull request with your changes. For any major changes, please open an issue first to discuss what you would like to improve.

📝 License
This project is licensed under the zchg.org License, attached.

💬 Support
If you encounter any issues or have questions, feel free to open an issue in the repository or contact the maintainer via email.
