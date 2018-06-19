---
title: Number.isinteger – funkce (Number) (JavaScript) | Microsoft Docs
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
ms.assetid: 54fcf68c-0067-4bad-af94-d7ff8c88914a
caps.latest.revision: 2
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 20e1b7b463003d3a25ef64bba793b3273371266b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791148"
---
# <a name="numberisinteger-function-number-javascript"></a>Number.isInteger – funkce (Number) (JavaScript)
Vrátí logickou hodnotu, která určuje, zda hodnota je celé číslo.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Number.isInteger(numValue)   
```  
  
## <a name="return-value"></a>Návratová hodnota  
 `true`Pokud hodnota je celé číslo, jinak `false`.  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]  
  
 **Platí pro**: [číslo objektu](../../javascript/reference/number-object-javascript.md)  
  
## <a name="example"></a>Příklad  
  
```JavaScript  
// Returns true  
Number.isInteger(100)  
Number.isInteger(-100)  
  
// Returns false  
Number.isInteger(Number.NaN)  
Number.isInteger(Infinity)  
Number.isInteger(100 / 3)  
Number.isInteger("100")  
  
```