# Week 4: JSON

So far we've only seen HTTP being used to send HTML files (because duh, it's in the name), but HTTP nowadays is used to transfer all kinds of different data. JSON stands for JavaScript Object Notation. Don't let the name fool you, JSON is used in almost every programming language to exchange data. Here, let's take a look at an example of a JSON file:

```json
{
    "glossary": {
        "title": "example glossary",
        "GlossDiv": {
            "title": "S",
            "GlossList": {
                "GlossEntry": {
                    "ID": "SGML",
                    "SortAs": "SGML",
                    "GlossTerm": "Standard Generalized Markup Language",
                    "Acronym": "SGML",
                    "Abbrev": "ISO 8879:1986",
                    "GlossDef": {
                        "para": "A meta-markup language, used to create markup languages such as DocBook.",
                        "GlossSeeAlso": ["GML", "XML"]
                    },
                    "GlossSee": "markup"
                }
            }
        }
    }
}
```
Source: [json.org](https://json.org/example.html)

As you can see that's very similar to a [python dictionary](https://realpython.com/python-dicts/). JSON is used for a lot of different things, but my favorite is that it's able to transfer information from one program to the other -- doesn't matter if they are written in different programming languages or running in different machines.

## Challenge

Like everything in life, there's an official Python library to read JSON files and convert them to Python objects, as well as the other way around (convert Python objects to JSON files). Here's a simple example usage for the following `simple.json` file:

```json
{
    "class": {
        "name": "Math 101",
        "students": ["kelly", "gabe", "shelly"]
    }
}

```

```python
import json

with open("simple.json") as json_file:
    school = json.load(json_file)

    print(school["class"]) # prints the class object

    for student in school["class"]["students"]:
        print(student) # prints each student in the list of students

```

As you can see, in Python the contents of a JSON file are put in a dictionary object. Now let's extend that last JSON file:

```json
{
    "class": {
        "name": "Math 101",
        "teacher": "Mrs. K",
        "students": [
            {
                "name": "kelly",
                "grades": ["1", "10", "5.5"]
            },
            {
                "name": "gabe",
                "grades": ["6", "9", "9"]
            },
            {
                "name": "shelly",
                "grades": ["0", "9", "8.5", "4"]
            }
        ]
    }
}
```

Create a program that takes in a JSON file name (the file is formated like the one above with `class`, `name`s, `teacher`, `students` and `grades`) and prints each student's average grade.

Example:

```bash
$ python3 my_program.py my_json_file.json

kelly: 5.5
gabe: 8
shelly: 7.16
```
