┌─────────────────────────────────────────────────────────────────────────────────────────────────────┐
│                         🍕 CLASSROOM ACTIVITY: DESIGN A PIZZA SHOP DATABASE                        │
│                                   (Introduction to Data Modeling)                                   │
├─────────────────────────────────────────────────────────────────────────────────────────────────────┤
│                                                                                                     │
│   🎯 OBJECTIVE: Design your first database model for "Ali's Pizza Palace"                          │
│                                                                                                     │
│   📋 SCENARIO: Ali is opening a pizza shop. He needs a database to manage:                         │
│              • Customer orders                                                                      │
│              • Pizza menu                                                                           │
│              • Delivery drivers                                                                     │
│              • Order tracking                                                                       │
│                                                                                                     │
│   STEP 1: Identify ENTITIES (What are we storing data about?)                                       │
│   ─────────────────────────────────────────────────────────────────────────────────                │
│                                                                                                     │
│   Ask students: "What are the main things in a pizza shop that we need to track?"                  │
│                                                                                                     │
│   Student answers become ENTITIES:                                                                 │
│                                                                                                     │
│   ┌─────────────────┐  ┌─────────────────┐  ┌─────────────────┐  ┌─────────────────┐              │
│   │   🍕 PIZZA      │  │   👤 CUSTOMER   │  │   📦 ORDER      │  │   🚗 DRIVER     │              │
│   │   (Entity)      │  │   (Entity)      │  │   (Entity)      │  │   (Entity)      │              │
│   └─────────────────┘  └─────────────────┘  └─────────────────┘  └─────────────────┘              │
│                                                                                                     │
│   💡 ENTITY = A real-world object or concept we want to store data about                           │
│                                                                                                     │
│   STEP 2: Identify ATTRIBUTES (What details do we need for each entity?)                           │
│   ─────────────────────────────────────────────────────────────────────────────────                │
│                                                                                                     │
│   For each entity, ask: "What information do we need to know?"                                     │
│                                                                                                     │
│   ┌─────────────────────────────────────────────────────────────────────────────────────────────┐  │
│   │                                                                                             │  │
│   │   🍕 PIZZA                    👤 CUSTOMER                   📦 ORDER                        │  │
│   │   ┌─────────────────┐        ┌─────────────────┐          ┌─────────────────┐              │  │
│   │   │ Pizza ID        │        │ Customer ID     │          │ Order ID        │              │  │
│   │   │ Name            │        │ Name            │          │ Date & Time     │              │  │
│   │   │ Size            │        │ Phone Number    │          │ Customer ID     │ ←──────────┐ │  │
│   │   │ Price           │        │ Address         │          │ Pizza ID        │ ←──────┐   │ │  │
│   │   │ Crust Type      │        │ Email           │          │ Quantity        │       │   │ │  │
│   │   │ Vegetarian?     │        │                   │          │ Total Amount    │       │   │ │  │
│   │   └─────────────────┘        └─────────────────┘          │ Driver ID       │ ←──┐  │   │ │  │
│   │                                                           │ Status          │    │  │   │ │  │
│   │   🚗 DRIVER                                                └─────────────────┘    │  │   │ │  │
│   │   ┌─────────────────┐                                                            │  │   │ │  │
│   │   │ Driver ID       │                                                            │  │   │ │  │
│   │   │ Name            │                                                            │  │   │ │  │
│   │   │ Phone           │                                                            │  │   │ │  │
│   │   │ Vehicle Number  │                                                            │  │   │ │  │
│   │   │ Status          │                                                            │  │   │ │  │
│   │   └─────────────────┘                                                            │  │   │ │  │
│   │                                                                                  │  │   │ │  │
│   └──────────────────────────────────────────────────────────────────────────────────┼──┼───┼─┘  │
│                                                                                      │  │   │    │
│   💡 ATTRIBUTE = A specific detail/property of an entity (becomes a FIELD in table)  │  │   │    │
│                                                                                      │  │   │    │
│   STEP 3: Identify RELATIONSHIPS (How are entities connected?)                       │  │   │    │
│   ─────────────────────────────────────────────────────────────────────────────────  │  │   │    │
│                                                                                      │  │   │    │
│   Ask students: "How do these things relate to each other?"                          │  │   │    │
│                                                                                      │  │   │    │
│   ┌─────────────────────────────────────────────────────────────────────────────────┼──┼───┼────┘  │
│   │                                                                                 │  │   │       │
│   │   👤 CUSTOMER ──────── (places) ────────▶ 📦 ORDER                              │  │   │       │
│   │   (One customer can have MANY orders)                                           │  │   │       │
│   │                                                                                 │  │   │       │
│   │   🍕 PIZZA ────────── (is in) ──────────▶ 📦 ORDER                              │  │   │       │
│   │   (One pizza can be in MANY orders)                                             │  │   │       │
│   │                                                                                 │  │   │       │
│   │   🚗 DRIVER ───────── (delivers) ────────▶ 📦 ORDER                             │  │   │       │
│   │   (One driver can deliver MANY orders)                                          │  │   │       │
│   │                                                                                 │  │   │       │
│   └─────────────────────────────────────────────────────────────────────────────────┴──┴───┴───────┘
│                                                                                                     │
│   💡 RELATIONSHIP = How entities are connected (One-to-Many, Many-to-Many, etc.)                   │
│                                                                                                     │
│   STEP 4: Create TABLES from Entities (Now we can build!)                                          │
│   ─────────────────────────────────────────────────────────────────────────────────                │
│                                                                                                     │
│   ┌─────────────────────────────────────────────────────────────────────────────────────────────┐  │
│   │                                                                                             │  │
│   │   🍕 PIZZA Table                    👤 CUSTOMER Table                                        │  │
│   │   ┌──────────┬────────────┬───────┐  ┌──────────┬────────────┬─────────────────┐           │  │
│   │   │ Pizza ID │ Name       │ Price │  │ Cust ID  │ Name       │ Phone           │           │  │
│   │   ├──────────┼────────────┼───────┤  ├──────────┼────────────┼─────────────────┤           │  │
│   │   │ P001     │ Margherita │ $8.99 │  │ C001     │ Ali Khan   │ 0300-1234567    │           │  │
│   │   │ P002     │ Pepperoni  │ $10.99│  │ C002     │ Sara Ahmed │ 0301-7654321    │           │  │
│   │   │ P003     │ Veggie     │ $9.99 │  │ C003     │ Ahmed Raza │ 0302-9876543    │           │  │
│   │   └──────────┴────────────┴───────┘  └──────────┴────────────┴─────────────────┘           │  │
│   │                                                                                             │  │
│   │   📦 ORDER Table                      🚗 DRIVER Table                                        │  │
│   │   ┌─────────┬────────────┬───────────┐  ┌──────────┬────────────┬─────────────┐           │  │
│   │   │Order ID │ Date       │ Cust ID   │  │Driver ID │ Name       │ Vehicle     │           │  │
│   │   ├─────────┼────────────┼───────────┤  ├──────────┼────────────┼─────────────┤           │  │
│   │   │ OR001   │ 28-Mar-2025│ C001      │  │ D001     │ Bilal      │ Bike-101    │           │  │
│   │   │ OR002   │ 28-Mar-2025│ C002      │  │ D002     │ Fatima     │ Car-202     │           │  │
│   │   │ OR003   │ 29-Mar-2025│ C001      │  │ D003     │ Usman      │ Bike-303    │           │  │
│   │   └─────────┴────────────┴───────────┘  └──────────┴────────────┴─────────────┘           │  │
│   │                                                                                             │  │
│   └─────────────────────────────────────────────────────────────────────────────────────────────┘  │
│                                                                                                     │
└─────────────────────────────────────────────────────────────────────────────────────────────────────┘
