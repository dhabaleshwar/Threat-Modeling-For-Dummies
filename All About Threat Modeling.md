# Introduction
Threat modeling is a way of identifying and prioritizing potential threats to a system (like a computer program or network) and figuring out how to reduce or neutralize those threats. It helps us understand where the system might be vulnerable and how to protect it. Think of Threat modeling as playing detective to find potential problems and protect a system, like a computer program or network. 

Here are some important terms to know:

**1. Threat agent:** This refers to the person or group that has the ability to carry out a threat. We need to identify who might want to attack the system, how they would do it, and if they have the capability to do so. Think of a threat agent as a "bad guy" who could attack the system. It could be a person or a group with the ability to cause harm.

**2. Impact:** Impact measures the potential damage caused by a threat. It can include physical damage, financial loss, harm to a company's reputation, or loss of user trust. Some threats may have indirect consequences that need to be considered too.

**3. Likelihood:** Likelihood is the possibility of a threat happening. Factors like the difficulty of carrying out the threat and the potential reward for the attacker affect the likelihood. If it's hard to carry out the threat or the reward is low, the likelihood is low. But if it's easier to attack or the attacker stands to gain valuable information, the likelihood is higher.

**4. Controls:** Controls are safeguards or countermeasures we put in place to protect the system from threats. There are two types:
   - Preventions: These controls completely prevent a specific attack from happening. For example, removing certain application logging to avoid exposing users' personal information.
   - Mitigations: These controls reduce the likelihood or impact of a threat without completely preventing it. For instance, adding salts to user passwords to make them harder to crack.

Now, let's talk about some key concepts:

**1. Data flow diagram:** This is a visual representation of how information flows through a system. It shows where data is input or output, and where it is stored temporarily or permanently.

**2. Trust boundary:** A trust boundary is a point on the data flow diagram where data changes its level of trust. It's usually where data is passed between different processes or subsystems. Think of it as a "safety line" where we know the data is safe. When data crosses this line, we need to be careful because it could be changed or manipulated by others. For example, when your application reads a file from disk, there's a trust boundary between the application and the file because the file can be modified by external processes or users.

In threat modeling, we create a threat model by following these steps:
```
1. Document how data flows through the system to identify possible attack points.
2. Identify and document as many potential threats to the system as possible.
3. Document security controls that can be implemented to reduce the likelihood or impact of those threats.
```
Threat modeling should be done by everyone involved in software development, not just security experts. It's important to include threat modeling early in the development process to save resources and address risks effectively. By understanding potential threats and implementing appropriate controls, we can protect our systems, applications, and user data from harm.
# Let's Get Started


## Define Business Objectives
Before starting threat modeling, it's important to understand the goals and requirements of the application or system you're assessing. This includes considering what the application aims to achieve for the business and any security or compliance regulations that need to be followed.

Example: Let's say you're assessing a shopping website. The business objective is to provide a secure and user-friendly platform for customers to browse and purchase products.

## Identify Application Design 
To perform threat modeling, you need to understand how the application is designed. This involves creating a diagram that shows how data flows within the system and identifying trust boundaries (where data changes its level of trust). Understanding the design helps assess the likelihood and impact of potential threats.

Example: In the shopping website example, the design would include how users input their information, how the website handles payment transactions, and how data is stored and protected.

## Create Design Documents
Design documents help document and communicate the application's design. One approach is the 4+1 view model, which provides different perspectives on the system's architecture. The views include:

**- Logical View:** Describes the application's object model and how it functions from a functional standpoint. It focuses on the system's behavior and relationships between components.

Example: In the shopping website, the logical view would outline the different parts of the website, such as the product catalog, shopping cart, and user account management.

**- Implementation View:** Focuses on the software components and how they are organized in layers or subsystems. It helps programmers understand how to build the application.

Example: The implementation view would show how the different software components, like the front-end interface and the back-end server, work together.

**- Process View:** Describes the non-functional aspects of the design, such as how the system handles concurrency and synchronization. It helps integrators understand how the different parts of the system interact.

Example: The process view would show how multiple users can interact with the website simultaneously and how the system handles their requests.

**- Deployment View:** Focuses on the physical infrastructure and shows how the software is deployed on hardware. It helps deployment managers understand how to set up and maintain the system.

Example: The deployment view would show how the website is hosted on servers and how those servers are connected.

**- Use-Case View:** Describes the central functionality of the system through specific scenarios or use cases. It helps all stakeholders, including end users, understand the system's purpose and features.

Example: The use-case view would outline scenarios like searching for products, adding items to the cart, and completing a purchase.

By using the 4+1 view model , everyone involved in building the software can have a better understanding of how the system works from different perspectives. It helps in communication, identifying potential issues, and making sure the system meets the requirements of users and stakeholders.
## Decomposing and Modeling The System
To perform threat modeling, it's important to understand how a system works and how it interacts with its surroundings. Here are some steps to help you decompose and model the system:

1- Start by creating a high-level diagram that shows the flow of information in the system. Identify the different parts of the system, like applications or modules, and how they connect with each other.

2- Identify the trusted boundaries of the system. These are the points where the system interacts with external entities. For example, if you're looking at a website, the trusted boundary could be where the website interacts with user input.

3- Add actors to the diagram. Actors can be both internal and external entities that interact with the system. Internal actors could be users or administrators, while external actors could be attackers or other systems.

