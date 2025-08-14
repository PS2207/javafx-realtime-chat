Day1 Task-
1)Generate the Project :
    *Go to Spring Initializr.
    *Create a new project named javafx-realtime-chat(or any other name).
    *Select dependencies like Spring Web, JavaFX, lombok, dev tools and any other you need.
    *Generate and download the project.
  
2)Open in IDE :
   *Open Eclipse.
   *Import the generated project as an Existing Maven Project.
  
3)Write the Code:
   *Start coding your chat application:
   *Create your JavaFX GUI for chat.
   *Set up Spring Boot controllers and WebSocket endpoints for real-time messaging.
  
4)Run the Application :
   *Run your Spring Boot application from Eclipse.
   *Ensure the server starts successfully.
  
5)Test in Multiple Browsers :
   *Open two or more browser windows/tabs.
   *Type the application URL (e.g., http://localhost:8081/chat.html) in each browser.
   *Use the chat interface to send messages between browsers, verifying real-time communication works.
   
/*
Right now server is probably accepting whatever the client sends as sender name.
That means someone could fake it (can change name everytime). so needs to modify it.
If you already have authentication, you can extract the username from the session/JWT instead of from the message body.
----------------------
so the username in messages to be secure and not fake-able, the correct flow is:
Register Page – user creates an account in your Spring Boot backend (stored in DB).
Login Page – user logs in and gets an authenticated session (Spring Security).
WebSocket Handshake – WebSocket connection is established after login, so principal.getName() in your ChatController will return the logged-in username automatically.
Send Messages – since the username comes from principal, no one can fake it in the client.
*/
-----------------------------------------------------------------------------------------------------------
