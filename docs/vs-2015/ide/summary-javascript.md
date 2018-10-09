---
title: '&lt;Souhrn&gt; (JavaScript) | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- summary JavaScript XML tag
- <summary> JavaScript XML tag
ms.assetid: 6540582d-bdb3-42ec-ad2f-c176783e6f9c
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: f6b4808112e746e30f0e40d4626f546c3f99b193
ms.sourcegitcommit: 71218ffc33da325cc1b886f69ff2ca50d44f5f33
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/09/2018
ms.locfileid: "48879015"
---
# <a name="ltsummarygt-javascript"></a>&lt;Souhrn&gt; (JavaScript)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [dokumentace k sadě Visual Studio 2017](/visualstudio/).  
  
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



