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

## Usar Constantes
#### :pencil2: Examples: <br>

_NÃO USAR_<br>
```java
export default class wRegionDragDropResizeAreasFactory {
  ajustLastPosition = (element) => {
    const code = this.getCodeElement(element);
    const codeFeature = this.getCodeFeature(this.scope);
    const dadosPostion = this.getDataResizer(codeFeature, code);
    if (dadosPostion) {
      const elementParent = element.parentElement;
      if (dadosPostion.width && !elementParent.classList.contains('region-cont-column')) {
        element.style.width = dadosPostion.width;
        element.style.flex = 'none';
      } else if (dadosPostion.width && elementParent.classList.contains('region-cont-column')) {
        elementParent.style.width = dadosPostion.width;
        elementParent.style.flex = 'none';
      }
      if (dadosPostion.height) {
        element.style.height = dadosPostion.height;
        element.style.flex = 'none';
      }
    }
  }
}
```

_USAR_<br>
```java
import { wRegionConstant } from './w-region-drag-drop-resize-areas.constant';

export default class wRegionDragDropResizeAreasFactory {
  ajustLastPosition = (element) => {
    const code = this.getCodeElement(element);
    const codeFeature = this.getCodeFeature(this.scope);
    const dadosPostion = this.getDataResizer(codeFeature, code);
    if (dadosPostion) {
      const elementParent = element.parentElement;
      if (dadosPostion.width && !elementParent.classList.contains(wRegionConstant.CLASS_CONT_COLUMN)) {
        element.style.width = dadosPostion.width;
        element.style.flex = wRegionConstant.NONE;
      } else if (dadosPostion.width && elementParent.classList.contains(wRegionConstant.CLASS_CONT_COLUMN)) {
        elementParent.style.width = dadosPostion.width;
        elementParent.style.flex = wRegionConstant.NONE;
      }
      if (dadosPostion.height) {
        element.style.height = dadosPostion.height;
        element.style.flex = wRegionConstant.NONE;
      }
    }
  }
}
```
<br><br>

## Separar condicionais de filtros 
#### :pencil2: Examples: <br>

_NÃO USAR_<br>
```java
const itensSibling = Array.from(this.elementResizer.parentElement.children)
                          .filter(x => !x.classList.contains(wRegionConstant.CLASS_RESIZER) 
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


