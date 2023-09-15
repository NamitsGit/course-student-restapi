# course-student-restapi
A simple REST API implementation in python with SQLite database to understand the flask-restx API documentation. It demonstrates CRUD operations on a student-course database through flask-restx module in python. 

## Why this app?
This app is created to solve the specific problem of having a database connected REST API in python using flask-restx module.

## About
There are 2 tables in the database namely `Student` and `Course`.

So every student record in the database can be represented by an `id` primary key field,  `name` field and a `course_id` which is the Foreign key (in Student table) refering to the primary key of the course record in the Course table in the database.
These students can choose to enroll in any of the recognized courses. 

The course record in the database can be represented by a `name` field and a `students` list field which keeps track of the student by using their id's. 
If a course does not have any students enrolled in it, it's students list is empty.

The app demonstrates:

  1. Creating new Student/Course records by using POST method.
  2. Reading the list of all the students/courses registered, by using GET method.
  3. Updating an existing Student/Course by using PUT method.
  4. Deleting a specific Student/Course by using DELETE method.

## File description
| Filename | Description |
| :---   | :--- |
| init.py | Used for initializing the app environment. Has the flask app object, SQLAlchemy Database object and flask-restx Api object reprsenting the api.|
| api_models.py | Used for defining a structure for the models of the objects that will be actually used during calls. |
| constants.py | Used for storing constant values like the name of the database. The name of the database can be changed here without disturbing the main logic.|
| extensions.py | Used for creating a Flask SQLAlchemy Database object which will be used to interact with the SQLite database.  |
| models.py | Used for storing the Database models i.e python objects that represent the database objects. |
| resources.py | Main logic of the app where each HTTP request is routed to its specific behaviour through methods in classes.  |

## Steps to run the app
1. Install all the required dependencies by using the command `pip install -r requirements.txt` in terminal/command prompt.
2. Run the flask app by using the command `flask run`. If this does not work you might need to do `pip install dotenv` as we have a config file `.flaskenv` which sets the debugging feature of flask app to True.
