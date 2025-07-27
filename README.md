# Order Management System API

A comprehensive Order Management System built with .NET 8, implementing Onion Architecture, SOLID principles, and various design patterns.

## Features

- **Customer Management**: Create customers and view their order history
- **Product Management**: CRUD operations for products with stock management
- **Order Processing**: Create orders with automatic stock validation and tiered discounts
- **Invoice Generation**: Automatic invoice creation for completed orders
- **User Authentication**: JWT-based authentication with role-based access control
- **Email Notifications**: Automated email notifications for order status changes
- **Tiered Discounts**: Automatic discount application (5% for orders >$100, 10% for orders >$200)
- **Multiple Payment Methods**: Support for Credit Card, PayPal, Bank Transfer, and Cash

## Architecture

The project follows **Onion Architecture** with clear separation of concerns:

### Layers

1. **Domain Layer** (`OrderManagementSystem.Domain`)
   - Entities (Customer, Order, OrderItem, Product, Invoice, User)
   - Value Objects (Money)
   - Enums (PaymentMethod, OrderStatus, UserRole)
   - Domain Services (DiscountService)
   - Repository Interfaces

2. **Application Layer** (`OrderManagementSystem.Application`)
   - Application Services
   - DTOs (Data Transfer Objects)
   - AutoMapper Profiles
   - Service Interfaces

3. **Infrastructure Layer** (`OrderManagementSystem.Infrastructure`)
   - Repository Implementations
   - Entity Framework DbContext
   - External Service Implementations (Email, JWT)
   - Data Access Logic

4. **Presentation Layer** (`OrderManagementSystem.Api`)
   - Web API Controllers
   - Middleware
   - Dependency Injection Configuration
   - Swagger Documentation

## Design Patterns Implemented

- **Repository Pattern**: Abstracts data access logic
- **Unit of Work Pattern**: Coordinates transactions across multiple repositories
- **Dependency Injection**: Manages dependencies between components
- **Strategy Pattern**: Used for different payment methods and discount calculations
- **Factory Method**: For creating complex objects
- **CQRS Concepts**: Separation of read and write operations

## SOLID Principles

- **Single Responsibility**: Each class has a single, well-defined responsibility
- **Open/Closed**: Classes are open for extension but closed for modification
- **Liskov Substitution**: Derived classes can be substituted for their base classes
- **Interface Segregation**: Clients depend only on interfaces they use
- **Dependency Inversion**: High-level modules don't depend on low-level modules
