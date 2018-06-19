---
title: valueOf – metoda (Object) (JavaScript) | Microsoft Docs
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
- valueOf
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- valueOf method
ms.assetid: c555e38b-f451-4341-8fcd-4c8b02906a2c
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 677b56fd6fc142ce175b130d2f83291c1ac9535f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24792009"
---
# <a name="valueof-method-object-javascript"></a>valueOf – metoda (Object) (JavaScript)
Vrátí primitivní hodnotu zadaného objektu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
object.valueOf( )  
```  
  
## <a name="remarks"></a>Poznámky  
 Požadované `object` odkaz je všechny vnitřní [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] objektu.  
  
 `valueOf` Jinak definována metoda pro každou vnitřní [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] objektu.  
  
|Objekt|Návratová hodnota|  
|------------|------------------|  
|Pole|Vrací instanci pole.|  
|Boolean|Logická hodnota.|  
|Datum|Hodnota uložená čas v milisekundách od půlnoci 1. ledna 1970 UTC.|  
|Funkce|Funkce sám sebe.|  
|Číslo|Číselná hodnota.|  
|Objekt|Samotný objekt. Toto nastavení je výchozí.|  
|String|Řetězcová hodnota.|  
  
 **Matematické** a `Error` objekty nemají `valueOf` metoda.  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]  
  
 **Platí pro**: [objekt Array](../../javascript/reference/array-object-javascript.md)&#124; [Boolean – objekt](../../javascript/reference/boolean-object-javascript.md)&#124; [Datum objektu](../../javascript/reference/date-object-javascript.md)&#124; [Funkce objekt](../../javascript/reference/function-object-javascript.md)&#124; [Číslo objekt](../../javascript/reference/number-object-javascript.md)&#124; [Objekt objektu](../../javascript/reference/object-object-javascript.md)&#124; [Řetězce objektu](../../javascript/reference/string-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [toString – metoda (Object)](../../javascript/reference/tostring-method-object-javascript.md)