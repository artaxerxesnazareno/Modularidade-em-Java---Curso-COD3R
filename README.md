# Modularidade em Java
é criar um encapsulamento mais expecifico entre projetos que de algum modo tenham dependencias entre si.

Basica mente modularidade é um conjunto de pacotes que estarão dentro de um modulo, e você apartir desse modulo quais os pacotes que vão estar visiveis para fora do modulo e aquilo que é preciso para aquele modulo funcionar 
![img.png](image/img.png)
### Dependencia Reciprica
é quando existe uma dependencia de A para B e B para A
![img_1.png](image/img_1.png)
O modulo em java ajudam a acabar com a dependencia Reciprica

## Importar Modulo
usamos `requires` para impotar modulo
```java
module app.financeiro {
    requires java.base; // java.base é o modulo padrão do java é nele onde esta contido o java.lang
    requires app.calculo;

}
```

## Exportar Modulo
usamos o `exports` para exportar um modulo

```java
module app.calculo {
exports ao.com.as.app.financeiro.app.calculo;
}
```

## Exportar Modulo de um projeto com dependencia de outro projeto para um novo projeto
usamos o `transitive` para exportar a dependencia de um projeto para um novo projeto
```java
module app.calculo {
    requires transitive app.loggin;
    exports ao.com.as.app.financeiro.app.calculo;
}
```