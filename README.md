# Urban Grocers: Backend API Testing & Business Logic Validation

A rigorous, database-focused Quality Assurance project dedicated to verifying the microservices, endpoint behaviors, and data validation constraints of the Urban Grocers platform. This phase transitions from UI testing into pure backend validation using programmatic HTTP environments.

---

## 🛠️ Author & Professional Profile
**Natalia Montaña** *QA Engineer & Data Analytics Specialist* | Bogotá, Colombia  
[LinkedIn](https://linkedin.com) | [GitHub](https://github.com/natalia-montana)

---

## 🔬 Scope of Verification & Core Architecture
This engineering phase maps out the system rules and error thresholds for key data management features:
* **Requirement 1 (Kits Integration):** Boundary value analysis and data-type validation for appending arrays of products to predefined kit clusters via `POST /api/v1/kits/:id/products`.
* **Requirement 2 (Delivery Calculations):** Algorithmic verification of the "Order and Go" state machine, ensuring numeric inputs govern cost allocations and shipment feasibility parameters.

---

## 💻 API Data Structures & JSON Payloads (Requirement 1)

To thoroughly validate the ecosystem rules, tests were systematically executed using structured JSON payloads to confirm how backend data parameters enforce technical constraints.

### 🟢 Positive Test Case Example (Valid Payload)
* **Scenario:** Adding existing products to an active kit under the 30-item limit constraint.
* **Payload Structure:** An array of objects where `id` represents unique products, and `quantity` tracks total volume.

```json
{
    "productsList": [
        {
            "id": 1,
            "quantity": 2
        },
        {
            "id": 6,
            "quantity": 2
        }
    ]
}
