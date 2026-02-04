# RESTful API Activity - Jhonn Carlo

## Best Practices Implementation

*** 1. Environment Variables ***
- Why did we put BASE_URI in .env instead of hardcoding it?

Putting BASE_URI in the .env file allows the application to be easily configurable without modifying the source code. This follows best practices by separating configuration from logic, improves security, and makes the API adaptable to different environments such as development and production.

---

*** 2. Resource Modeling ***
- Why did we use plural nouns (e.g., /dishes) for our routes?

Plural nouns are used to represent collections of resources in RESTful APIs. Using /dishes clearly indicates that the endpoint handles multiple dish resources, making the API more intuitive, consistent, and aligned with REST standards.

---

*** 3. Status Codes ***
- When do we use 201 Created vs 200 OK?

- 201 Created is used when a new resource has been successfully created, such as when adding a new dish.
- 200 OK is used when a request is successful but does not create a new resource, such as fetching, updating, or deleting data.

- Why is it important to return 404 instead of just an empty array or a generic error?

Returning 404 Not Found clearly informs the client that the requested resource does not exist. This improves error handling, avoids confusion, and helps developers and users understand what went wrong.

---

*** 4. Testing ***
*(<img width="428" height="666" alt="Screenshot 2026-01-28 152342" src="https://github.com/user-attachments/assets/952cfb11-3805-4b52-97e6-a9899750c85c" />
)*


