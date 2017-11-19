---
title: "Tento příkaz (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: this_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- this statement
- constructors, referring to current object
ms.assetid: 8510a00b-2f14-4700-a276-4d9a523c5112
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f4afed1bd978d1985c151efa77873c93e699f0b1
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="this-statement-javascript"></a>this – příkaz (JavaScript)
Odkazuje na aktuální objekt.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
this.property  
```  
  
## <a name="remarks"></a>Poznámky  
 Požadované `property` argument je jedna z vlastností aktuálního objektu  
  
 `this` – Klíčové slovo lze použít v konstruktorech objektu k odkazování na aktuální objekt.  
  
## <a name="example"></a>Příklad  
 V následujícím příkladu **to** odkazuje na nově vytvořený objekt Car a přiřazuje hodnoty třemi vlastnostmi:  
  
```JavaScript  
function Car(color, make, model){  
   this.color = color;  
   this.make = make;  
   this.model = model;  
}  
```  
  
 **To** – klíčové slovo obvykle odkazuje **okno** objekt, je-li použít mimo obor jakýkoliv jiný objekt. Ale uvnitř obslužné rutiny událostí `this` odkazuje na elementu DOM, který vyvolá událost.  
  
 V následujícím kódu (pro aplikaci Internet Explorer 9 a novější) vypisuje obslužná rutina události řetězcovou verzi tlačítka s ID „clicker“.  
  
```JavaScript  
document.getElementById("clicker").addEventListener("click", eventHandler, false);  
  
        function eventHandler(ev) {  
            document.write(this.toString());  
        }  
  
// Output (when you click the button): [object HTMLButtonElement]  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [New – operátor](../../javascript/reference/new-operator-decrementjavascript.md)   
 [Používání metody bind](../../javascript/advanced/using-the-bind-method-javascript.md)