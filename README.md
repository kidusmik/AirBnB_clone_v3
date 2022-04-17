![HBNB Cover Image](resources/hbnb-cover.png)

# Project HBNB: AirBnB Clone
This is ALX/Holberton's project **AirBnB Clone**, as the title states it is cloning the AirBnB web application leading towards building full web application: the **AirBnB Clone**

## Project Description

The current aim of the project is to build a terminal that is used to manage and test the objects of our project, such as:

* Create a new object (ex: a new User or a new Place)
* Retrieve an object from a file, a database etc…
* Diplaying an object or all objects from a file, a database etc…
* Do operations on objects (count, compute stats, etc…)
* Update attributes of an object
* Destroy an object

### Classes

| Name | Description |
| --- | --- |
| BaseModel | Defines all common attributes/methods for other classes |
| FileStorage | Serializes instances to a JSON file and deserializes JSON file to instances |
| User | Holds user information |
| State | Holds state information |
| City | Holds city information |
| Amenity | Holds amenity information |
| Place | Holds place information |
| Review | Holds review information |

## The Command Interpreter

The command interpreter is used to perform actions to objects of the classes mentioned above.

### Starting the Terminal

To run the command interpreter, execute the `console.py` file.

```
kidusmik@ubuntu:~AirBnB_clone$ ./console.py
(hbnb) 
```

### Usage

These are lists of commands that can be interpreted by the terminal.

