# chatapproject
Implementation of websocket and basic jwt authentication in django.
#Description

Create a chat application using Django that allows users to create accounts, login, view online users, start chats with online users, and restrict sending messages to offline users.

#To start the project 
python manage.py runserver
python manage.py process_tasks
daphne chat_project.asgi:application

chatapp collection contains user api's

login->get bearer token use in other api's which says unauthorized

#websocket request  will be used to send messages.
for localhost
url ->ws://127.0.0.1:8000/ws/chat/some_room_name/
message :
{
            "recipient": "User2",
            "message": "Hello, User1! This is a sent message2",
            "sender":"User1"
        }

###############
users are named as
username:User1, User2,User3, etc....
password for each user is same "secretpassword".
