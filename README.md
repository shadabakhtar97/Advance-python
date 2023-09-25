# Advance-python
Learn About Advance Python in Deep Dive

### What Is a Django Web Framework?

Django is a high-level, open-source web framework written in Python that facilitates the development of web applications and websites. It follows the Model-View-Controller (MVC) architectural pattern, which is often referred to as the Model-View-Template (MVT) pattern in Django's context. Django is designed to simplify and accelerate the creation of complex, database-driven websites by providing a robust set of tools and features.

Here are some key components and features of the Django web framework:

1. **ORM (Object-Relational Mapping)**: Django includes its own Object-Relational Mapping system, which allows developers to interact with the database using Python objects instead of raw SQL queries. This makes database interactions more Pythonic and abstracts the underlying database engine.

2. **Admin Panel**: Django provides a built-in admin interface that makes it easy to create, read, update, and delete data in the database. This is a powerful feature for managing the content of a web application without having to build custom admin interfaces.

3. **URL Routing**: Django uses a URL dispatcher that maps URL patterns to views. This makes it straightforward to define the URL structure of your application and connect it to specific functions or classes (views) that handle the user's requests.

4. **Template Engine**: Django includes a template system for creating dynamic HTML templates. These templates allow you to separate the presentation layer from the application logic, promoting code reusability and maintainability.

5. **Authentication and Authorization**: Django provides built-in tools for user authentication and authorization, including user management, access control, and session management.

6. **Security**: Django is designed with security in mind and includes built-in features to protect against common web application vulnerabilities, such as Cross-Site Scripting (XSS), Cross-Site Request Forgery (CSRF), and SQL injection.

7. **Middleware**: Django's middleware components allow you to process requests and responses globally across your application, enabling tasks like authentication, logging, and more.

8. **Form Handling**: Django simplifies form handling and validation, making it easy to create and process HTML forms while also protecting against common form-related security issues.

9. **Database Abstraction**: Django supports various database backends, including PostgreSQL, MySQL, SQLite, and Oracle, allowing developers to choose the database that best suits their application's needs.

10. **Scalability**: Django's architecture supports the development of scalable web applications. It can be used for both small projects and large-scale, high-traffic websites.

11. **Community and Packages**: Django has a large and active community of developers, which means there are numerous third-party packages and extensions available to extend its functionality.

Overall, Django is known for its "batteries-included" philosophy, which means it provides a wide range of built-in features and tools, allowing developers to focus on building their applications rather than reinventing the wheel. It's a popular choice for web developers because of its efficiency, robustness, and the wealth of resources available in its ecosystem.

### --------------------------------------------------------------------------------------------------------------------
### Python	The MVC & MVT Design Pattern
In Python web development, the MVC (Model-View-Controller) and MVT (Model-View-Template) design patterns are commonly used to structure web applications. These patterns help organize code and separate concerns, making it easier to develop and maintain web applications. Let's explore both patterns in Python:

1. **MVC (Model-View-Controller):**
   
   MVC is a design pattern that separates an application into three interconnected components:

   - **Model**: This represents the data and business logic of the application. It interacts with the database, processes data, and performs computations. In Python, you can use libraries like SQLAlchemy or Django's ORM to work with databases and define models.

   - **View**: The view is responsible for rendering the user interface and presenting data to the user. In a web application, views are typically implemented as templates that define how data is displayed to the user. Popular Python frameworks like Django and Flask use template engines like Jinja2 or their own templating systems.

   - **Controller**: The controller acts as an intermediary between the Model and View. It handles user input, processes requests, and communicates with the Model to retrieve or update data. In Python web frameworks like Django, this role is often fulfilled by the views or the routing mechanism.

   Here's a simple example using the Flask framework:

   ```python
   from flask import Flask, render_template

   app = Flask(__name__)

   # Model
   class Item:
       def __init__(self, name, price):
           self.name = name
           self.price = price

   items = [Item("Item 1", 10), Item("Item 2", 20)]

   # Controller
   @app.route('/')
   def index():
       return render_template('index.html', items=items)

   # View (index.html)
   # Display items
   # <html>...</html>

   if __name__ == '__main__':
       app.run()
   ```

2. **MVT (Model-View-Template):**

   MVT is a design pattern specifically used in Django, a popular Python web framework. It's similar to MVC but with some terminology differences:

   - **Model**: The Model in Django represents the data structure and database schema. It defines how data is stored and retrieved from the database.

   - **View**: In Django, the View is responsible for processing incoming HTTP requests and returning HTTP responses. It can include business logic and communicates with the Model to retrieve or modify data.

   - **Template**: The Template is the equivalent of the View in the traditional MVC pattern. It defines how the data is presented to the user in HTML format. Django uses its own template engine.

   Here's a simple Django example:

   ```python
   # models.py
   from django.db import models

   class Item(models.Model):
       name = models.CharField(max_length=100)
       price = models.DecimalField(max_digits=5, decimal_places=2)

   # views.py
   from django.shortcuts import render
   from .models import Item

   def index(request):
       items = Item.objects.all()
       return render(request, 'index.html', {'items': items})

   # templates/index.html
   # Display items
   # <html>...</html>
   ```

