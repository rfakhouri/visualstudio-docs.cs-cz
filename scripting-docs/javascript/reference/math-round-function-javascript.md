---
title: "Math.Round – funkce (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: round
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Round method
- Math object
ms.assetid: 51008df3-5d0c-4951-84cb-4f41000db0be
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9543d529e3d0e4e45cff29f1286edbfad8dc0e27
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="mathround-function-javascript"></a>Math.round – funkce (JavaScript)
Vrátí zadaný číselného výrazu zaokrouhlí na nejbližší celé číslo.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
Math.round(  
number  
)   
```  
  
## <a name="remarks"></a>Poznámky  
 Požadované `number` argument je hodnota má být zaokrouhleno na nejbližší celé číslo.  
  
 Pro kladná čísla Pokud za desetinnou `number` 0,5 nebo je vyšší, návratová hodnota se rovná nejmenší celé číslo větší než `number`. Pokud za desetinnou je menší než 0,5, vrácená hodnota je největší celé číslo menší než nebo rovna hodnotě `number`.  
  
 Pro záporná čísla, pokud desetinné části přesně -0,5, vrácená hodnota je nejmenší celé číslo větší než číslo.  
  
 Například `Math.round(8.5)` vrátí 9, ale `Math.round(-8.5)` vrátí -8.  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **Platí pro**: [Math – objekt](../../javascript/reference/math-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [Math.Random – funkce](../../javascript/reference/math-random-function-javascript.md)