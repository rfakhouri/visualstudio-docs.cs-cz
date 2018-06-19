---
title: with – příkaz (JavaScript) | Microsoft Docs
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
- with_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- With statement
ms.assetid: 892c7621-ae9e-4c10-8adb-05532274b1ca
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 35d49b13261c66cde0ecd53517a99361f6aecb79
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791874"
---
# <a name="with-statement-javascript"></a>with – příkaz (JavaScript)
Vytvoří výchozí objekt pro příkaz.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
with (object) {  
    statements  
}   
```  
  
## <a name="parameters"></a>Parametry  
 `object`  
 Výchozí objekt.  
  
 `statements`  
 Jeden nebo více příkazů, pro kterou `object` je výchozí objekt.  
  
## <a name="remarks"></a>Poznámky  
 `with` Příkaz se často používá ke zmenšit velikost kód, který máte k zápisu v určitých situacích.  
  
> [!WARNING]
>  Použití `with` není povolen v striktní režim. Použití `with` můžete provést kód těžší pro čtení a ladění a obecně by se mělo zabránit.  
  
## <a name="example"></a>Příklad  
 V tomto příkladu `Math` objekt se používá opakovaně:  
  
```JavaScript  
x = Math.cos(3 * Math.PI) + Math.sin(Math.LN10)   
y = Math.tan(14 * Math.E)  
```  
  
## <a name="example"></a>Příklad  
 Pokud přepisování příklad pro použití `with` příkaz, bude váš kód více stručného:  
  
```JavaScript  
with (Math){  
   x = cos(3 * PI) + sin (LN10)    
   y = tan(14 * E)  
}  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Tento příkaz](../../javascript/reference/this-statement-javascript.md)