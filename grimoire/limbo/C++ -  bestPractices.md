---
cssclasses:
  - "centerTitles "
  - " centerImages "
  - " roundedImages"
---
# :dev_cplusplus_original:
# 1. Convenciones De Nombres
Usa camelCase para variables/metodos, PascalCase para clases.

```cpp title="Convenciones de nombres"
class UserAccount{ //PascalCase
	public:
		void proccesUserAge(int userAge){ //camelCase
			if(userAge < 0) return<
		}
};
```

# 2. Alcance Y Constantes
<mark style="background: #FF5582A6;">Se declara siempre en el ambito minimo posible, se inicializa al declarar. Usa <b>const/constexpr</b> </mark>

```cpp title="Alcance y Constantes"
constexpr int MAX_USERS = 100;

void ProccessList(){
	for(int i= 0; i<10; i++){
		const int localSum = i*2;
		std::cout << localSum << '\n';
	}
}
```

# 3. Excepciones Y Documentación

```cpp title="Excepciones y documentación"
/**  
  * Calcula el promedio de una lista de enteros. 
  * @param numbers Lista de números. 
  * @return Promedio como double. 
  */
  
 double CalculateAverage(const std::vector<int>& numbers) {
  try {
    int sum = 0;
    for (int n : numbers) sum += n;
    return static_cast<double>(sum) / numbers.size();
  } catch (const std::overflow_error& ex) {  // Específica, no catch(...)
    std::cerr << "Overflow: " << ex.what() << '\n';
    return 0.0;
  }
}
```


