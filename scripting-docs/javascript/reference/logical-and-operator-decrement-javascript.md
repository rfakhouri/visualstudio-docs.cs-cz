---
title: "Logický operátor AND (&amp;&amp;) (JavaScript) | Microsoft Docs"
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
- '&&'
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- logical AND operator
- '&& operator'
ms.assetid: 4714dea9-1999-444a-8acd-72f0851e4f65
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2107eb89c5ca964cf08172050b49307cb150590f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="logical-and-operator-ampamp-javascript"></a>Logický operátor AND (&amp;&amp;) (JavaScript)
Provede logickou konjunkci dvou výrazů.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
result = expression1 && expression2   
```  
  
## <a name="parameters"></a>Parametry  
 `result`  
 Všechny proměnné.  
  
 `expression1`  
 Jakýkoli výraz.  
  
 `expression2`  
 Jakýkoli výraz.  
  
## <a name="remarks"></a>Poznámky  
 Pokud `expression1` vyhodnotí jako `false`, `result` je `expression1`. V opačném `result` je `expression2`. V důsledku toho vrátí operaci `true` Pokud jsou oba operandy true; jinak vrátí `false`.  
  
 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]pro převedení hodnoty logickou hodnotu na logické hodnoty používá následující pravidla:  
  
-   Všechny objekty se považují za `true`.  
  
-   Řetězce se považují za `false` prázdné.  
  
-   `null`a `undefined` se považují za `false`.  
  
-   Číslo je `false` Pokud je nula.  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Priorita operátorů](../../javascript/operator-subtractprecedence-javascript.md)   
 [Souhrn operátorů (JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)