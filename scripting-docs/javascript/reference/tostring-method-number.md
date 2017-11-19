---
title: "toString – metoda (Number) | Microsoft Docs"
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
ms.assetid: 07c3484b-d9d8-4451-a2be-88a19a081966
caps.latest.revision: "2"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f6be170061faf4c2782c7247c80c55065c3a6742
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="tostring-method-number"></a>toString – metoda (Number)
Vrací řetězec představující číslo.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
number.toString()  
```  
  
## <a name="parameters"></a>Parametry  
 `number`  
 Požadováno. Číslo, které má představovat jako řetězec.  
  
## <a name="return-value"></a>Návratová hodnota  
 Řetězcová reprezentace čísla.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití **toString** metoda s číslem.  
  
```JavaScript  
var number = 234.567;  
var s = number.toString();  
document.write(s.length);  
  
// Output: 7  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]