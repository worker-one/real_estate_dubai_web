### **Web Application for Real Estate Evaluation**

### **User Flow**

#### **1. Main Screen:**
- **Headline (Center-Aligned):**  
  "Сделать оценку недвижимости" / "Make evaluation of your property"
- **Button (Center-Aligned):**  
  "Начать" / "Begin"

#### **2. Building Selection Screen:**
- **Headline:**  
  "Укажите название здания:" / "Choose your building"
- **Input Field (Placeholder):**  
  "Введите текст" / "Start typing"  
  - User starts typing a building name.
  - A dropdown appears with suggestions from the database, matching `project_name_en` and displaying the corresponding `master_project_en`.  
  Example: _"La Sirene, La Mer"_

#### **3. Bedroom Selection Screen:**
- **Headline:**  
  "Укажите количество спален:" / "Choose number of beds"
- **Dropdown Menu (Dynamic):**
  - Options: `Studio`, `1 bedroom`, `2 bedroom`, `3 bedroom`, `4 bedroom`
  - The system only displays available options based on the building selected from the database (`rooms_en`).  
  If, for example, there’s no `Studio` in the data for a particular building, it won’t be shown.

#### **4. Evaluation Results Screen:**
- **Headline:**  
  "Результат оценки" / "Evaluation results and summary:"
- **Content:**  
  - **Building:** La Sirene, La Mer  
  - **Bedrooms:** 1 bedroom  
  - **Type:** Flat  
  - **Size:** 75 sqm / 807 sqft  
  - **Price per sqm:** 10,000 AED  
  - **Price per sqft:** 2,000 AED

- **Additional Information:**
- - **Property Type:** From `property_sub_type_en`
- - **Area (sqm):** Average from `procedure_area` based on the selected building and apartment type.
- - **Area (sqft):** Convert sqm to sqft (multiply sqm by 10.76).
- - **Price per sqm:** Average apartment price divided by the average area (in square meters).
- - **Price per sqft:** Average apartment price divided by the average area (in square feet).

#### **5. Current Estimation:**
- **Headline:**  
  "Текущая оценка:" / "Current estimation:"
- **Estimated Value (AED):**  
  Displays the average value from `actual_worth` for all 1-bedroom units in the building _La Sirene, La Mer_ (e.g., "2,000,000 AED").

#### **6. Call to Action:**
- **Buttons:**  
  - "Сделайте более точную оценку" / "Request more precise evaluation"  
  - "Заказать" / "Order"  
  - Clicking "Order" sends a prefilled WhatsApp message to the number +971551742540 with the message:  
    _“Hi, I need more precise evaluation of my 1 bedroom in La Sirene, La Mer. Please make evaluation.”_

---

### **7. Detailed Table View:**
- **Headline:**  
  Table displaying all available data for the selected building (`project_name_en`), with columns:
  - **Date:** `instance_date`
  - **Transaction Type:** `trans_group_en`
  - **Sub-Type:** `procedure_name_en`
  - **Bedrooms:** `rooms_en`
  - **Size (sqm):** `procedure_area`
  - **Price (AED or USD):** `actual_worth`
  - **Price per sqm/sqft:** Calculated as `actual_worth` divided by `procedure_area`


### **Functional Requirements**

#### ** Design:**
Ensure full responsiveness for mobile and desktop users. Color schema: https://coolors.co/d6d8da-d6d8da-f5f5f4-ff904d-000000
- font color : `000000`
- main color :` d6d8da`
- secondery color : `f5f5f4`
- accent color : `ff904d`

Fonts:
- main font: `Tw Cen MT`
- accent font: `Tw Cen MT Bald`

#### ** Multilingual Support:**
Support Russian and English languages with seamless switching.

#### ** Main Screen:**
**"Begin" Button:** Redirects to building selection screen.

#### ** Building Selection:**
**Search Input:** Suggests building names (`project_name_en`) as the user types, displaying `master_project_en` details. **Dynamic Suggestions:** Populate data from the database in real-time.

#### ** Bedroom Selection:**
**Dynamic Dropdown:** Display only available bedroom options (`rooms_en`) for the selected building.

#### ** Evaluation Calculation:**
**Size and Price:** Calculate and display average size (`procedure_area`) and price (`actual_worth`) for the chosen building. **Price per sqm/sqft:** Calculate dynamically, converting sqm to sqft (sqm * 10.76).

#### ** Current Estimation:**
Display the average property value (`actual_worth`) for selected building and room type.

#### ** Call to Action:**
**WhatsApp Button:** Sends a predefined message to +971551742540 with selected property details.

#### ** Data Table:**
Display data for the selected building with columns:  
  - Date (`instance_date`), Type (`trans_group_en`), Sub-Type (`procedure_name_en`), Beds (`rooms_en`), Size (`procedure_area`), Price (`actual_worth`), Price per sqm/sqft.

#### ** Currency and Unit Switcher:**
Toggle between AED/USD and sqm/sqft.

#### ** Backend Requirements:**
**Database:** Connect to real-time database for building and property details.

#### ** Error Handling:**
Display friendly error messages for empty datasets and validate all inputs.

#### ** Security:**
Encrypt data transactions and sanitize all user inputs to prevent security vulnerabilities.


### Attachments

[1] Исходное ТЗ: https://docs.google.com/document/d/1-2qSFdwdxLaMyOb1Sd7aeldyuxMiZTJG/edit?usp=sharing&ouid=116826442056623255845&rtpof=true&sd=true

[2] Макет: https://drive.google.com/file/d/1-4k53fp5QLMXjtXBFX58ysElr4G6qyvq/view?usp=sharing
