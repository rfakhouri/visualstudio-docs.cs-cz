---
title: "Length – vlastnost (pole) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- length Property
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Array object
- Length property
- length property (array)
ms.assetid: e1c6377c-2e84-440a-9660-f1f512e4a938
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6e69fd5387b1d7430491b1693dec07581f165cc9
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="length-property-array-javascript"></a>length – vlastnost (Pole) (JavaScript)
Získá nebo nastaví délku pole. To je číslo vyšší než nejvyšší element definovaný v pole.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
numVar = arrayObj.length   
```  
  
## <a name="parameters"></a>Parametry  
 `numVar`  
 Požadováno. Jakékoli číslo.  
  
 `arrayObj`  
 Požadováno. Všechny `Array` objektu.  
  
## <a name="remarks"></a>Poznámky  
 V jazyce JavaScript jsou zhuštěných pole a prvků v poli nemusí být souvislý. `length` Vlastnost není nutně počet prvků v poli. Například v definici následující pole `my_array.length` obsahuje 7, není 2:  
  
```JavaScript  
var my_array = new Array( );  
my_array[0] = "Test";  
my_array[6] = "Another Test";  
```  
  
 Provedete-li `length` menší než původní hodnotu vlastnosti, se zkrátí pole a všechny elementy pole indexů rovna nebo větší než nová hodnota `length` vlastnost budou ztraceny.  
  
 Pokud provedete vlastnost délku větší než jejich předchozí hodnotu, je rozšířena pole a vytvořit nové prvky mají hodnotu `undefined`.  
  
 Následující příklad ukazuje použití `length` vlastnost:  
  
```JavaScript  
var a;  
a = new Array(0,1,2,3,4);  
document.write(a.length);  
  
// Output  
// 5  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]  
  
> [!NOTE]
>  Spouštění v režimu Standardy aplikace Internet Explorer 9, jsou koncové čárkami, které jsou součástí inicializace pole zpracovány jinak.