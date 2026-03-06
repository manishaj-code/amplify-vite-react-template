🚀 **AI Todo Application – AWS Serverless Architecture**

This project is a full-stack serverless web application built using React + Vite and AWS Amplify.
It demonstrates how to build a modern cloud-native application using managed AWS services with authentication, API, and database integration.

The application allows users to:

Sign up / login securely

Create and manage todos

Store data in a scalable backend

Deploy automatically using CI/CD

**Architecture Flow**

1️⃣ User opens the React Web Application hosted by Amplify.

2️⃣ Authentication is handled by Amazon Cognito.

3️⃣ Once authenticated, the application communicates with AWS AppSync GraphQL API.

4️⃣ AppSync performs CRUD operations on Amazon DynamoDB.

5️⃣ Changes in the database are reflected in the UI in real-time.

☁️ AWS Services Used
Service	Purpose
1 **AWS Amplify**	Hosting and CI/CD for the frontend
2 **Amazon Cognito**	User authentication and authorization
3 **AWS AppSync**	GraphQL API for backend communication
4 **Amazon DynamoDB**	NoSQL database to store todos


⚙️ **Application Flow**
User Browser
     │
     ▼
React + Vite Frontend
     │
     ▼
AWS Amplify Hosting
     │
     ▼
Amazon Cognito (Authentication)
     │
     ▼
AWS AppSync (GraphQL API)
     │
     ▼
Amazon DynamoDB (Database)

🚀 **Deploying the Application with AWS Amplify**

This project is deployed using AWS Amplify Hosting, which provides CI/CD integration with GitHub. Every time code is pushed to the repository, Amplify automatically builds and deploys the application.

☁️ **Deployment Steps**
1️⃣ Create a New App in Amplify

Login to AWS Console

Navigate to AWS Amplify

Click Create new app

Select Host web app

2️⃣ Connect GitHub Repository

Choose GitHub as the source provider

Authorize AWS Amplify to access your GitHub account

Select your repository

Select the branch (for example: main)

3️⃣ Configure Build Settings
Amplify automatically detects that the project uses React + Vite and creates a build configuration.

Example:

version: 1
frontend:
  phases:
    preBuild:
      commands:
        - npm install
    build:
      commands:
        - npm run build
  artifacts:
    baseDirectory: dist
    files:
      - '**/*'
  cache:
    paths:
      - node_modules/**/*

4️⃣ Review and Deploy

Click Next

Review configuration

Click Save and Deploy

**Amplify will now**:

Clone the GitHub repository

Install dependencies

Build the application

Deploy it to the Amplify hosting environment

🔄 **CI/CD Pipeline**

Once deployment is complete:

Every git push triggers automatic deployment

Amplify rebuilds and updates the hosted application

Flow:

Developer Push Code → GitHub Repository
            │
            ▼
       AWS Amplify CI/CD
            │
            ▼
        Build Process
            │
            ▼
        Amplify Hosting
            │
            ▼
      Live Web Application

  🌐 **Live Application**
  **Example deployed URL:**

  https://main.dg07rc60an451.amplifyapp.com

  **After Deployment your application will be available on AWS**
  **Screenshots :**

  Signup:

  <img width="1253" height="926" alt="image" src="https://github.com/user-attachments/assets/dc047ac8-6096-4e31-ad74-ff75c5ec99ab" />

  Sign-in: 

  <img width="1439" height="908" alt="image" src="https://github.com/user-attachments/assets/7a0a97a8-1dc5-472a-8340-be9140522d30" />

  Once Sign-In in application, You are able to use To-Do application for that perticular user:
  **User1**:

  <img width="1389" height="883" alt="image" src="https://github.com/user-attachments/assets/687d1f8d-0254-4f7c-ac7c-ebb95e7a38b0" />

  **User2:**

  <img width="1569" height="838" alt="image" src="https://github.com/user-attachments/assets/a6271d7a-ce2c-4701-827e-da8140753bd6" />



  🗑️ **Delete To-Do Functionality**

  The application also supports deleting To-Do items.
  
  **How it works**:
  
  The user views the list of created To-Dos.
  
  When the user clicks on a specific To-Do item, the application triggers a delete action.
  
  The selected To-Do is removed from the Amazon DynamoDB database through the GraphQL API.
  
  The UI automatically updates and the To-Do disappears from the list.
  
  Flow
  
  User Clicks To-Do
          │
          ▼
  React Frontend
          │
          ▼
  GraphQL Mutation (Delete)
          │
          ▼
  AWS AppSync
          │
          ▼
  Amazon DynamoDB
          │
          ▼
  Updated To-Do List in UI
  
  **Note:**
  After clicking on a particular To-Do item, that To-Do will be permanently deleted from the database and removed from the UI list.





