
# Organico Project

Organico is a that integrates multiple technologies to handle and save requisitions, leveraging Azure Functions for actions such as approving, rejecting, or billing product orders. 

## **Project Structure**
![architecture](/docs/architecture.png)

### **1. Organico**
- **Purpose:** The main web application.
- **Technology Stack:** C# (Backend), JavaScript (Frontend).
- **Responsibilities:**
  - User interactions.
  - Interface with Azure Functions for business logic.

### **2. Organico.FunctionApp**
- **Purpose:** Azure Functions to handle HTTP triggers.
- **Responsibilities:**
  - GET and POST all the orders using HTTP triggers.
  - Integrate with CosmosDB for CRUD operations.

### **3. Organico.JS**
- **Purpose:** Handle asynchronous and scheduled tasks using Azure Functions.
- **Components:**
  - **Queue Triggers:** Process data asynchronously.
  - **Timer Trigger:** Generate billing reports periodically.
- **Responsibilities:**
  - Ensure background operations, saving on Storage Account Queues.

### **4. Organico.Library**
- **Purpose:** A shared library for reusable logic.
- **Responsibilities:**
  - Common models and utility functions.

## **Technologies Used**

- **Frontend:** JavaScript, HTML, CSS.
- **Backend:** C#, JavaScript, Azure Functions.
- **Database:** CosmosDB.
- **Azure Functions:** HTTP Trigger, Queue Storage Trigger, Timer Trigger.
- **Library:** .NET Standard Library.

## **Getting Started**

### Prerequisites
- .NET SDK installed.
- Node.js installed.
- Azure CLI for managing resources.

### Installation

1. Clone the repository:
```bash
git clone https://github.com/lorenzouriel/azure-functions-site-orders.git
```

2. Navigate to each folder and install dependencies as required.
   
For example, for Organico.JS:
```bash
cd Organico.JS
npm install
```

### Running the Project

1. **Start the Web Application:**
```bash
cd Organico
dotnet run
```

2. **Run Azure Functions Locally:**
```bash
cd Organico.FunctionApp
func start
```

3. **Start Background Jobs:**
```bash
cd Organico.JS
func start 
```
***P.S:** As a Queue and Timer Trigger, to test you need to deploy to your Azure Storage Blob*
