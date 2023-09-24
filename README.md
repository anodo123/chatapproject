#The actual project is in zip folder please clone and Unzip to access the django project
# ChatApp Project

A real-time chat application built using Django, WebSocket, and JWT authentication. This application allows users to create accounts, log in, view online users, initiate chats with online users, send messages to online users, and restrict sending messages to offline users.

## Table of Contents

- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
- [Authentication](#authentication)
- [API Endpoints](#api-endpoints)
- [WebSocket](#websocket)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

## Getting Started

### Prerequisites

Before you start, ensure you have the following installed:

- Python 3.7+
- Django
- Django Rest Framework
- Channels

### Installation

1. Clone the repository:

   ```
   git clone https://github.com/yourusername/chatapp.git
   cd chatapp
Create a virtual environment:



python -m venv venv
source venv/bin/activate
Install dependencies:
pip install -r requirements.txt
Apply migrations:
python manage.py migrate

Run the development server:
python manage.py runserver

Start the WebSocket server (asynchronous):
python manage.py process_tasks
daphne chat_project.asgi:application
Authentication
To access protected API endpoints, you need to authenticate using JWT (JSON Web Tokens). Follow these steps:

Register a user account using the //chatapp/register/ endpoint.
Log in with your registered account using the //chatapp/login/ endpoint to obtain a JWT token.
Include the JWT token in the Authorization header of your API requests.
API Endpoints
User Authentication
POST //hatapp/register/: Register a new user.
POST /chatapp/login/: Log in and obtain a JWT token.
Chat Operations
GET /chatapp/online-users/: Retrieve a list of online users.
POST /chatapp/start-chat/: Start a chat with an online user.
POST /chatapp/send-message/: Send a message to an online user. (WebSocket is used for real-time messaging)
POST /chatapp/restrict-offline-message/: Restrict sending messages to offline users.
WebSocket
WebSocket is used for real-time messaging in this application. To send messages using WebSocket:

WebSocket URL: ws://127.0.0.1:8000/ws/chat/some_room_name/

Message format:

json

{
    "recipient": "User2",
    "message": "Hello, User1! This is a sent message2",
    "sender": "User1"
}
Usage
Register a user account.
Log in and obtain a JWT token.
Use the API endpoints to interact with the chat application.
To send real-time messages, use WebSocket as described above.
