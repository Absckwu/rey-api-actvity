# RESTful API Activity - Jhonn Carlo Rey

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

*** Why did I choose to Embed the [Review/Tag/Log] *** 
- I chose to embed the review/tag/log because it is directly connected to a specific resource and does not need to exist independently. These data usually belong only to one parent record (e.g., a specific dish). Embedding makes it easier and faster to retrieve related information in a single query. It also keeps related data grouped together for better organization.

*** Why did I choose to Reference the [Chef/User/Guest] ***
- I chose to reference the chef/user/guest because they can exist independently from the main resource. One chef or user can be associated with multiple records, so referencing avoids duplication of data. This approach keeps the database more scalable and maintains data consistency. If the chef or user information changes, it only needs to be updated in one place.

***Submission Checklist & README.md Update your README.md with the following questions to prove your understanding:***

1.[ /] Code runs via npm run dev with no errors.
2.[ /] Registration and Login endpoints are functional.
3.[ /] Middleware correctly blocks unauthorized users.
4.[ /] GitHub Repo link submitted.
5.[ /] README.md updated with the following answers: README.md Questions:
README.md Questions:
1. Authentication vs Authorization:
o What is the difference between Authentication and Authorization in our
code?
o Answer: In our system, Authentication refers to confirming the identity of the user. This happens when the system checks the user’s email and password and then generates a JWT token after successful verification. On the other hand, Authorization determines what actions the authenticated user is allowed to perform. It checks the user’s role, such as “admin,” to see if they have permission to access or use a specific route or feature.
2. Security (bcrypt):
o Why did we use bcryptjs instead of saving passwords as plain text in
MongoDB?
o Answer: We use bcryptjs because storing passwords as plain text is highly insecure and can expose users’ credentials if the database is compromised. Bcryptjs enhances security by converting passwords into a hashed version, which protects the original password and makes it much harder for attackers to retrieve or misuse it.
3. JWT Structure:
o What does the protect middleware do when it receives a JWT from the
client?
o Answer:When the protect middleware receives a JWT from the client, it verifies and decodes the token to extract the user’s ID from its payload. The middleware then retrieves the corresponding user information from the database and attaches it to the req.user object. This allows the following route functions to identify who is making the request and apply the appropriate permissions or actions.
