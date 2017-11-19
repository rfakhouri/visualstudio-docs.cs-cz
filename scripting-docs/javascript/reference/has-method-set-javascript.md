---
title: "has – metoda (Set) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: fb80f2e0-fc5e-4508-af14-1c3b3b833636
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c9690e3d091e8ae0f9670fd737a29590524834c9
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="has-method-set-javascript"></a>has – metoda (Set) (JavaScript)
Vrátí `true` Pokud sada obsahuje zadaný element.  
  
## <a name="syntax"></a>Syntaxe  
  
```JavaScript  
setObj.has(value)  
```  
  
#### <a name="parameters"></a>Parametry  
 `setObj`  
 Požadováno. A `Set` objektu.  
  
 `value`  
 Požadováno. Elementu, který chcete otestovat.  
  
## <a name="property-valuereturn-value"></a>Hodnota vlastnosti / návratová hodnota  
 `true`Pokud sada obsahuje zadaný element.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak přidávat členy do `Set` a potom zkontrolujte, zda sada obsahuje konkrétní člena.  
  
```JavaScript  
var s = new Set();  
s.add("Thomas Jefferson");  
s.add(1776);  
  
document.write(s.has(1776));  
document.write(s.has("1776"));  
  
// Output:  
// true  
// false  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]