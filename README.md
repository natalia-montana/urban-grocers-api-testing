Urban Grocers: Backend API Testing
A rigorous Quality Assurance project dedicated to verifying the microservices and data validation constraints of the Urban Grocers platform using Postman and Jira.

Author & Professional Profile
Natalia Montana | QA Engineer & Data Analytics Specialist | Bogota, Colombia

API Data Structures (Requirement 1: Kits)
Case 1: Positive Test Case Example (Valid Payload)
Scenario: Adding existing products to an active kit under the 30-item limit constraint.

Payload Structure: An array of objects where ID represents unique products, and quantity tracks total volume.

{
"productsList": [
{ "id": 1, "quantity": 2 },
{ "id": 6, "quantity": 2 }
]
}

Case 2: Negative Test Case Example (Boundary Limit Exceeded)
Scenario: Attempting to bypass the architecture constraint by introducing 31 unique product IDs into a single kit structure.

Payload Constraint: The backend tracks unique IDs; total quantities do not alter this unique item counter.

{
"productsList": [
{ "id": 1, "quantity": 1 }, { "id": 2, "quantity": 1 }, { "id": 3, "quantity": 1 },
{ "id": 4, "quantity": 1 }, { "id": 5, "quantity": 1 }, { "id": 6, "quantity": 1 },
{ "id": 7, "quantity": 1 }, { "id": 8, "quantity": 1 }, { "id": 9, "quantity": 1 },
{ "id": 10, "quantity": 1 }, { "id": 11, "quantity": 1 }, { "id": 12, "quantity": 1 },
{ "id": 13, "quantity": 1 }, { "id": 14, "quantity": 1 }, { "id": 15, "quantity": 1 },
{ "id": 16, "quantity": 1 }, { "id": 17, "quantity": 1 }, { "id": 18, "quantity": 1 },
{ "id": 19, "quantity": 1 }, { "id": 20, "quantity": 1 }, { "id": 21, "quantity": 1 },
{ "id": 22, "quantity": 1 }, { "id": 23, "quantity": 1 }, { "id": 24, "quantity": 1 },
{ "id": 25, "quantity": 1 }, { "id": 26, "quantity": 1 }, { "id": 27, "quantity": 1 },
{ "id": 28, "quantity": 1 }, { "id": 29, "quantity": 1 }, { "id": 30, "quantity": 1 },
{ "id": 31, "quantity": 1 }
]
}  

Expected System Behavior (Error Enforcement)
Testing Strategy: Boundary Value Analysis (BVA) + 1 Parameter.

Status Code Expected: 400 Bad Request

Response Body Expected:
{
"code": 400,
"message": "No mas de 30 articulos por conjunto"
}
