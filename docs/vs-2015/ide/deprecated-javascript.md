---
title: '&lt;zastaralé&gt; (JavaScript) | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
ms.assetid: cf33d371-59da-4310-95ee-d7524fd9d58c
caps.latest.revision: 10
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: b93a2b4dcc541f32c16766da0dd9dd19a4fdfe0d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68177808"
---
# <a name="ltdeprecatedgt-javascript"></a>&lt;zastaralé&gt; (JavaScript)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

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
