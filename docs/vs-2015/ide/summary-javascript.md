---
title: '&lt;Souhrn&gt; (JavaScript) | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- summary JavaScript XML tag
- <summary> JavaScript XML tag
ms.assetid: 6540582d-bdb3-42ec-ad2f-c176783e6f9c
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 81d41918d61bbe95cfe19d2382535449a47deb8c
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54775811"
---
# <a name="ltsummarygt-javascript"></a>&lt;Souhrn&gt; (JavaScript)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Určuje popis pro funkci nebo metodu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<summary locid="descriptionID">description  
</summary>  
```  
  
#### <a name="parameters"></a>Parametry  
 `locid`  
 Volitelné. Identifikátor lokalizace informace o funkci nebo metodu. Identifikátor je buď členem, nebo ID odpovídá `name` hodnotu v sadě zprávy určené OpenAjax metadat atributu. Typ identifikátoru závisí na formátu určeného v [ \<umístění >](../ide/loc-javascript.md) elementu.  
  
 `description`  
 Volitelné. Popis funkce nebo metody.  
  
## <a name="remarks"></a>Poznámky  
 Prvky používaná k anotaci funkce, mezi které patří [ \<summary >](../ide/summary-javascript.md), [ \<param >](../ide/param-javascript.md), a [ \<vrátí >](../ide/returns-javascript.md), musí být umístěn v těle funkce před vykonáním jakýchkoli příkazů.  
  
## <a name="example"></a>Příklad  
 Následující kód ukazuje způsob použití `<summary>` elementu.  
  
```javascript  
function areaFunction(radiusParam)  
{  
    /// <summary>Determines the area of a circle when supplied a radius parameter.</summary>  
    /// <param name="radiusParam" type="Number">The radius of the circle.</param>  
    /// <returns type="Number">The area.</returns>  
    var areaVal;  
    areaVal = Math.PI * radiusParam * radiusParam;  
    return areaVal;  
}  
  
```  
  
## <a name="see-also"></a>Viz také  
 [Dokumentační komentáře XML](../ide/xml-documentation-comments-javascript.md)
