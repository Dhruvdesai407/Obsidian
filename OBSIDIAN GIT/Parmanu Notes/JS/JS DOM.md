DOM is not a part of JS.
# Accessing elements via console :
==document== 
==document.documentElement== *to access html part*
==document.head== *to access html's head*
### child nodes are all of the nodes that are children of the body, this also includes whitespaces .
==document.body.childNodes[2]== *this selects 3rd child in body*
==document.body.firstChild.nextSibling== *selects sibling next to first child*
## document.getElementById('id')
## document.getElementsByTagName('tagname')
## document.getElementsByClassName()

# CSS queryselectors for DOM :
1. ==document.querySelectorAll('css style query')== *returns multiple elements that matches css selector*
2. ==document.querySelector()==