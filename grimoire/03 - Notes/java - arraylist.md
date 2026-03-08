---
cssclasses:
  - centerTitles
  - " roundedImages"
  - " centerImages"
tags:
  - java
---

# :dev_java_original: Arraylists
Arraylists are a special type of arrays that have dynamic size, <mark style="background: #FF5582A6;">THIS TYPE OF ARRAY CAN ONLY CONTAIN OBJECTS</mark> these type of arrays need to be imported

```java cpp title:Import_ArrayList
import java.util.ArrayList;
```

## Declaration

```java cpp title:Declaración_ArrayLists
ArrayList<Object> name = new ArrayList<Object>(); 
```

## Methods for arraylists

```java title="Object for example"
Circle circle1 = new Circle(radius); 
Circle circle1 = new Circle(radius); 
```

```java cpp title:Metodos_principales_ArrayList
ArrayList<Circle> circles = new ArrayList<Circle>();
circles.add(circle1); //Adding circle1 to next position
circles.add(circle2); //Adding circle2 to next position
circles.get(0); //Retrieve the element in the position 1
circles.getLast(); //Retrieve the last element
circles.set(1,circle1);//Add element to selected position (overwrites)
circles.remove(1); //Removes element in selected position
circles.size(); //Gets the size of the arraylist
circles.clear; //Clears all the positions of the arraylist
circles.isEmpty; //Boolean true or false
```





