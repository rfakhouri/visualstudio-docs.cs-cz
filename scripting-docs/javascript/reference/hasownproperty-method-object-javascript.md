---
title: "hasOwnProperty – metoda (Object) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: hasOwnProperty
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: hasOwnProperty method
ms.assetid: 3eb69d69-486f-4792-9518-4452aef369ca
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 397b68fc87bf730886c928e099037ff0183a7f63
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="hasownproperty-method-object-javascript"></a>hasOwnProperty – metoda (Object) (JavaScript)
Určuje, zda má objekt vlastnost se zadaným názvem.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
object.hasOwnProperty(proName)  
```  
  
## <a name="parameters"></a>Parametry  
 `object`  
 Požadováno. Instance objektu.  
  
 `proName`  
 Požadováno. Hodnota názvu vlastnosti typu řetězec.  
  
## <a name="remarks"></a>Poznámky  
 `hasOwnProperty` Metoda vrátí `true` Pokud `object` vlastnost zadaný název, `false` Pokud neexistuje. Tato metoda nekontroluje vlastnosti v objektu prototypu řetězce; Vlastnost musí být členem skupiny samotného objektu.  
  
 Tato vlastnost není podporována u objektů hostitele pro Internet Explorer 8 a pod ním.  
  
## <a name="example"></a>Příklad  
 V následujícím příkladu všechny `String` objekty sdílejí společnou split – metoda. Následující kód zobrazí **false** a **true**.  
  
```JavaScript  
var s = new String("Sample");  
document.write(s.hasOwnProperty("split"));  
document.write("<br/>");  
document.write(String.prototype.hasOwnProperty("split"));  
  
// Output:  
// false  
// true  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [in – operátor](../../javascript/reference/in-operator-decrementjavascript.md)