# CS 360 Portfolio — Stockroom Inventory

**Maximo Obra Winfield**

Project Three artifact: [App code and finalized UI design](Maximo_Obra_Winfield_Inventory_App_Project_Three.zip).

The ZIP contains the Android project, Java source code, XML layouts, database instrumentation test, and build and verification instructions in `StockroomInventory/README.txt`.

**Briefly summarize the requirements and goals of the app you developed. What user needs was this app designed to address?**

I developed Stockroom Inventory to help users organize inventory on an Android device. The requirements included account creation and login, a grid of stored items, the ability to add, edit, and delete records, and optional SMS alerts when stock reaches zero. Users need to find items quickly, identify their storage locations, update quantities, and retain their information between sessions. My implementation uses SQLite for a shared stockroom on one device, with separate user accounts and individual SMS preferences.

**What screens and features were necessary to support user needs and produce a user-centered UI for the app? How did your UI designs keep users in mind? Why were your designs successful?**

The interface includes login and account creation, an inventory grid, an add/edit form, item details with quantity controls, and an SMS settings screen. Search and an out-of-stock filter help users locate relevant items, while labeled fields, readable stock statuses, and consistent controls make actions easier to understand. I also included deletion confirmation, responsive grid columns, and scrollable forms to support different screen sizes and reduce accidental changes. These choices support the intended workflow by keeping common inventory tasks visible and organized; final usability still needs to be verified in the running Project Three app.

**How did you approach the process of coding your app? What techniques or strategies did you use? How could those techniques or strategies be applied in the future?**

I used the Project Two interface as the starting point and organized the implementation around navigation, account access, inventory storage, and optional alerts. Separate classes handle database operations, password hashing, inventory display, and SMS behavior, making each responsibility easier to understand. Input checks and database constraints address missing fields, duplicate identifiers, and invalid quantities. I can apply this approach in future projects by breaking requirements into smaller components, defining how they interact, and checking those interactions throughout development.

**How did you test to ensure your code was functional? Why is this process important, and what did it reveal?**

The recorded validation included Java syntax and resource checks and standalone password checks. I also included an Android instrumentation test covering account authentication, duplicate usernames and item identifiers, inventory changes, data persistence after reopening the database, and zero-stock alert conditions. However, the Project Three notes document that the Android build, instrumentation tests, and emulator UI checks were not successfully completed because the preparation environment lacked an Android SDK and emulator and could not download Gradle. This leaves functionality on Android unverified. The process highlighted the need to distinguish source-level checks from testing the complete application; a successful build, device testing, and SMS verification remain necessary to establish that the full user experience works.

**Consider the full app design and development process from initial planning to finalization. Where did you have to innovate to overcome a challenge?**

One challenge was connecting zero-stock alerts to inventory changes without sending repeated messages whenever a user reopened a screen. I addressed this by checking the item's quantity before and after a save and triggering an alert only when a new item starts at zero or an existing item changes from a positive quantity to zero. I also separated account opt-in from Android's SMS permission and kept inventory saves independent of message delivery. This design accommodates users who decline alerts and devices where SMS is unavailable, while keeping stock management as the main purpose of the app.

**In what specific component of your mobile app were you particularly successful in demonstrating your knowledge, skills, and experience?**

The inventory database component best demonstrates my skills in translating application requirements into a structured implementation. It centralizes creating, reading, updating, and deleting records, uses unique item identifiers, and prevents negative quantities. Connecting those operations to the inventory grid and item detail screens shows how I approached the relationship between stored data and the interface. The accompanying instrumentation test also demonstrates my understanding of the behaviors that need verification, even though its execution remains pending.
