---
title: findIndex – metoda (Array) (JavaScript) | Microsoft Docs
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
ms.assetid: 3a200cf0-db67-4c7b-89f8-5e9f5dc1a926
caps.latest.revision: 3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5c8da475b776e1c04e4fe5bfc7062318cfec952c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790482"
---
# <a name="findindex-method-array-javascript"></a>findIndex – metoda (Array) (JavaScript)
Vrátí hodnotu indexu pro první prvek pole, že splňuje test kritéria zadaná ve funkci zpětného volání.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
arrayObj.findIndex(callbackfn [, thisArg]);  
```  
  
#### <a name="parameters"></a>Parametry  
 `arrayObj`  
 Požadováno. Objekt array.  
  
 `callbackfn`  
 Požadováno. Funkce zpětného volání k testování každý prvek v poli.  
  
 `thisArg`  
 Volitelné. Určuje, `this` objekt ve funkci zpětného volání. Pokud není zadáno, `this` objekt není definován.  
  
## <a name="remarks"></a>Poznámky  
 `findIndex` Volání funkce zpětného volání jednou pro každý prvek v poli ve vzestupném pořadí, dokud element vrátí `true`. Jakmile element vrátí hodnotu true, `findIndex` vrací hodnotu index elementu, který vrátí hodnotu true. Pokud žádné elementy v poli, vrátí hodnotu PRAVDA, `findIndex` vrátí hodnotu -1.  
  
 `findIndex`není mutovat objekt array.  
  
## <a name="callback-function-syntax"></a>Syntaxe funkce zpětného volání  
 Syntaxe funkce zpětného volání je následující:  
  
 `function callbackfn(value, index, thisArg)`  
  
 Funkci zpětného volání můžete deklarovat pomocí až tří parametrů.  
  
 Parametry funkce zpětného volání jsou následující.  
  
|Argument zpětného volání|Definice|  
|-----------------------|----------------|  
|`value`|Hodnota prvku pole.|  
|`index`|Číselný index prvku pole.|  
|`arrayObj`|Pole objekt, který má-li procházet.|  
  
## <a name="example"></a>Příklad  
 V následujícím příkladu funkce zpětného volání testuje, zda každý prvek v poli je rovna 2.  
  
```JavaScript  
[1,2,3].findIndex(function(x) { x == 2; });  
// Returns an index value of 1.  
  
```  
  
## <a name="example"></a>Příklad  
 Následující příklad používá k testování jednotlivých prvků šipku syntaxe. V tomto příkladu žádné elementy vrátit `true`, a `findIndex` vrátí hodnotu -1.  
  
```  
[1,2,3].findIndex(x => x == 4);  
// Returns an index value of -1.   
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]