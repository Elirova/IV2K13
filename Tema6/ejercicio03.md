#Tema 6 - Ejercicio03
- - -
### **Escribir en YAML la siguiente estructura de datos en JSON:**

> **{ uno: "dos", tres: [ 4, 5, "Seis", { siete: 8, nueve: [ 10, 11 ] } ] }**

Para hacer listas ponemos cada miembro en una línea precedido del signo "-". *También pueden hacerse entre simbolos "[]" separando cada elemento con ",".*
Los arrays asociativos se pueden introducir con el formato "clave: valor", uno por línea.*También pueden hacerse entre simbolos "{}" separando cada elemento con ",".*

Uno de los resultados posibles es el siguiente a modo de árbol:

```
- uno: "dos"
  tres:
    - 4
    - 5
    - "Seis"
    -
      - siete: 8
        nueve: 
          - 10
          - 11
```
