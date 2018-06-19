---
title: Promise – objekt (JavaScript) | Microsoft Docs
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
ms.assetid: 358ad98b-f7fa-448c-9ee0-ef1e2a45e9c6
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 61e5611dd0d455c7e7b704777cc2341ca43a2404
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791697"
---
# <a name="promise-object-javascript"></a>Promise – objekt (JavaScript)
Poskytuje mechanismus pro plánování práce na hodnotu, která nebyla dosud poškozený. Je abstrakci pro správu interakce s asynchronní rozhraní API.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
var promise = new Promise(function(resolve, reject) { ... });  
```  
  
#### <a name="parameters"></a>Parametry  
 `promise`  
 Požadováno. Název proměnné, ke kterému je přiřazena potenciálu.  
  
 `resolve`  
 Požadováno. Funkce, která spouští indikující, zda potenciálu byla úspěšně dokončena.  
  
 `reject`  
 Volitelné. Funkce, která spouští indikující, že potenciálu byl odmítnut s chybou.  
  
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
  
## <a name="example"></a>Příklad  
 Můžete také tvoří řetěz volání `then` metoda, jak je znázorněno v následujícím kódu. Každý dokončení obslužné rutiny musí vracet samotné promise pro podporu řetězení. V tento kód, který volá stejné `timeout` fungovat, vrátí první volání časový limit po 1000 ms. První volání obslužné rutiny dokončení `timeout` znovu, a vrátí tuto promise po 2000ms. Obslužná rutina jeho dokončení pak vrátí chybu. Chyba volání obslužné rutiny `Promise.all`, která vrací jenom v případě, že jsou obě volání do vypršení časového limitu byla dokončena nebo odmítl.  
  
```JavaScript  
var p = timeout(1000).then(() => {  
    return timeout(2000);  
}).then(() => {  
    throw new Error("error");  
}).catch(err => {  
    return Promise.all([timeout(100), timeout(200)]);  
})  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]  
  
## <a name="functions"></a>Funkce  
 Následující tabulka popisuje funkcí `Promise` objektu.  
  
|Funkce|Popis|  
|--------------|-----------------|  
|[Promise.all – funkce](../../javascript/reference/promise-all-function-promise.md)|Spojí dva nebo více lišící a vrátí pouze v případě, že všechny zadané lišící dokončíte nebo bylo odmítnuto.|  
|[Promise.race – funkce](../../javascript/reference/promise-race-function-promise.md)|Vytvoří nový promise, který bude vyřešit nebo zamítnout se stejnou hodnotou výsledek jako první promise vyřešit nebo zamítnout mezi předané argumenty.|  
|[Promise.Reject – funkce](../../javascript/reference/promise-reject-function-promise.md)|Vytvoří nový odmítnutých promise se výsledek rovná se předaný argument.|  
|[Promise.Resolve – funkce](../../javascript/reference/promise-resolve-function-promise.md)|Vytvoří nový přeložit promise se výsledek rovná se jeho argumentem.|  
  
## <a name="methods"></a>Metody  
 Následující tabulka popisuje metody `Promise` objektu.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[catch – metoda](../../javascript/reference/catch-method-promise.md)|Umožňuje zadat pracovní provést pro zamítnutí příslib.|  
|[Then – metoda](../../javascript/reference/then-method-promise.md)|Umožňuje zadat pracovní provést pro splnění příslib.|