**2️⃣ Add Entity Shapes**

1. In the **left panel**, expand **"Entity Relationship"** under **More Shapes** (if not visible, click **"More Shapes" > "Entity Relationship"**).
2. Drag the **"Entity"** shape into the workspace **seven times**, renaming them as follows:
    - **User**
    - **Energy Usage**
    - **Carbon Footprint**
    - **Appointments**
    - **Consultation Service**
    - **Recommendations**
    - **Accessibility Settings** (if required)

**3️⃣ Define Primary Keys (PK) and Foreign Keys (FK)**

1. **Double-click** each entity to edit the text inside.
2. **Format the attributes** inside each box as follows:

**User**

\+ User_ID (PK)

\+ Name

\+ Email

\+ Role (User/Admin)

✅ **Primary Key (PK):** User_ID

**Energy Usage**

\+ Energy_ID (PK)

\+ User_ID (FK)

\+ Usage in kWh

✅ **Primary Key (PK):** Energy_ID  
✅ **Foreign Key (FK):** User_ID → Links to **User (User_ID)**

**Carbon Footprint**

\+ Footprint_ID (PK)

\+ Energy_ID (FK)

\+ User_ID (FK)

\+ Footprint in KG

✅ **Primary Key (PK):** Footprint_ID  
✅ **Foreign Key (FK):** Energy_ID → Links to **Energy Usage (Energy_ID)**  
✅ **Foreign Key (FK):** User_ID → Links to **User (User_ID)**

**Appointments**

\+ Appointment_ID (PK)

\+ User_ID (FK)

\+ Appointment Date

\+ Customer Name

\+ Customer Email

✅ **Primary Key (PK):** Appointment_ID  
✅ **Foreign Key (FK):** User_ID → Links to **User (User_ID)**

**Consultation Service**

\+ Service_ID (PK)

\+ Appointment_ID (FK)

✅ **Primary Key (PK):** Service_ID  
✅ **Foreign Key (FK):** Appointment_ID → Links to **Appointments (Appointment_ID)**

**Recommendations**

\+ Rec_ID (PK)

\+ User_ID (FK)

\+ Efficiency Tips

\+ Solar Panel Recommendation

✅ **Primary Key (PK):** Rec_ID  
✅ **Foreign Key (FK):** User_ID → Links to **User (User_ID)**

**4️⃣ Connect Entities with Relationships**

1. **Select the "Connector" tool** from the **left panel**.
2. **Drag a line from each Foreign Key (FK) to its corresponding Primary Key (PK):**
    - **User → Energy Usage** (User_ID (PK) → User_ID (FK))
    - **User → Carbon Footprint** (User_ID (PK) → User_ID (FK))
    - **Energy Usage → Carbon Footprint** (Energy_ID (PK) → Energy_ID (FK))
    - **User → Appointments** (User_ID (PK) → User_ID (FK))
    - **Appointments → Consultation Service** (Appointment_ID (PK) → Appointment_ID (FK))
    - **User → Recommendations** (User_ID (PK) → User_ID (FK))
3. **Label each relationship** by double-clicking the connecting line and adding:
    - "A user can have multiple energy usage records."
    - "A user can have multiple carbon footprint calculations."
    - "An energy usage record is linked to a carbon footprint."
    - "A user can book multiple appointments for consultations."
    - "Each appointment is linked to a consultation service."
    - "A user can receive multiple energy-saving recommendations."

**5️⃣ Style & Format the Diagram**

1. **Arrange entities neatly** in a **hierarchical order**:
    - **User (Top Center)**
    - **Energy Usage & Appointments (Middle Layer)**
    - **Carbon Footprint, Recommendations, and Consultation Service (Bottom Layer)**
2. **Use colors** for clarity:
    - **User-related entities** → Light Blue
    - **Energy tracking entities** → Light Green
    - **Appointments & Consultation** → Light Yellow
3. **Bold Primary Keys (PK) and Italicize Foreign Keys (FK)** for clarity.

**Supporting Argument for ER Diagram**

The **ER Diagram** for **Rolsa Technologies' Carbon Tracking System** defines the **relationships between key data entities**, ensuring **structured data storage and retrieval**.

- **User Data**: Each **User (PK)** can log **multiple Energy Usage records (FK)**, which link to **Carbon Footprint calculations**.
- **Appointments**: Users can schedule **Appointments (PK, FK: User_ID)**, linked to **Consultation Services**.
- **Recommendations**: The system **analyzes energy trends** and provides **personalized sustainability tips (FK: User_ID)**.
- **Integrity & Security**: **PK-FK constraints** prevent orphaned data, ensuring **GDPR compliance and data validation**.

