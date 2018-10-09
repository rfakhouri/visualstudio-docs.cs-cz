---
title: '&lt;zastaralé&gt; (JavaScript) | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cf33d371-59da-4310-95ee-d7524fd9d58c
caps.latest.revision: 10
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 220f320eba6231161328a08914848114db7ae02b
ms.sourcegitcommit: 71218ffc33da325cc1b886f69ff2ca50d44f5f33
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/09/2018
ms.locfileid: "48880461"
---
# <a name="ltdeprecatedgt-javascript"></a>&lt;zastaralé&gt; (JavaScript)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [dokumentace k sadě Visual Studio 2017](/visualstudio/).  
  
Určuje zastaralé funkce nebo metody.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<deprecated  
    type="deprecate|remove"  
    locid="descriptionID">description  
</deprecated>  
```  
  
#### <a name="parameters"></a>Parametry  
 `type`  
 Volitelné. Určuje, zda odebrat funkce nebo metoda v budoucí verzi, nebo určuje, zda funkce nebo metoda již byla odebrána a její použití může vést k chybě. Nastavte na `deprecate` k určení, že funkce nebo metoda se odebere v budoucí verzi. Nastavte na `remove` k určení, že funkce nebo metoda již byla odebrána.  
  
 `locid`  
 Volitelné. Identifikátor lokalizace informace o funkci nebo metodu. Identifikátor je buď členem, nebo ID odpovídá `name` hodnotu v sadě zprávy určené OpenAjax metadat atributu. Typ identifikátoru závisí na formátu určeného v [ \<umístění >](../ide/loc-javascript.md) elementu.  
  
 `description`  
 Volitelné. Popis funkce nebo metoda, která je zastaralé.  
  
## <a name="remarks"></a>Poznámky  
 Prvky používaná k anotaci funkce, mezi které patří `<deprecated>`, musí být umístěn v těle funkce před vykonáním jakýchkoli příkazů. Pokud označíte funkce jako zastaralé, doporučujeme nahradit její [ \<summary >](../ide/summary-javascript.md) element s `<deprecated>` elementu.  
  
## <a name="example"></a>Příklad  
 Následující kód ukazuje způsob použití `<deprecated>` elementu.  
  
```javascript  
function areaFunction(radiusParam) {  
    /// <deprecated type="deprecate" >Determines the area of a circle when supplied a radius parameter.</deprecated>  
    /// <param name="radiusParam" type="Number">The radius of the circle.</param>  
    /// <returns type="Number">The area.</returns>  
    var areaVal;  
    areaVal = Math.PI * radiusParam * radiusParam;  
    return areaVal;  
}  
  
```  
  
## <a name="see-also"></a>Viz také  
 [Dokumentační komentáře XML](../ide/xml-documentation-comments-javascript.md)