In both MVC and MVT, the main idea is to separate concerns, making your code more maintainable and easier to scale. The choice between these patterns often depends on the specific web framework you are using. Django, for instance, enforces the use of the MVT pattern, while other frameworks like Flask provide more flexibility to choose between MVC or other patterns based on your project's needs.

### --------------------------------------------------------------------------------------------------------------------
### Django’s History
Django is a high-level Python web framework that was created to simplify web development and promote best practices. Its history dates back to the early 2000s, and it has since become one of the most popular web frameworks for building robust and scalable web applications. Here's an overview of Django's history:

1. **Development Begins (2003)**:
   - Django's development started at the Lawrence Journal-World newspaper in Lawrence, Kansas, USA.
   - The project was initiated by Adrian Holovaty and Simon Willison as a tool to help journalists and developers build web applications quickly and efficiently.

2. **Publicly Released (2005)**:
   - Django was publicly released in July 2005 as an open-source project under the BSD license.
   - The release included a set of core components that are still central to Django today, such as the ORM (Object-Relational Mapping) system, the templating engine, and the administrative interface.

3. **Django Software Foundation (2008)**:
   - In 2008, the Django Software Foundation (DSF) was established to promote, support, and advance the development of Django.
   - The DSF has played a significant role in managing the project's resources, organizing events, and ensuring its long-term sustainability.

4. **Major Releases**:
   - Django follows a regular release schedule, with major releases every 9-12 months and frequent minor updates. Some notable major releases include:
     - Django 1.0 (2008): A significant milestone, marking the framework's stability and maturity.
     - Django 1.2 (2010): Introduced a built-in support for internationalization and localization.
     - Django 1.3 (2011): Added support for class-based views.
     - Django 1.4 (2012): Included support for time zones and static file handling.
     - Django 1.8 (2015): Brought major improvements to the ORM, including the introduction of built-in support for database migrations.
     - Django 2.0 (2017): Dropped support for Python 2, making Python 3 the minimum required version.
     - Django 3.0 (2019): Introduced asynchronous views and support for Python 3.6+.

5. **Community Growth**:
   - Django has a vibrant and active community of developers, which has contributed to its continuous improvement and popularity.
   - The Django community organizes conferences, sprints, and documentation efforts to support and expand the framework's ecosystem.

6. **Django REST framework**:
   - Django REST framework, an extension for building RESTful APIs, has become an essential part of the Django ecosystem. It provides powerful tools for creating web APIs quickly.

7. **Current Status (2021)**:
   - As of my last knowledge update in September 2021, Django was actively maintained and widely used by developers worldwide.
   - The latest version at that time was Django 3.2 LTS (Long-Term Support), with Django 4.0 in development.

Please note that developments in the Django framework may have occurred since my last knowledge update in September 2021. You can visit the official Django website (https://www.djangoproject.com/) for the most up-to-date information and to track the latest releases and developments in the Django community.


### --------------------------------------------------------------------------------------------------------------------
# Installing Django on windows 10
To install Django on Windows 10, you can follow these steps:

1. **Install Python:** Django is a Python web framework, so you need Python installed on your system. You can download Python for Windows from the official website (https://www.python.org/downloads/windows/) and follow the installation instructions. Make sure to check the box that says "Add Python X.Y to PATH" during installation (X.Y represents the Python version you're installing).

2. **Open Command Prompt:** Once Python is installed, open Command Prompt by searching for "cmd" or "Command Prompt" in the Windows Start menu.

3. **Create a Virtual Environment (Optional but Recommended):** It's a good practice to create a virtual environment to isolate your Django project's dependencies. To create a virtual environment, run the following command in Command Prompt:

   ```bash
   python -m venv myenv
   ```

   Replace "myenv" with the name you want to give to your virtual environment.

4. **Activate the Virtual Environment:** To activate the virtual environment, run the appropriate command based on your Command Prompt version:

   For Command Prompt:
   ```bash
   myenv\Scripts\activate
   ```

   For PowerShell:
   ```bash
   .\myenv\Scripts\Activate.ps1
   ```

5. **Install Django:** With the virtual environment activated, you can now install Django using pip:

   ```bash
   pip install django
   ```

6. **Verify Django Installation:** To verify that Django has been installed correctly, you can check its version with the following command:

   ```bash
   python -m django --version
   ```

   This should display the installed Django version.

Now, Django is installed on your Windows 10 system, and you're ready to start creating Django projects and applications. Make sure to deactivate the virtual environment when you're done working on your Django project by running:

```bash
deactivate
```

That's it! You're all set to begin developing with Django on Windows 10.
