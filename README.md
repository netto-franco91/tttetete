# Dicas para um padrão de código HTML<br>
Fazer um padrão em determinadas coisas.</br>

## Interpolação
#### :pencil2: Examples: <br>

_NÃO USAR_<br>
```java
const secondString = 'Minha segunda string';
const variable = 'Minhas primeira string ' + secondString;
```

_USAR_<br>
```java
const secondString = 'Minha segunda string';
const variable = `Minhas primeira string ${secondString}`;
```
<br><br>

## Separar condicionais de filtros 
#### :pencil2: Examples: <br>

_NÃO USAR_<br>
```java
const itensSibling = Array.from(this.elementResizer.parentElement.children).filter(x => !x.classList.contains(wRegionConstant.CLASS_RESIZER) 
                                                                                     && !x.classList.contains(wRegionConstant.CLASS_RESIZER_PANEL) && x.style.display != wRegionConstant.NONE);
```

_USAR_<br>
```java
const isWithoutResizer = (element) => {
    const { CLASS_RESIZER, CLASS_RESIZER_PANEL, NONE } = wRegionConstant;
    return element.style.display !== NONE &&
           !element.classList.contains(CLASS_RESIZER) &&
           !element.classList.contains(CLASS_RESIZER_PANEL);
}
const itensSibling = Array.from(this.elementResizer.parentElement.children).filter(isWithoutResizer);
```
<br><br>


