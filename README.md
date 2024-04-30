# AirBnB Clone - The Console

### By Jessica Oviahon & Ugwoke Levi Soromto

"The console is the first segment of the AirBnB project at Holberton School that will collectively cover fundamental concepts of higher level programming. The goal of AirBnB project is to eventually deploy our server a simple copy of the AirBnB Website(HBnB). A command interpreter is created in this segment to manage objects for the AirBnB(HBnB) website.

## Functionalities of this command interpreter:
- Create a new object (ex: a new User or a new Place)
- Retrieve an object from a file, a database, etc...
- Do operations on objects (count, compute stats, etc...)
- Update attributes of an object
- Destroy an object

## Table of Content
1. [Environment](#environment)
2. [Installation](#installation)
3. [File Descriptions](#file-descriptions)
4. [Usage](#usage)
5. [Examples of use](#examples-of-use)
6. [Bugs](#bugs)
7. [Authors](#authors)
8. [License](#license)

---

## Environment
This project is interpreted/tested on Ubuntu 14.04 LTS using python3 (version 3.4.3).

## Installation
1. Clone this repository: `git clone "https://github.com/alexaorrico/AirBnB_clone.git"`
2. Access AirBnb directory: `cd AirBnB_clone`
3. Run hbnb(interactively): `./console` and enter command
4. Run hbnb(non-interactively): `echo "<command>" | ./console.py`

## File Descriptions
- `console.py`: the console contains the entry point of the command interpreter. List of commands this console currently supports:
    - EOF - exits console
    - quit - exits console
    - <emptyline> - overwrites default emptyline method and does nothing
    - create - Creates a new instance ofBaseModel, saves it (to the JSON file) and prints the id
    - destroy - Deletes an instance based on the class name and id (save the change into the JSON file).
    - show - Prints the string representation of an instance based on the class name and id.
    - all - Prints all string representation of all instances based or not on the class name.
    - update - Updates an instance based on the class name and id by adding or updating attribute (save the change into the JSON file).
- `models/` directory contains classes used for this project:
    - `base_model.py`: The BaseModel class from which future classes will be derived
        - `__init__(self, *args, **kwargs)`: Initialization of the base model
        - `__str__(self)`: String representation of the BaseModel class
        - `save(self)`: Updates the attribute updated_at with the current datetime
        - `to_dict(self)`: returns a dictionary containing all keys/values of the instance
    - Classes inherited from Base Model:
        - `amenity.py`
        - `city.py`
        - `place.py`
        - `review.py`
        - `state.py`
        - `user.py`
- `/models/engine` directory contains File Storage class that handles JSON serialization and deserialization :
    - `file_storage.py`: serializes instances to a JSON file & deserializes back to instances
        - `all(self)`: returns the dictionary `__objects`
        - `new(self, obj)`: sets in `__objects` the obj with key `.id`
        - `save(self)`: serializes `__objects` to the JSON file (path: `__file_path`)
        - `reload(self)`: deserializes the JSON file to `__objects`
- `/tests` directory contains all unit test cases for this project:

---

## Usage
```
vagrantAirBnB_clone$./console.py
(hbnb) help

Documented commands (type help <topic>):
========================================
EOF  all  create  destroy  help  quit  show  update

(hbnb) all MyModel
** class doesn't exist **
(hbnb) create BaseModel
7da56403-cc45-4f1c-ad32-bfafeb2bb050
(hbnb) all BaseModel
[[BaseModel] (7da56403-cc45-4f1c-ad32-bfafeb2bb050) {'updated_at': datetime.datetime(2017, 9, 28, 9, 50, 46, 772167), 'id': '7da56403-cc45-4f1c-ad32-bfafeb2bb050', 'created_at': datetime.datetime(2017, 9, 28, 9, 50, 46, 772123)}]
(hbnb) show BaseModel 7da56403-cc45-4f1c-ad32-bfafeb2bb050
[BaseModel] (7da56403-cc45-4f1c-ad32-bfafeb2bb050) {'updated_at': datetime.datetime(2017, 9, 28, 9, 50, 46, 772167), 'id': '7da56403-cc45-4f1c-ad32-bfafeb2bb050', 'created_at': datetime.datetime(2017, 9, 28, 9, 50, 46, 772123)}
(hbnb) destroy BaseModel 7da56403-cc45-4f1c-ad32-bfafeb2bb050
(hbnb) show BaseModel 7da56403-cc45-4f1c-ad32-bfafeb2bb050
** no instance found **
(hbnb) quit
```

## Bugs
No known bugs at this time.

## Authors
- Ugwoke Levi Soromto - Github / Twitter
- Jessica Oviahon - Github / Twitter Jessica Oviahon [github]https://github.com/jessyovia

Second part of Airbnb: Joann Vuong

## License
Public Domain. No copyright protection.