| Command | Syntax | Alternate Syntax | Function |
| --- | --- | --- | --- |
| create | `create <class name>` | `<class name>.create()` | Creates a new instance of the class |
| show | `show <class name> <id>` | `<class name>.show(<id>)` | Prints the string representation of an instance based on the class name |
| destroy | `destroy <class name> <id>` | `<class name>.destroy(<id>)` | Deletes an instance based on the class name and id |
| all | `all` or `all <class name>` | `<class name>.all()` | Prints all string representation of all instances based or not on the class name |
| update | `update <class name> <id> <attribute name> <attribute value>` | `<class name>.update(<id>, <attribute name>, <attribute value>)` or `<class name>.update(<id>, <dictionary representation>)` | Updates an instance based on the class name and id by adding or updating attribute (save the change into the JSON file |
| quit | `quit` | (none) | Exits the console |
| EOF | `Ctrl-D` | (none) | Same as `quit`, exits the console |

### Execution

Execution in `interactive` and `non-interactive` modes.

#### 1. Interactive Mode
```
kidusmik@ubuntu:~AirBnB_clone$ ./console.py
(hbnb) help

Documented commands (type help <topic>):
========================================
EOF  all  count  create  destroy  help  quit  show  update
(hbnb)
```

#### 2. Non-interactive Mode
```
kidusmik@ubuntu:~AirBnB_clone$ echo "help" | ./console.py
(hbnb)

Documented commands (type help <topic>):
========================================
EOF  all  count  create  destroy  help  quit  show  update
(hbnb) 
kidusmik@ubuntu:~AirBnB_clone$
```
```
kidusmik@ubuntu:~AirBnB_clone$ cat test_help
help
kidusmik@ubuntu:~AirBnB_clone$
kidusmik@ubuntu:~AirBnB_clone$ cat test_help | ./console.py
(hbnb)

Documented commands (type help <topic>):
========================================
EOF  all  count  create  destroy  help  quit  show  update
(hbnb) 
kidusmik@ubuntu:~AirBnB_clone$
```

### Example

Here are some examples of the terminal usage.

#### 1. Creating an instance of a class
```
(hbnb) create User
c2e7de07-4c19-4ada-ba23-323cd5c26a5e
(hbnb)
```
```
(hbnb) User.create()
463d9c0f-b356-4f79-9ace-b91374503231
(hbnb)
```
```
(hbnb) all
["[User] (c2e7de07-4c19-4ada-ba23-323cd5c26a5e) {'id': 'c2e7de07-4c19-4ada-ba23-323cd5c26a5e', 'created_at': datetime.datetime(2022, 1, 28, 12, 16, 27, 752995), 'updated_at': datetime.datetime(2022, 1, 28, 12, 16, 27, 753136)}", "[User] (463d9c0f-b356-4f79-9ace-b91374503231) {'id': '463d9c0f-b356-4f79-9ace-b91374503231', 'created_at': datetime.datetime(2022, 1, 28, 12, 16, 31, 593480), 'updated_at': datetime.datetime(2022, 1, 28, 12, 16, 31, 593541)}"]
```

#### 2. Counting number of instances of a class
```
(hbnb) count User
2
(hbnb)
```
```
(hbnb) User.count()
2
(hbnb)
```

#### 3. Showing a single instance of a class
```
(hbnb) show User c2e7de07-4c19-4ada-ba23-323cd5c26a5e
[User] (c2e7de07-4c19-4ada-ba23-323cd5c26a5e) {'id': 'c2e7de07-4c19-4ada-ba23-323cd5c26a5e', 'created_at': datetime.datetime(2022, 1, 28, 12, 16, 27, 752995), 'updated_at': datetime.datetime(2022, 1, 28, 12, 16, 27, 753136)}
(hbnb)
```
```
(hbnb) User.show("c2e7de07-4c19-4ada-ba23-323cd5c26a5e")
[User] (c2e7de07-4c19-4ada-ba23-323cd5c26a5e) {'id': 'c2e7de07-4c19-4ada-ba23-323cd5c26a5e', 'created_at': datetime.datetime(2022, 1, 28, 12, 16, 27, 752995), 'updated_at': datetime.datetime(2022, 1, 28, 12, 16, 27, 753136)}
(hbnb)
```

#### 4. Destroying instances of a class
```
(hbnb) destroy User c2e7de07-4c19-4ada-ba23-323cd5c26a5e
(hbnb)
(hbnb) all
["[User] (463d9c0f-b356-4f79-9ace-b91374503231) {'id': '463d9c0f-b356-4f79-9ace-b91374503231', 'created_at': datetime.datetime(2022, 1, 28, 12, 16, 31, 593480), 'updated_at': datetime.datetime(2022, 1, 28, 12, 16, 31, 593541)}"]
```
```
(hbnb) User.destroy("463d9c0f-b356-4f79-9ace-b91374503231")
(hbnb)
(hbnb) all
[]
(hbnb)
```

#### 5. Showing all instances of all/specific class
```
(hbnb) all
["[User] (7acd5e69-3260-4906-8757-2f77a16fe005) {'id': '7acd5e69-3260-4906-8757-2f77a16fe005', 'created_at': datetime.datetime(2022, 1, 28, 12, 24, 40, 680563), 'updated_at': datetime.datetime(2022, 1, 28, 12, 24, 40, 680657)}", "[User] (841765ce-3727-49b8-8ce5-c0e454a58dac) {'id': '841765ce-3727-49b8-8ce5-c0e454a58dac', 'created_at': datetime.datetime(2022, 1, 28, 12, 24, 42, 915639), 'updated_at': datetime.datetime(2022, 1, 28, 12, 24, 42, 915702)}", "[BaseModel] (5afc1ebe-20f9-41ff-b51c-859f08e6e0ac) {'id': '5afc1ebe-20f9-41ff-b51c-859f08e6e0ac', 'created_at': datetime.datetime(2022, 1, 28, 12, 24, 57, 197423), 'updated_at': datetime.datetime(2022, 1, 28, 12, 24, 57, 197535)}", "[Place] (eb3bf04e-feb8-459e-bceb-fa80cb2bcb1c) {'id': 'eb3bf04e-feb8-459e-bceb-fa80cb2bcb1c', 'created_at': datetime.datetime(2022, 1, 28, 12, 25, 2, 940350), 'updated_at': datetime.datetime(2022, 1, 28, 12, 25, 2, 940417)}"]
(hbnb)
(hbnb) all User
["[User] (7acd5e69-3260-4906-8757-2f77a16fe005) {'id': '7acd5e69-3260-4906-8757-2f77a16fe005', 'created_at': datetime.datetime(2022, 1, 28, 12, 24, 40, 680563), 'updated_at': datetime.datetime(2022, 1, 28, 12, 24, 40, 680657)}", "[User] (841765ce-3727-49b8-8ce5-c0e454a58dac) {'id': '841765ce-3727-49b8-8ce5-c0e454a58dac', 'created_at': datetime.datetime(2022, 1, 28, 12, 24, 42, 915639), 'updated_at': datetime.datetime(2022, 1, 28, 12, 24, 42, 915702)}"]
```
```
(hbnb) User.all()
["[User] (7acd5e69-3260-4906-8757-2f77a16fe005) {'id': '7acd5e69-3260-4906-8757-2f77a16fe005', 'created_at': datetime.datetime(2022, 1, 28, 12, 24, 40, 680563), 'updated_at': datetime.datetime(2022, 1, 28, 12, 24, 40, 680657)}", "[User] (841765ce-3727-49b8-8ce5-c0e454a58dac) {'id': '841765ce-3727-49b8-8ce5-c0e454a58dac', 'created_at': datetime.datetime(2022, 1, 28, 12, 24, 42, 915639), 'updated_at': datetime.datetime(2022, 1, 28, 12, 24, 42, 915702)}"]
(hbnb)
(hbnb) Place.all()
["[Place] (eb3bf04e-feb8-459e-bceb-fa80cb2bcb1c) {'id': 'eb3bf04e-feb8-459e-bceb-fa80cb2bcb1c', 'created_at': datetime.datetime(2022, 1, 28, 12, 25, 2, 940350), 'updated_at': datetime.datetime(2022, 1, 28, 12, 25, 2, 940417)}"]
(hbnb)
```

#### 6. Update an instance of a class
```
(hbnb) Place.all()
["[Place] (eb3bf04e-feb8-459e-bceb-fa80cb2bcb1c) {'id': 'eb3bf04e-feb8-459e-bceb-fa80cb2bcb1c', 'created_at': datetime.datetime(2022, 1, 28, 12, 25, 2, 940350), 'updated_at': datetime.datetime(2022, 1, 28, 12, 25, 2, 940417)}"]
(hbnb)
(hbnb) update Place location "Urban"
(hbnb)
(hbnb) Place.all()
["[Place] (eb3bf04e-feb8-459e-bceb-fa80cb2bcb1c) {'id': 'eb3bf04e-feb8-459e-bceb-fa80cb2bcb1c', 'created_at': datetime.datetime(2022, 1, 28, 12, 25, 2, 940350), 'updated_at': datetime.datetime(2022, 1, 28, 12, 27, 20, 728641), 'location': 'Urban'}"]
(hbnb)
```
```
(hbnb) City.all()
["[City] (bd88ab39-c90c-4efe-bf0e-98555347efa9) {'id': 'bd88ab39-c90c-4efe-bf0e-98555347efa9', 'created_at': datetime.datetime(2022, 1, 28, 12, 28, 41, 419411), 'updated_at': datetime.datetime(2022, 1, 28, 12, 28, 41, 419616)}"]
(hbnb)
(hbnb) City.update("bd88ab39-c90c-4efe-bf0e-98555347efa9", "population_count", 150000)
(hbnb)
(hbnb) City.all()
["[City] (bd88ab39-c90c-4efe-bf0e-98555347efa9) {'id': 'bd88ab39-c90c-4efe-bf0e-98555347efa9', 'created_at': datetime.datetime(2022, 1, 28, 12, 28, 41, 419411), 'updated_at': datetime.datetime(2022, 1, 28, 12, 30, 52, 99814), 'population_count': 150000}"]
```
```
(hbnb) Review.all()
["[Review] (9a97d116-8edf-4478-80e0-b57ad4a6406d) {'id': '9a97d116-8edf-4478-80e0-b57ad4a6406d', 'created_at': datetime.datetime(2022, 1, 28, 16, 37, 17, 970265), 'updated_at': datetime.datetime(2022, 1, 28, 16, 37, 17, 970393)}"]
(hbnb)
(hbnb) Review.update("9a97d116-8edf-4478-80e0-b57ad4a6406d", {'stars': 4.685, 'total_view': 5876, 'user_name': "Kidus Worku"})
(hbnb)
(hbnb) Review.all()
["[Review] (9a97d116-8edf-4478-80e0-b57ad4a6406d) {'id': '9a97d116-8edf-4478-80e0-b57ad4a6406d', 'created_at': datetime.datetime(2022, 1, 28, 16, 37, 17, 970265), 'updated_at': datetime.datetime(2022, 1, 28, 17, 7, 50, 333219), 'stars': 4.685, 'total_view': 5876, 'user_name': 'Kidus Worku'}"]
```

#### Overall Usage Example

```
kidusmik@ubuntu:~AirBnB_clone$ ./console.py
(hbnb) create BaseModel
ae76953c-4f05-4e14-9659-e599cd45a229
(hbnb)
(hbnb) create Place
4e70b774-e1ce-45c6-8993-45e10ce48a46
(hbnb)
(hbnb) show BaseModel 4e70b774-e1ce-45c6-8993-45e10ce48a46
** no instance found **
(hbnb)
(hbnb) show BaseModel ae76953c-4f05-4e14-9659-e599cd45a229
[BaseModel] (ae76953c-4f05-4e14-9659-e599cd45a229) {'id': 'ae76953c-4f05-4e14-9659-e599cd45a229', 'created_at': datetime.datetime(2022, 1, 26, 19, 50, 46, 400369), 'updated_at': datetime.datetime(2022, 1, 26, 19, 50, 46, 400501)}
(hbnb)
(hbnb) create NonExistingClass
** class doesn't exist **
(hbnb) create
** class name missing **
(hbnb) show
** class name missing **
(hbnb) show NonExistingClass
** class doesn't exist **
(hbnb) show BaseModel
** instance id missing **
(hbnb) destroy BaseModel
** instance id missing **
(hbnb)
(hbnb) all
["[BaseModel] (ae76953c-4f05-4e14-9659-e599cd45a229) {'id': 'ae76953c-4f05-4e14-9659-e599cd45a229', 'created_at': datetime.datetime(2022, 1, 26, 19, 50, 46, 400369), 'updated_at': datetime.datetime(2022, 1, 26, 19, 50, 46, 400501)}", "[Place] (4e70b774-e1ce-45c6-8993-45e10ce48a46) {'id': '4e70b774-e1ce-45c6-8993-45e10ce48a46', 'created_at': datetime.datetime(2022, 1, 26, 19, 50, 49, 59166), 'updated_at': datetime.datetime(2022, 1, 26, 19, 50, 49, 59232)}"]
(hbnb)
(hbnb) destroy BaseModel ae76953c-4f05-4e14-9659-e599cd45a229
(hbnb)
(hbnb) all
["[Place] (4e70b774-e1ce-45c6-8993-45e10ce48a46) {'id': '4e70b774-e1ce-45c6-8993-45e10ce48a46', 'created_at': datetime.datetime(2022, 1, 26, 19, 50, 49, 59166), 'updated_at': datetime.datetime(2022, 1, 26, 19, 50, 49, 59232)}"]
(hbnb)
(hbnb) create BaseModel
c37c1765-bd84-4890-90b4-690afffb2b3d
(hbnb)
(hbnb) all
["[Place] (4e70b774-e1ce-45c6-8993-45e10ce48a46) {'id': '4e70b774-e1ce-45c6-8993-45e10ce48a46', 'created_at': datetime.datetime(2022, 1, 26, 19, 50, 49, 59166), 'updated_at': datetime.datetime(2022, 1, 26, 19, 50, 49, 59232)}", "[BaseModel] (c37c1765-bd84-4890-90b4-690afffb2b3d) {'id': 'c37c1765-bd84-4890-90b4-690afffb2b3d', 'created_at': datetime.datetime(2022, 1, 26, 19, 54, 52, 766133), 'updated_at': datetime.datetime(2022, 1, 26, 19, 54, 52, 766219)}"]
(hbnb) all BaseModel
["[BaseModel] (c37c1765-bd84-4890-90b4-690afffb2b3d) {'id': 'c37c1765-bd84-4890-90b4-690afffb2b3d', 'created_at': datetime.datetime(2022, 1, 26, 19, 54, 52, 766133), 'updated_at': datetime.datetime(2022, 1, 26, 19, 54, 52, 766219)}"]
(hbnb)
(hbnb) update
** class name missing **
(hbnb) update BaseModel
** instance id missing **
(hbnb) update BaseModel 4e70b774-e1ce-45c6-8993-45e10ce48a46
** no instance found **
(hbnb) update BaseModel c37c1765-bd84-4890-90b4-690afffb2b3d
** attribute name missing **
(hbnb) update BaseModel c37c1765-bd84-4890-90b4-690afffb2b3d email
** value missing **
(hbnb) update BaseModel c37c1765-bd84-4890-90b4-690afffb2b3d email "kidusmik@gmail.com"
(hbnb)
(hbnb) all
["[Place] (4e70b774-e1ce-45c6-8993-45e10ce48a46) {'id': '4e70b774-e1ce-45c6-8993-45e10ce48a46', 'created_at': datetime.datetime(2022, 1, 26, 19, 50, 49, 59166), 'updated_at': datetime.datetime(2022, 1, 26, 19, 50, 49, 59232)}", "[BaseModel] (c37c1765-bd84-4890-90b4-690afffb2b3d) {'id': 'c37c1765-bd84-4890-90b4-690afffb2b3d', 'created_at': datetime.datetime(2022, 1, 26, 19, 54, 52, 766133), 'updated_at': datetime.datetime(2022, 1, 26, 19, 56, 36, 394426), 'email': 'kidusmik@gmail.com'}"]
(hbnb)
(hbnb) help

Documented commands (type help <topic>):
========================================
EOF  all  count  create  destroy  help  quit  show  update

(hbnb)
(hbnb) help quit
Quit command to exit the program
(hbnb)
(hbnb) quit
kidusmik@ubuntu:~AirBnB_clone$
kidusmik@ubuntu:~AirBnB_clone$ cat file.json ; echo ""
{"Place.4e70b774-e1ce-45c6-8993-45e10ce48a46": {"id": "4e70b774-e1ce-45c6-8993-45e10ce48a46", "created_at": "2022-01-26T19:50:49.059166", "updated_at": "2022-01-26T19:50:49.059232", "__class__": "Place"}, "BaseModel.c37c1765-bd84-4890-90b4-690afffb2b3d": {"id": "c37c1765-bd84-4890-90b4-690afffb2b3d", "created_at": "2022-01-26T19:54:52.766133", "updated_at": "2022-01-26T19:56:36.394426", "email": "kidusmik@gmail.com", "__class__": "BaseModel"}}
kidusmik@ubuntu:~AirBnB_clone$
```

### Testing

To run all the `unittests` run `python3 -m unittest discover tests`:
```
kidusmik@ubuntu:~AirBnB_clone$ python3 -m unittest discover tests
```

Or non-interactively by running `echo "python3 -m unittest discover tests" | bash`:
```
kidusmik@ubuntu:~AirBnB_clone$ echo "python3 -m unittest discover tests" | bash
```

#### `/tests` directory contains all unit test cases for this project:
[/test_models/test_base_model.py](/tests/test_models/test_base_model.py) - Contains the TestBaseModel and TestBaseModelDocs classes
TestBaseModelDocs class:
* `def setUpClass(cls)`- Set up for the doc tests
* `def test_pep8_conformance_base_model(self)` - Test that models/base_model.py conforms to PEP8
* `def test_pep8_conformance_test_base_model(self)` - Test that tests/test_models/test_base_model.py conforms to PEP8
* `def test_bm_module_docstring(self)` - Test for the base_model.py module docstring
* `def test_bm_class_docstring(self)` - Test for the BaseModel class docstring
* `def test_bm_func_docstrings(self)` - Test for the presence of docstrings in BaseModel methods

TestBaseModel class:
* `def test_is_base_model(self)` - Test that the instatiation of a BaseModel works
* `def test_created_at_instantiation(self)` - Test created_at is a pub. instance attribute of type datetime
* `def test_updated_at_instantiation(self)` - Test updated_at is a pub. instance attribute of type datetime
* `def test_diff_datetime_objs(self)` - Test that two BaseModel instances have different datetime objects

[/test_models/test_amenity.py](/tests/test_models/test_amenity.py) - Contains the TestAmenityDocs class:
* `def setUpClass(cls)` - Set up for the doc tests
* `def test_pep8_conformance_amenity(self)` - Test that models/amenity.py conforms to PEP8
* `def test_pep8_conformance_test_amenity(self)` - Test that tests/test_models/test_amenity.py conforms to PEP8
* `def test_amenity_module_docstring(self)` - Test for the amenity.py module docstring
* `def test_amenity_class_docstring(self)` - Test for the Amenity class docstring

[/test_models/test_city.py](/tests/test_models/test_city.py) - Contains the TestCityDocs class:
* `def setUpClass(cls)` - Set up for the doc tests
* `def test_pep8_conformance_city(self)` - Test that models/city.py conforms to PEP8
* `def test_pep8_conformance_test_city(self)` - Test that tests/test_models/test_city.py conforms to PEP8
* `def test_city_module_docstring(self)` - Test for the city.py module docstring
* `def test_city_class_docstring(self)` - Test for the City class docstring

[/test_models/test_file_storage.py](/tests/test_models/test_file_storage.py) - Contains the TestFileStorageDocs class:
* `def setUpClass(cls)` - Set up for the doc tests
* `def test_pep8_conformance_file_storage(self)` - Test that models/file_storage.py conforms to PEP8
* `def test_pep8_conformance_test_file_storage(self)` - Test that tests/test_models/test_file_storage.py conforms to PEP8
* `def test_file_storage_module_docstring(self)` - Test for the file_storage.py module docstring
* `def test_file_storage_class_docstring(self)` - Test for the FileStorage class docstring

[/test_models/test_place.py](/tests/test_models/test_place.py) - Contains the TestPlaceDoc class:
* `def setUpClass(cls)` - Set up for the doc tests
* `def test_pep8_conformance_place(self)` - Test that models/place.py conforms to PEP8.
* `def test_pep8_conformance_test_place(self)` - Test that tests/test_models/test_place.py conforms to PEP8.
* `def test_place_module_docstring(self)` - Test for the place.py module docstring
* `def test_place_class_docstring(self)` - Test for the Place class docstring

[/test_models/test_review.py](/tests/test_models/test_review.py) - Contains the TestReviewDocs class:
* `def setUpClass(cls)` - Set up for the doc tests
* `def test_pep8_conformance_review(self)` - Test that models/review.py conforms to PEP8
* `def test_pep8_conformance_test_review(self)` - Test that tests/test_models/test_review.py conforms to PEP8
* `def test_review_module_docstring(self)` - Test for the review.py module docstring
* `def test_review_class_docstring(self)` - Test for the Review class docstring

[/test_models/state.py](/tests/test_models/test_state.py) - Contains the TestStateDocs class:
* `def setUpClass(cls)` - Set up for the doc tests
* `def test_pep8_conformance_state(self)` - Test that models/state.py conforms to PEP8
* `def test_pep8_conformance_test_state(self)` - Test that tests/test_models/test_state.py conforms to PEP8
* `def test_state_module_docstring(self)` - Test for the state.py module docstring
* `def test_state_class_docstring(self)` - Test for the State class docstring

[/test_models/user.py](/tests/test_models/test_user.py) - Contains the TestUserDocs class:
* `def setUpClass(cls)` - Set up for the doc tests
* `def test_pep8_conformance_user(self)` - Test that models/user.py conforms to PEP8
* `def test_pep8_conformance_test_user(self)` - Test that tests/test_models/test_user.py conforms to PEP8
* `def test_user_module_docstring(self)` - Test for the user.py module docstring
* `def test_user_class_docstring(self)` - Test for the User class docstring

## Bugs
No known bugs at this time. 

## Authors
Alexa Orrico - [Github](https://github.com/alexaorrico) / [Twitter](https://twitter.com/alexa_orrico)  
Jennifer Huang - [Github](https://github.com/jhuang10123) / [Twitter](https://twitter.com/earthtojhuang)

Kidus Worku - [Github](https://github.com/kidusmik) / [Twitter](https://twitter.com/kidusmike)
Elias Fisseha - [Github](https://github.com/) / [Twitter](https://twitter.com/)
