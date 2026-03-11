---
cssclasses:
  - centerTitles
  - " roundedImages"
  - " centerImages"
tags:
  - java
---

# :dev_java_original: Arrays

[[algorithms__datastructures|Data structures]] that are consecutively stored in memory

```java title="java_declaration" group="arrays"
int[] list = new int [10]; // type[] name = new type[size]
```
```cpp title="cpp_declaration" group="arrays"
int list[10]; // tipe name[size]
```
```c title="C_declaration" group="arrays"
int list[10]; // type name[size]
```
```js title="js_decaration" group="arrays"
let list = [1,2] //scope name = [values]
```
```python title="py_declaration" group="arrays"
list = [] [] [] [] # name = [datum1] [datum2] (Dynamic size)
```


To insert values onto an array 

```java title="valuesInsertion" group="values"
lista[0] = 100; //In the index 0, int 100 is inserted
```
```cpp title="valuesInsertion" group="values"
list[0] = 100; //In index 0, int 100 is inserted
```
```c title="valuesInsertion" group="values"
list[0] = 100; //In index 0, int 100 is inserted
```
```js title="valuesInsertion" group="values"
list[0] = 100; //In index 0, 100 is inserted
```
```python title="valuesInsertion" group="values"
list[0] = 100; # In index 0, 100 is inserted
```

```java title="valuesSelection" group="selection"
lista[0] = 100; // Assign the value
System.out.println(lista[0]);  // Prints 100
int x = lista[0]; // Assign x the value stored at position 0 of the array
```
```cpp title="valuesSelection" group="selection"
list[0] = 100;              // Assign value to index 0
std::cout << list[0];       // Print 100
int x = list[0];            // Read value from index 0 into x
```
```c title="valuesSelection" group="selection"
list[0] = 100;              // Assign value to index 0
printf("%d\n", list[0]);    // Print 100
int x = list[0];            // Read value from index 0 into x
```
```js title="valuesSelection" group="selection"
list[0] = 100; // Assign value to index 0
console.log(list[0]); // Print 100
let x = list[0]; // Read value from index 0 into x
```
```python title="valuesSelection" group="selection"
list[0] = 100 # Assign value to index 0
print(list[0]) # Print 100
x = list[0]  # Read value from index 0 into x
```

## Ejemplo de array (simple)
```java cpp title:Ejemplo_array
package ejemplo_arrays;
	public class Arrays_simples {
	final static int INI_INT = 0;
	public static void main(String[] args) {
		int inicial = INI_INT;
		int[] lista = new int [10];
	
		for (int i = INI_INT; i < lista.length; i++) {
			inicial = inicial + 100;
			lista[i] = inicial;	
		}

		for (int i = 0; i < lista.length; i++) {
			System.out.println(lista[i]);
		}
	}
}
```





