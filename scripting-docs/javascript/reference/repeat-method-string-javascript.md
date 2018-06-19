---
title: REPEAT – metoda (String) (JavaScript) | Microsoft Docs
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
ms.assetid: fe02cdfd-f0f6-45a2-ad36-31c4300ef142
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b1a3d6edce877a97b0e46a69c43b667231c26981
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791121"
---
# <a name="repeat-method-string-javascript"></a>repeat – metoda (String) (JavaScript)
Vrátí že nový objekt řetězce se hodnota rovná se původní řetězec opakuje zadaného počtu opakování.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
stringObj.repeat(count);  
```  
  
#### <a name="parameters"></a>Parametry  
 `stringObj`  
 Požadováno. Objekt řetězce.  
  
 `count`  
 Požadováno. Počet opakování původního řetězce v vrácený řetězec.  
  
## <a name="exceptions"></a>Výjimky  
 Tato metoda vyvolá výjimku RangeError jenom v případě argument je záporný nebo + nekonečna.  
  
## <a name="remarks"></a>Poznámky  
 `repeat` Metoda zřetězí původní řetězec, který má nový řetězec kolikrát určeného `count`.  
  
 Tato metoda vyvolá chybu, pokud `count` není kladné číslo menší než `Infinity`.  
  
## <a name="example"></a>Příklad  
  
```JavaScript  
"abc".repeat(3); // Returns "abcabcabc"  
"abc".repeat(0); // Returns an empty string.  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]