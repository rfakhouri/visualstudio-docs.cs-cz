---
title: split – metoda (String) (JavaScript) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- split
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- split method
ms.assetid: 7f093336-c887-4efb-b91f-819b6d18a181
caps.latest.revision: 17
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: eea90dda2e8e4d52451af247d139eeee44f83917
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791598"
---
# <a name="split-method-string-javascript"></a>split – metoda (String) (JavaScript)
Rozdělení řetězce na podřetězce pomocí zadaného oddělovače a jejich vrácení v podobě pole.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
stringObj.split([separator[, limit]])  
```  
  
## <a name="parameters"></a>Parametry  
 `stringObj`  
 Požadováno. `String` Objekt nebo řetězcový literál, aby se daly rozdělit. Tento objekt není upraveném **rozdělení** metoda.  
  
 `separator`  
 Volitelné. Řetězec nebo **regulární výraz** objekt, který identifikuje znak nebo znaků, který má používat v oddělení řetězec. Pokud je tento argument vynechán, je vráceno pole s jedním prvkem obsahujícím celý řetězec.  
  
 `limit`  
 Volitelné. Hodnota použitá k omezení počtu prvků vrácených v poli.  
  
## <a name="return-value"></a>Návratová hodnota  
 Výsledkem **rozdělení** metoda je pole řetězců rozdělení v každém bodu kde `separator` dojde v `stringObj`. `separator` Nevrátí jako součást libovolného pole elementu.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití **rozdělení** metoda.  
  
```JavaScript  
var s = "The quick brown fox jumps over the lazy dog.";  
var ss = s.split(" ");  
for (var i in ss) {  
    document.write(ss[i]);  
    document.write("<br/>");  
}  
  
// Output:   
// The  
// quick  
// brown  
// fox  
// jumps  
// over  
// the  
// lazy  
// dog.  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Platí pro**: [řetězce objektu](../../javascript/reference/string-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [Metoda concat (řetězec)](../../javascript/reference/concat-method-string-javascript.md)   
 [RegExp – objekt](../../javascript/reference/regexp-object-javascript.md)   
 [Objekt regulárního výrazu](../../javascript/reference/regular-expression-object-javascript.md)   
 [Syntaxi regulárního výrazu (JavaScript)](http://msdn.microsoft.com/en-us/ab0766e1-7037-45ed-aa23-706f58358c0e)   
 [Posouvání, posouvání a přibližování ukázkové aplikace](http://code.msdn.microsoft.com/ie/Scrolling-panning-and-6834aaf9)