**1️⃣ Flowchart: User Login & Authentication (Enhanced)**

**Steps to Create in Draw.io**

1. **Start (Oval)** → "Start".
2. **Input (Parallelogram)** → "User enters email & password".
3. **Process (Rectangle)** → "System checks if email exists".
4. **Decision (Diamond)** → "Does email exist?"
    - **No** → "Show error: 'Email not found'" → Loop back to input.
    - **Yes** → Proceed.
5. **Process (Rectangle)** → "System validates password".
6. **Decision (Diamond)** → "Is password correct?"
    - **No** → "Show error: 'Incorrect password'" → Loop back to input.
    - **Yes** → Proceed.
7. **Process (Rectangle)** → "Check if account is locked (Too many failed attempts)".
8. **Decision (Diamond)** → "Is account locked?"
    - **Yes** → "Show error: 'Account locked. Reset required.'" → End.
    - **No** → Proceed.
9. **Process (Rectangle)** → "User is logged in & session starts".
10. **End (Oval)** → "End".

**2️⃣ Flowchart: Energy Usage Input & Carbon Footprint Calculation (Enhanced)**

**Steps to Create in Draw.io**

1. **Start (Oval)** → "Start".
2. **Input (Parallelogram)** → "User enters daily energy usage (kWh)".
3. **Process (Rectangle)** → "System checks data format & range".
4. **Decision (Diamond)** → "Is input valid?"
    - **No** → "Show error message & request valid input" → Loop back.
    - **Yes** → Proceed.
5. **Process (Rectangle)** → "System fetches carbon conversion factors".
6. **Process (Rectangle)** → "Calculate CO₂ emissions using formulas".
7. **Process (Rectangle)** → "Update database with footprint data".
8. **Decision (Diamond)** → "Does user want a monthly report?"
    - **No** → "End".
    - **Yes** → Proceed.
9. **Process (Rectangle)** → "Generate and email monthly footprint report".
10. **End (Oval)** → "End".

**3️⃣ Flowchart: Personalized Recommendations Generation (Enhanced)**

**Steps to Create in Draw.io**

1. **Start (Oval)** → "Start".
2. **Input (Parallelogram)** → "User submits energy data".
3. **Process (Rectangle)** → "System retrieves user energy history".
4. **Process (Rectangle)** → "Compare against efficiency benchmarks".
5. **Decision (Diamond)** → "Is energy consumption above threshold?"
    - **No** → "Show message: 'Great! Your usage is efficient'" → End.
    - **Yes** → Proceed.
6. **Process (Rectangle)** → "Retrieve energy recommendations".
7. **Decision (Diamond)** → "Does user want detailed suggestions?"
    - **No** → "Show brief summary only" → End.
    - **Yes** → Proceed.
8. **Process (Rectangle)** → "Provide step-by-step action plan".
9. **End (Oval)** → "End".

**4️⃣ Flowchart: Appointment Booking System (Enhanced)**

**Steps to Create in Draw.io**

1. **Start (Oval)** → "Start".
2. **Input (Parallelogram)** → "User selects consultation type (Solar, EV, etc.)".
3. **Input (Parallelogram)** → "User selects date & time".
4. **Decision (Diamond)** → "Is slot available?"
    - **No** → "Ask user to select a different date/time" → Loop back.
    - **Yes** → Proceed.
5. **Process (Rectangle)** → "Confirm & save appointment".
6. **Process (Rectangle)** → "Check if consultation requires pre-payment".
7. **Decision (Diamond)** → "Is payment required?"
    - **No** → "Display payment offers" → End.
    - **Yes** → Proceed.
8. **Input (Parallelogram)** → "User completes payment".
9. **Process (Rectangle)** → "Generate payment receiptl".
10. **End (Oval)** → "End".

**5️⃣ Flowchart: Logout Process (Enhanced)**

**Steps to Create in Draw.io**

1. **Start (Oval)** → "Start".
2. **Process (Rectangle)** → "User clicks 'Log Out' button".
3. **Decision (Diamond)** → "Confirm logout?"
    - **No** → "Return to previous page" → End.
    - **Yes** → Proceed.
4. **Process (Rectangle)** → "Clear session data".
5. **Process (Rectangle)** → "Redirect to login page".
6. **End (Oval)** → "End".
