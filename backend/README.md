# Full Stack Trivia API Backend

## Getting Started

### Installing Dependencies

#### Python 3.7

Follow instructions to install the latest version of python for your platform in the [python docs](https://docs.python.org/3/using/unix.html#getting-and-installing-the-latest-version-of-python)

#### Virtual Enviornment

We recommend working within a virtual environment whenever using Python for projects. This keeps your dependencies for each project separate and organaized. Instructions for setting up a virual enviornment for your platform can be found in the [python docs](https://packaging.python.org/guides/installing-using-pip-and-virtual-environments/)

#### PIP Dependencies

Once you have your virtual environment setup and running, install dependencies by naviging to the `/backend` directory and running:

```bash
pip install -r requirements.txt
```

This will install all of the required packages we selected within the `requirements.txt` file.

##### Key Dependencies

- [Flask](http://flask.pocoo.org/)  is a lightweight backend microservices framework. Flask is required to handle requests and responses.

- [SQLAlchemy](https://www.sqlalchemy.org/) is the Python SQL toolkit and ORM we'll use handle the lightweight sqlite database. You'll primarily work in app.py and can reference models.py. 

- [Flask-CORS](https://flask-cors.readthedocs.io/en/latest/#) is the extension we'll use to handle cross origin requests from our frontend server. 

## Database Setup
With Postgres running, restore a database using the trivia.psql file provided. From the backend folder in terminal run:
```bash
psql trivia < trivia.psql
```

## Running the server

From within the `backend` directory first ensure you are working using your created virtual environment.

To run the server, execute:

```bash
export FLASK_APP=flaskr
export FLASK_ENV=development
flask run
```

Setting the `FLASK_ENV` variable to `development` will detect file changes and restart the server automatically.

Setting the `FLASK_APP` variable to `flaskr` directs flask to use the `flaskr` directory and the `__init__.py` file to find the application. 


REVIEW_COMMENT
```

Endpoints

GET '/categories'
- Fetches a dictionary of categories in which the keys are the ids and the value is the corresponding string of the category
- Request Arguments: None
- Returns: An object with a single key, categories, that contains a object of id: category_string key:value pairs. 
{'1' : "Science",
'2' : "Art",
'3' : "Geography",
'4' : "History",
'5' : "Entertainment",
'6' : "Sports"}
  
GET '/questions'
- Fetches an array of questions which contains paginated (every 10 questions) questions of the database 
- Fetches a dictionary of categories in which the keys are the ids and the value is the corresponding string of the category
- Request Arguments: None
- Returns: An object with keys: questions (array of questions), total_questions (num of questions), categories

DELTE '/questions/question_id'
- Fetches an object by its id
- Deletes this question from the database
- Request Arguments: question_id (id of the question needed to be deleted)
- Returns: An object with keys: questions (array of questions), total_questions (num of questions)

POST '/questions'
- Fetches request from the frontend to obatain the new data of the new question
- Inserts the new question into the database
- Request Arguments: question=new_question, answer=new_answer, difficulty=new_difficulty, category=some_category
- Returns: An object with keys: created (id of the new inserted question) , questions : current_questions, the total number of questions

POST '/questions/srch'
- Fetches request from the frontend to obatain the search term
- Selects the suitable questions from the database
- Request Arguments: searchTerm (The key word for searching)
- Returns: An object with key: questions (the suitable questions from the database)

GET '/categories/<current_category>/questions'
- Fetches an array of questions which contains paginated (every 10 questions) questions of the database with the needed category
- Request Arguments: current_category (id of the category)
- Returns: An object with key: questions (the suitable questions from the database)



POST '/quizzes'
- Fetches category and previous question 
- Selects a question from the database with same category and not previous
- Request Arguments: category and previous question 
- Returns: An object with key: currentQuestion (the selected question)


        
        



```


## Testing
To run the tests, run
```
dropdb trivia_test
createdb trivia_test
psql trivia_test < trivia.psql
python test_flaskr.py
```
