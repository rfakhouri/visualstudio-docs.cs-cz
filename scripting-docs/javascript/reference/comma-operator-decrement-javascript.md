---
title: "Operátor čárka (,) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: '%2C'
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: comma operator
ms.assetid: 699fa0bf-cd0a-45ee-a291-2fbed4ecd470
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2cb504beefc5ce4c260ec8296e2cf097e17d349e
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="comma-operator--javascript"></a>Operátor čárka (,) (JavaScript)
Způsobí, že dvou výrazů má provádět sekvenčně.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
expression1, expression2  
```  
  
## <a name="parameters"></a>Parametry  
 `expression1`  
 Jakýkoli výraz.  
  
 `expression2`  
 Jakýkoli výraz.  
  
## <a name="remarks"></a>Poznámky  
 `,` Operátor způsobí, že výrazy, které mají být provedeny v pořadí zleva doprava. Běžně používá pro `,` operátor je ve výrazu přírůstek `for` smyčky. Příklad:  
  
```JavaScript  
j=25;  
for (i = 0; i < 10; i++, j++)  
{  
   k = i + j;  
}  
```  
  
 `for` Příkaz umožňuje jenom jeden výraz spouštění na konci každé předávání smyčku. `,` Operátor umožňuje více výrazů považován za jeden výraz, takže se zvýší obě proměnné.  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [for – příkaz](../../javascript/reference/for-statement-javascript.md)   
 [Priorita operátorů](../../javascript/operator-subtractprecedence-javascript.md)   
 [Souhrn operátorů (JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)