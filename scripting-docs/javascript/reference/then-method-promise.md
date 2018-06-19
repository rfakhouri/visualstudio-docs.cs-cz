---
title: Then – metoda (Promise) | Microsoft Docs
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
ms.assetid: c7f3259d-78f7-4ca7-8bdf-99fbd3f41e8d
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: eeb97fae19ca9923280b5099e3e4d8c839fa2815
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791571"
---
# <a name="then-method-promise"></a>then – metoda (Promise)
Umožňuje zadat pracovní provést pro splnění příslib.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
promise.then(onCompleted, onRejected);  
```  
  
#### <a name="parameters"></a>Parametry  
 `promise`  
 Požadováno. Promise objekt.  
  
 `onCompleted`  
 Požadováno. Funkce obslužných rutin splnění spustit po úspěšném dokončení potenciálu.  
  
 `onRejected`  
 Volitelné. Chyba obslužné rutiny spustit, když potenciálu byl odmítnut.  
  
## <a name="remarks"></a>Poznámky  
 Příslib musí být buď dokončení s hodnotou, nebo musí být odmítnuta s důvod. `then` Metodu objektu Promise se spouští při potenciálu je dokončena nebo zamítnutí, cokoliv nastane dříve. Pokud potenciálu je úspěšně dokončit, funkce splnění obslužné rutiny `then` metoda spustí. Pokud potenciálu se odmítne, funkce obslužná rutina chyby `then` – metoda (nebo `catch` metoda) spouští.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak volat funkci (`timeout`), který vrací příslib. Obslužné rutiny splnění `then` metoda se spouští po 5000ms vyprší časový limit.  
  
```JavaScript  
function timeout(duration) {  
    return new Promise(function(resolve, reject) {  
        setTimeout(resolve, duration);  
    });  
}  
  
// Note: This code uses arrow function syntax  
var m = timeout(5000).then(() => {  
    console.log("done!");  
})  
  
// Output (after 5 seconds):  
// done!  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Promise – objekt](../../javascript/reference/promise-object-javascript.md)