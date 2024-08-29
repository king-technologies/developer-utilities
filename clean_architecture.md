# Clean Architecture

In Clean Architecture, the flow of writing code follows a layered approach where each layer has a specific responsibility. The key principle is to maintain a clear separation of concerns, ensuring that the core business logic is independent of external frameworks, UI, and data sources. Here's the typical flow for implementing features using Clean Architecture:


1. Set Up Project Structure
- Principle: Start by setting up a clear project structure that reflects Clean Architecture principles. This ensures that each component is placed in its respective layer.

```bash
/lib
├── /domain
│   ├── /entities
│   ├── /repositories
│   └── /usecases
├── /data
│   ├── /datasources
│   └── /repositories
└── /presentation
    ├── /ui
    └── /state_management
```

1. Define the Core Domain (Entities)

Principle: Entities represent the core business logic. They are independent and should not rely on any external frameworks or libraries.
- Goal: Define the core business logic and models (entities) that represent the core concepts of your application.
- Location: Domain Layer
- Steps:
     1. Identify the main business objects and their properties.
     2. Create plain classes that represent these entities.
     3. Ensure they are pure Dart classes without dependencies.


2. Define and Implement Use Cases (Business Logic)

- Principle: Use cases encapsulate the application’s business logic. They should coordinate the interactions between entities and repository interfaces.
- Goal: Implement the business logic that uses the entities to perform specific tasks. Use cases encapsulate the actions that can be performed in your application.
- Location: Domain Layer
- Steps:
     1. Identify actions that involve your entities (e.g., saving a setting, retrieving a setting).
     2. Create classes that represent these actions and encapsulate the logic.


3. Abstract Data Sources (Repositories)

- Goal: Abstract the data layer by defining interfaces (repositories) that declare methods to access or manipulate data.
- Location: Domain Layer
- Steps:
    1. Identify the data operations needed by your use cases.
    2. Create repository interfaces that declare these operations.


4. Implement Data Sources

- Goal: Provide concrete implementations of the repository interfaces using various data sources like local storage, databases, or remote APIs.
- Location: Data Layer
- Steps:
    1. Create data source classes that interact with the specific technology (e.g., SharedPreferences, SQLite).
    2. Implement repository interfaces by using these data sources.


5. Implement Presentation Logic

- Goal: Implement the UI logic that interacts with the use cases and responds to user input.
- Location: Presentation Layer
- Steps:
    1. Create state management classes (e.g., Riverpod providers) that use the use cases.
    2. Build UI components that observe these state providers and react to changes.


6. Build UI Components

- Goal: Create the UI components that display data and handle user interactions.
- Location: Presentation Layer
- Steps:
    1. Create widgets that are bound to the state managed by Riverpod providers.
    2. Ensure that these widgets are decoupled from the business logic.


7. Connect Everything in main.dart

- Goal: Initialize dependencies and connect the different layers.
- Location: Root of the Application
- Steps:
    1. Initialize SharedPreferences and other dependencies.
    2. Pass them to the relevant providers.

#### Summary of the Flow:
1. **Start with the Domain Layer:** Define entities, use cases, and repository interfaces.
2. **Move to the Data Layer:** Implement the repository interfaces using actual data sources (e.g., SharedPreferences).
3. **Proceed to the Presentation Layer:** Implement state management and UI components that interact with the use cases.
4. **Integrate and Initialize:** Bring everything together in the main.dart file, ensuring dependencies are correctly passed through providers.
This approach ensures that your core business logic is decoupled from the UI and data storage, making your codebase more maintainable and testable.