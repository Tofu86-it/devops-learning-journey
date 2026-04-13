# Docker Data Persistence Comparison

## 🎯 Purpose
Understand the differences between image, bind mount, and named volume in Docker.

---

## 1. Image

### Concept
Image stores fixed application content and build-time files.

### Example

```dockerfile
FROM nginx
COPY index.html /usr/share/nginx/html/index.html
```
Characteristics
 - Data is saved in image layers
 - Suitable for fixed content
 - Suitable for versioned deployment
 - Not suitable for runtime-changing data
Best Use Cases
 - Application code
 - Static website files
 - Default configuration
 - Packaged dependencies
2. Bind Mount
Concept

Bind mount maps a host folder directly into a container.

Example
```
services:
  web:
    image: nginx
    volumes:
      - ./html:/usr/share/nginx/html
```
Characteristics
 - Data is stored in host directory
 - Changes on host are reflected immediately in container
 - Easy to inspect and manage with file explorer
 - Good for development and testing
Best Use Cases
 - Frequently edited files
 - Development environment
 - Host-based file management
 - Easy space planning and backup
3. Named Volume
Concept

Named volume is managed by Docker and used for persistent data.

Example
```
services:
  db:
    image: mysql:8
    volumes:
      - db_data:/var/lib/mysql

volumes:
  db_data:
```
Characteristics
 - Data is managed by Docker
 - Not stored in current project directory
 - Suitable for persistent service data
 - Commonly used for databases
Best Use Cases
 - Database files
 - Service persistent data
 - Production-like storage
4. Comparison Table
| Method       | Stored Where           | Suitable For            | Advantages              | Limitations                |
| ------------ | ---------------------- | ----------------------- | ----------------------- | -------------------------- |
| image        | image layers           | fixed content           | versioned, reproducible | not good for changing data |
| bind mount   | host directory         | development files       | easy to edit and manage | depends on host path       |
| named volume | Docker managed storage | persistent service data | clean and stable        | less direct to inspect     |

5. Key Takeaway
 - image = save build-time fixed content
 - bind mount = save files in host directory
 - named volume = save persistent service data managed by Docker
Practical Rule
 - Use image for fixed versioned content
 - Use bind mount for development
 - Use named volume for database or long-term runtime data
