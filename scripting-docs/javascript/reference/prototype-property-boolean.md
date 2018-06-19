---
title: prototype – vlastnost (logická hodnota) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: e4f07cb5-3462-488c-a418-76064ab10eae
caps.latest.revision: 3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 52d2d241c4d550fe4491ea827fab9d586281242d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791160"
---
# <a name="prototype-property-boolean"></a>prototype – vlastnost (logická hodnota)
Vrátí odkaz na prototypu pro logickou hodnotu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
boolean.prototype  
```  
  
## <a name="remarks"></a>Poznámky  
 `boolean` Argument je název objektu.  
  
 `prototype` Vlastnost poskytuje základní sadu funkcí, které třídu objektů. Nové instance objektu "Zdědit" chování prototypu přiřazen tento objekt. Vlastnosti a metody mohou být přidány do prototyp, ale předdefinované objekty nesmí být přiřazena různých prototypu.  
  
 Například přidejte metodu k `Boolean` objektu, která vrátí hodnotu největší elementu pole, deklarovat funkci, přidejte ho do `Boolean.prototype`a pak jeho pomocí.  
  
```JavaScript  
function isFalse( ){  
    if (this.toString() == "false")  
         return true;  
    else  
        return false;  
}  
Boolean.prototype.isFalse = isFalse;  
var bool = new Boolean(1);  
document.write(bool.isFalse());  
  
// Output:  
// false  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]