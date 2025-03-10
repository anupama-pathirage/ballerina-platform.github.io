---
layout: ballerina-left-nav-pages
title: Coding Conventions
description: The Ballerina Style Guide aims at maintaining a standard coding style among the Ballerina community. The Ballerina code formatting tools are based on this guide.
keywords: ballerina, programming language, ballerina style guide
permalink: /1.2/learn/coding-conventions/
active: coding-conventions
intro: This Ballerina Style Guide aims at maintaining a standard coding style among the Ballerina community. Therefore, the Ballerina code formatting tools are based on this guide.
redirect_from:
  - /1.2/learn/style-guide
  - /1.2/learn/style-guide/
  - /v1-2/learn/style-guide
  - /v1-2/learn/style-guide/
  - /1.2/learn/coding-conventions
---

> You can follow your own coding style when writing Ballerina source code. Also, plugins and tools can be configured to match your coding style.

## Indentation and Line Length
* Use four spaces (not tabs) for each level of indentation.
* Keep the maximum length of a line to 120 characters. 

> **Note:** You can configure tools and plugins to use tabs when indenting and to change the number of maximum characters of the line length.

## Line Spacing

* Use only a single space to separate keywords, types, and identifiers. 
   
**Do's**

```ballerina
public function getFullName() returns string {
    string fullName = "john doe";
    return fullName;
}
```

**Don'ts**

```ballerina
public   function   getFullName()   returns   string {
    string   fullName = "john doe";
    return     fullName;
}
```

Few exceptions for this rule are:
- Do not keep spaces around a type when it is enclosed using angle brackets `<string>`. 
      
**Example,**

```ballerina
map<string> names = {};
```

- Do not keep spaces between the type and the opening bracket in the array definition `string[]`.
      
**Example,**

```ballerina
    string[] names = [];
```

* If it is a list of values separated by commas, add only a single space after each comma and don't add spaces before the comma.
  
**Example,**

```ballerina
[string, int, boolean] tupleVar = ["", 0, false];
    
int[] arrayOfInteger = [1, 2, 3, 4];
    
map<string> stringMap = {one: st1, two: st2, three: st3};
    
Person personRecord = {name:"marcus", id: 0};
    
function foo(string name, int id) {}
    
service hello on ep1, ep2 {...}
```

## Blank Lines

Separate both statements and top-level definitions by zero or one blank lines.

**Example,**
  
```ballerina
import ballerina/http;
import ballerina/io;
    
const string CITY = "Colombo";
const int CITY_NO = 1;
    
function getName() returns string {
    string firstName = "john";
    string lastName = "doe";
        
    return firstName + lastName;
}
    
function setName(string name) {}
function setAge(int age) {}
```
  
> **Note:** You can configure tools and plugins to change the number of minimum and maximum blank lines used when formatting. 
 
## Blocks
* Opening curly braces of a block should be placed inline.
  
**Do's**

```ballerina
if (true) {
}
  
function setName(string name) {
  
}
```

**Don'ts**

```ballerina
if (true)
{
    
}

function setName(string name)
{
  
}
```

* Add a single space before the opening curly braces. 

**Example,**

```ballerina

function func1() {
    if (true) {}
}

```

* If a block is empty, do not keep spaces in between the opening and closing braces.
  
**Example,**

```ballerina
function func1() {}
``` 

* Indent all the statements inside a block to be at the same level.
* Indent the closing brace of a block to align it with the starting position of the block statement.

**Example,**
  
```ballerina
if (false) {
   ...
}
  
match a {
   ...
}
```

## Parentheses and Brackets
* Do not have spaces after opening parentheses/bracket and before closing parentheses/bracket.
  
**Example,**

```ballerina
[string, int] tupleVar = ["", 0];
  
function setValue(string value) {...}
  
setValue("value");
```

* To define empty parentheses, do not keep spaces between the opening and closing parentheses `()`.
  
**Example,**

```ballerina
int|() result = getResult();
```
  
## Line Breaks

* Have only one statement in a line.
* When splitting lines, which contain operator(s), split them right before an operator.
  
**Example,**
  
```ballerina
// Binary operations.
string s = "added " + People.name
    + " in to database.";
  
// Function invocation.
string s = person
    .getName();
  
// Binary operations in if condition
if (isNameAvailable 
    && (i == 1)) {
  
}
```

* When splitting lines, which contains separator(s), split them right after a separator.
  
**Example,**
    
```ballerina
// Function parameters.
function getName(int id, int age,
    string searchValue) returns string {
    ...
}
```

* If there isn't any operator or separator to break the line from, move the whole expression to a new line.
  
**Example,**

```ballerina
// String literal.
string s1 =
    "My name is not in this description";
  
// Function invocation.
string s2 =
    getPersonNameWithUpperCaseLetters();
``` 

* If a line exceeds the max line length, start from the end of the line and come towards the start of the line until you find a point, which matches the above rules to break the line.
* Indent split lines with relation to the starting position of the statement or definition.
  
**Example,**

```ballerina
if (isNameAvailable 
    && (i == 1)) {
      
}
  
// Function parameters.
function getName(int id, int age,
    string searchValue) returns string {
    ...
}
```  

* However, if you cannot add the type-casting expression or statement with the constrained type in a single line 
  due to it exceeding the max line length, 
- move the casting type with the operators to a new line.
  
**Example,**
      
```ballerina
    string name =
        <string>json.name;
```
  
- keep the constrained type on the same line by splitting the statement from a point before the constraint type.
      
**Example,**

```ballerina
map<int|string> registry = {
    name: "marcus"
};
      
table<Employee> employee = table {
    {key id, name, address}
    };
```

## Top-Level Definitions

For style guidelines on imports, service definition, object definition, record definition, referencing record or abstract object, etc., see [Top Level Definitions](/1.2/learn/style-guide/definitions).

## Operators, Keywords, and Types

For style guidelines on operators, keywords, and types, see [Operators, Keywords, and Types](/1.2/learn/style-guide/operators_keywords_and_types).

## Statements

For style guidelines on statements such as if, match, transaction etc., see [Statements](/1.2/learn/style-guide/statements).

## Expressions

For style guidelines on function invocation, literals, tuple, type casting etc. see [Expressions](/1.2/learn/style-guide/expressions).

## Annotations, Documentation, and Comments

For style guidelines on annotations, documentation, and comments, see [Annotations, Documentation, and Comments](/1.2/learn/style-guide/annotations_documentation_and_comments).

<div class="cGitButtonContainer"><p data-button="iGitStarText">"Star"</p><p data-button="iGitWatchText">"Watch"</p></div>


<style> #tree-expand-all , #tree-collapse-all, .cTocElements {display:none;} .cGitButtonContainer {padding-left: 40px;display: none;} </style>