4- Define internal trusted boundaries within the system. These are the different security zones or compartments that have been designed to protect certain parts of the system.

5- Review the actors you identified earlier to make sure they align with the trusted boundaries and the overall system design.

6- Add information flows to the diagram. These represent how data or information moves between different parts of the system. For example, it could be the flow of user input from a web form to a database.

7- Identify the information elements and classify them based on your information classification policy. This means categorizing the information based on its sensitivity or importance. For example, personal user data may be classified as highly sensitive.

8- Where possible, add assets to the identified information flows. Assets are the valuable resources that need protection, such as databases, servers, or intellectual property. This helps you identify what needs to be safeguarded.

## Define and Evaluate your Assets

In the context of threat modeling, assets refer to the valuable resources within a system or organization. These assets can include sensitive data, intellectual property, infrastructure components, or anything else that holds value. It is important to define and evaluate these assets based on their confidentiality, integrity, and availability.

Example: In a cybersecurity context, assets can include customer data, financial information, proprietary software code, or critical infrastructure components like servers or network devices. Evaluating the value of these assets helps prioritize security measures and allocate resources effectively.

## Consider Data in transit and Data at rest
Data in transit refers to information that is being transmitted over networks or transferred between different devices. Data at rest, on the other hand, refers to information that is stored or saved on storage devices, servers, or databases. Protecting both data in transit and data at rest is crucial to maintain the security of sensitive information.

Example: When you send an email, the data being transmitted from your device to the email server is data in transit. Encrypting the email using secure protocols ensures that it cannot be intercepted and read by unauthorized individuals. Similarly, when you store files on your computer's hard drive, they become data at rest. Implementing encryption or access controls to protect the files from unauthorized access safeguards the data.

## Create an information flow diagram
An information flow diagram is a visual representation of how data moves within a system. It shows how information is processed, transferred, and accessed by different components or entities within the system.

Example: In a typical e-commerce website, an information flow diagram would depict how user inputs, such as product orders or payment information, flow through the web application, database, and payment gateway. Understanding this flow helps identify potential points of vulnerability and implement security measures to protect the data during its journey.

## Whiteboard Your Architecture
Whiteboarding the system architecture means drawing a simplified diagram that highlights the main components, constraints, and decisions of the system. It helps provide a clear overview and facilitates communication among stakeholders.

Example: Imagine you are designing a mobile banking application. Whiteboarding the architecture would involve sketching out the user interface, the server infrastructure, and the connection between them. This visual representation helps everyone involved understand the overall structure and functionalities of the application.

## Manage to present your DFD in the context of MVC
When creating a Data Flow Diagram (DFD), it can be helpful to divide it into the context of the Model-View-Controller (MVC) architectural pattern. MVC separates the system into three components: the model (data and logic), the view (user interface), and the controller (handles user input and manages the interaction between the model and view).

Example: In the context of an e-commerce website, the model component would represent the product catalog and inventory management, the view component would be the web pages that users see, and the controller component would handle the shopping cart functionality and order processing. Organizing the DFD in this way helps understand the system's functionality and potential security risks associated with each component.

## Use tools to draw your diagram
There are various tools available that can assist in creating the information flow diagram or DFD. These tools provide features and templates to visualize the system's architecture and highlight potential threats.

Example: OWASP Threat Dragon, Microsoft Threat Modeling Tool (TMT), and OWASP PYTM are examples of tools that help in creating threat model diagrams. These tools offer functionalities to record threats, identify mitigations, and generate visual representations of the system's architecture and associated risks.

## Define Data Flow over your DFD
When defining the data flow in the DFD, you need to identify how information moves within the organization or system.

This includes understanding the sources, destinations, and transformations of data throughout its lifecycle.

Example: In the context of an online banking system, the data flow could include user login information, transaction details, and account balances. Mapping out the data flow helps identify potential security vulnerabilities, such as unauthorized access or data leakage, at each stage of the process.

## Define Trust Boundaries
Trust boundaries represent the points within a system where trust is established or boundaries between different levels of trust. Defining these boundaries helps identify areas where security controls and measures should be enforced.

Example: In a corporate network, a trust boundary may exist between the internal network and the external internet. The internal network is considered more trusted, and access to resources outside the network requires additional security measures such as firewalls or access controls to protect against external threats.

## Define applications user roles and trust levels
In this step, you define different user roles and their corresponding levels of trust within the system. User roles determine the privileges and access rights granted to individuals or entities using the application.

Example: In an online shopping website, user roles can include regular customers, administrators, and guest users. Each role has different levels of access and permissions within the system. For instance, administrators have higher privileges to manage product listings and customer data, while guest users may have limited access for browsing products.

## Highlight Authorization per user role over the DFD
This step involves specifying the authorization or permissions granted to different user roles within the system. It ensures that only authorized individuals can access and perform specific actions based on their assigned roles.

Example: In an educational institution's student information system, different user roles could include students, teachers, and administrative staff. Each role would have different levels of authorization, with students having access to their own grades and assignments, teachers being able to enter grades, and administrators having broader administrative privileges.

## Define Application Entry points
Application entry points are the interfaces or channels through which potential attackers can interact with the application or introduce malicious data or commands.

Example: For a web-based application, entry points could include web forms, login screens, or API endpoints. Attackers may attempt to exploit vulnerabilities in these entry points to gain unauthorized access or inject malicious code.

