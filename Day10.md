Date: July 24, 2026

What I Learned

Today I learned the fundamentals of Spring Security and how it protects Spring Boot applications from unauthorized access.

Key Concepts
Authentication – Verifies who a user is (e.g., username and password).
Authorization – Determines what an authenticated user is allowed to access.
Security Filter Chain – A chain of filters that intercept every HTTP request before it reaches the application.
AuthorizationFilter – Checks whether a user has permission to access a requested resource.
AccessDecisionManager – Makes the final decision to grant or deny access based on the user's roles or authorities.
Spring Cloud Config

I also learned that Spring Cloud Config centralizes configuration files for multiple microservices, making it easier to manage application settings across distributed systems.

Spring MVC Configuration

Spring MVC allows different application contexts to communicate through the DispatcherServlet, which acts as the central controller that routes incoming HTTP requests to the appropriate controllers.

Why Spring Security Matters
Protects sensitive endpoints.
Prevents unauthorized access.
Supports role-based access control.
Integrates seamlessly with Spring Boot applications.
Challenges

Understanding the complete request flow through the Security Filter Chain was initially confusing, but breaking it into smaller steps made it easier to understand.

Key Takeaway

Security isn't just about logging users in—it's about ensuring that every request is authenticated, authorized, and safely processed before reaching the application's business logic.
