# 0x00. AirBnB clone - The console

## 0x00.Table of contents

* [0x01 Introduction](#0x01-Introduction)
* [0x02 Environment](#0x02-Environment)
* [0x03 Installation](#0x03-Installation)
* [0x04 Testing](#0x04-Testing)
* [0x05 Usage](#0x05-Usage)
* [0x06 Authors](#0x06-Authors)

## 0x01 Introduction

Team project to build a clone of [AirBnB](https://www.airbnb.com/).

The console is a command interpreter to manage objects abstraction between objects and how they are stored.

To see the fundamental background of the project visit the [Wiki](https://github.com/ralexrivero/AirBnB_clone/wiki).

The console will perform the following tasks:

* create a new object
* retrive an object from a file
* do operations on objects
* destroy an object

### Storage

All the classes are handled by the `Storage` engine in the `FileStorage` Class.

## 0x02 Environment

<!-- ubuntu -->
<a href="https://ubuntu.com/" target="_blank"> <img height="" src="https://img.shields.io/static/v1?label=&message=Ubuntu&color=E95420&logo=Ubuntu&logoColor=E95420&labelColor=2F333A" alt="Suite CRM"></a> <!-- bash --> <a href="https://www.gnu.org/software/bash/" target="_blank"> <img height="" src="https://img.shields.io/static/v1?label=&message=GNU%20Bash&color=4EAA25&logo=GNU%20Bash&logoColor=4EAA25&labelColor=2F333A" alt="terminal"></a> <!-- python--> <a href="https://www.python.org" target="_blank"> <img height="" src="https://img.shields.io/static/v1?label=&message=Python&color=FFD43B&logo=python&logoColor=3776AB&labelColor=2F333A" alt="python"></a> </a> <!-- vim --> <a href="https://www.vim.org/" target="_blank"> <img height="" src="https://img.shields.io/static/v1?label=&message=Vim&color=019733&logo=Vim&logoColor=019733&labelColor=2F333A" alt="Suite CRM"></a> <!-- vs code --> <a href="https://code.visualstudio.com/" target="_blank"> <img height="" src="https://img.shields.io/static/v1?label=&message=Visual%20Studio%20Code&color=5C2D91&logo=Visual%20Studio%20Code&logoColor=5C2D91&labelColor=2F333A" alt="Suite CRM"></a> </a><!-- git --> <a href="https://git-scm.com/" target="_blank"> <img height="" src="https://img.shields.io/static/v1?label=&message=Git&color=F05032&logo=Git&logoColor=F05032&labelColor=2F333A" alt="git distributed version control system"></a> <!-- github --> <a href="https://github.com" target="_blank"> <img height="" src="https://img.shields.io/static/v1?label=&message=GitHub&color=181717&logo=GitHub&logoColor=f2f2f2&labelColor=2F333A" alt="Github"></a>
 <!-- Style guidelines -->
* Style guidelines:
  * [pycodestyle (version 2.7.*)](https://pypi.org/project/pycodestyle/)
  * [PEP8](https://pep8.org/)

All the development and testing was runned over an operating system Ubuntu 20.04 LTS using programming language Python 3.8.3. The editors used were VIM 8.1.2269, VSCode 1.6.1 and Atom 1.58.0 . Control version using Git 2.25.1.

## 0x03 Installation

```bash
git clone https://github.com/insidemordecai/AirBnB_clone.git
```

change to the `AirBnb` directory and run the command:

```bash
 ./console.py
```

### Execution

In interactive mode

```bash
$ ./console.py
(hbnb) help

Documented commands (type help <topic>):
========================================
EOF  help  quit

(hbnb)
(hbnb)
(hbnb) quit
$
```

in Non-interactive mode

```bash
$ echo "help" | ./console.py
(hbnb)

Documented commands (type help <topic>):
========================================
EOF  help  quit
(hbnb)
$
$ cat test_help
help
$
$ cat test_help | ./console.py
(hbnb)

Documented commands (type help <topic>):
========================================
EOF  help  quit
(hbnb)
$
```

## 0x04 Testing

All the test are defined in the `tests` folder.

### Documentation

* Modules:

```python
python3 -c 'print(__import__("my_module").__doc__)'
```

* Classes:

```python
python3 -c 'print(__import__("my_module").MyClass.__doc__)'
```

* Functions (inside and outside a class):

```python
python3 -c 'print(__import__("my_module").my_function.__doc__)'
```

and

```python
python3 -c 'print(__import__("my_module").MyClass.my_function.__doc__)'
```

### Python Unit Tests

* unittest module
* File extension ``` .py ```
* Files and folders star with ```test_```
* Organization:for ```models/base.py```, unit tests in: ```tests/test_models/test_base.py```
* Execution command: ```python3 -m unittest discover tests```
* or: ```python3 -m unittest tests/test_models/test_base.py```

### run test in interactive mode

```bash
echo "python3 -m unittest discover tests" | bash
```

### run test in non-interactive mode

To run the tests in non-interactive mode, and discover all the test, you can use the command:

```bash
python3 -m unittest discover tests
```


## 0x05 Usage

* Start the console in interactive mode:

```bash
$ ./console.py
(hbnb)
```

* Use help to see the available commands:

```bash
(hbnb) help

Documented commands (type help <topic>):
========================================
EOF  all  count  create  destroy  help  quit  show  update

(hbnb)
```

* Quit the console:

```bash
(hbnb) quit
$
```

### Commands

> The commands are displayed in the following format *Command / usage / example with output*

* Create

> *Creates a new instance of a given class. The class' ID is printed and the instance is saved to the file file.json.*

```bash
create <class>

```

```bash
(hbnb) create BaseModel
e573d0eb-2dcb-44cf-9751-217f8671d328
(hbnb)
```

* Show

```bash
show <class> <id>
```

```bash
(hbnb) show BaseModel e573d0eb-2dcb-44cf-9751-217f8671d328
[BaseModel] (e573d0eb-2dcb-44cf-9751-217f8671d328) {'id': 'e573d0eb-2dcb-44cf-9751-217f8671d328', 'created_at': datetime.datetime(2023, 2, 13, 2, 29, 53, 833978), 'updated_at': datetime.datetime(2023, 2, 13, 2, 29, 53, 833978)}
(hbnb)
```

* Destroy

> *Deletes an instance of a given class with a given ID.*
> *Update the file.json*

```bash
(hbnb) create User
57971426-3f2f-4f47-8496-c1e6cce29889
(hbnb) destroy User 57971426-3f2f-4f47-8496-c1e6cce29889
(hbnb) show User 57971426-3f2f-4f47-8496-c1e6cce29889
** no instance found **
(hbnb)
```

* all

> *Prints all string representation of all instances of a given class.*
> *If no class is passed, all classes are printed.*

```bash
(hbnb) create BaseModel
44637f9a-46ab-4dcd-9628-db6784ddf550
(hbnb) all BaseModel
["[BaseModel] (307056ba-69a0-49e3-89c5-97ff7f95a65c) {'id': '307056ba-69a0-49e3-89c5-97ff7f95a65c', 'created_at': datetime.datetime(2023, 2, 13, 2, 18, 46, 904067), 'updated_at': datetime.datetime(2023, 2, 13, 2, 18, 46, 908916), 'name': 'My First Model', 'my_number': 89}", "[BaseModel] (e41a8f4f-756d-4f27-b09d-65a85aaffbb1) {'id': 'e41a8f4f-756d-4f27-b09d-65a85aaffbb1', 'created_at': datetime.datetime(2023, 2, 13, 2, 22, 18, 737989), 'updated_at': datetime.datetime(2023, 2, 13, 2, 22, 18, 737989)}", "[BaseModel] (e573d0eb-2dcb-44cf-9751-217f8671d328) {'id': 'e573d0eb-2dcb-44cf-9751-217f8671d328', 'created_at': datetime.datetime(2023, 2, 13, 2, 29, 53, 833978), 'updated_at': datetime.datetime(2023, 2, 13, 2, 29, 53, 833978)}", "[BaseModel] (44637f9a-46ab-4dcd-9628-db6784ddf550) {'id': '44637f9a-46ab-4dcd-9628-db6784ddf550', 'created_at': datetime.datetime(2023, 2, 13, 2, 33, 31, 113385), 'updated_at': datetime.datetime(2023, 2, 13, 2, 33, 31, 113385)}"]
(hbnb)
```

* count

> *Prints the number of instances of a given class.*

```bash
(hbnb) create City
9793b2ed-be52-4bec-a4a3-71f718950b17
(hbnb) create City
454c3669-77ce-412b-aebb-cde821e5216e
(hbnb) count City
4
(hbnb)
```

* update

> *Updates an instance based on the class name, id, and kwargs passed.*
> *Update the file.json*

```bash
(hbnb) create User
2d09b40d-eef5-4644-baa2-28cc599a24b7
(hbnb) update User 2d09b40d-eef5-4644-baa2-28cc599a24b7 email "aniekemeumoren@gmail.com"
(hbnb) show User 2d09b40d-eef5-4644-baa2-28cc599a24b7
[User] (2d09b40d-eef5-4644-baa2-28cc599a24b7) {'id': '2d09b40d-eef5-4644-baa2-28cc599a24b7', 'created_at': datetime.datetime(2023, 2, 13, 2, 38, 52, 853556), 'updated_at': datetime.datetime(2023, 2, 13, 2, 38, 52, 853556), 'email': 'aniekemeumoren@gmail.com'}
(hbnb)

```
## Authors
<details>
    <summary>Mordecai Kipng'etich</summary>
    <ul>
    <li><a href="https://www.github.com/insidemordecai">Github</a></li>
    <li><a href="https://www.twitter.com/insidemordecai">Twitter</a></li>
    </ul>
</details>
<details>
    <summary>Aniekeme Umoren</summary>
    <ul>
    <li><a href="https://www.github.com/Aniekeme1">Github</a></li>
    <li><a href="https://www.twitter.com/Anie_keme">Twitter</a></li>
    <li><a href="mailto:aniekemeumoren@gmail.com">e-mail</a></li>
    </ul>
</details>

