---
title: New – operátor (JavaScript) | Microsoft Docs
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
- new_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- new operator in JavaScript
ms.assetid: 5ea556ba-7ae6-426c-8430-9032eee5a0a5
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0ad004abb534d69bed1a1bd9bbd2ae96755544b9
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791082"
---
# <a name="new-operator-javascript"></a>new – operátor (JavaScript)
Vytvoří nový objekt.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
new constructor ([arguments])   
```  
  
## <a name="parameters"></a>Parametry  
 `constructor`  
 Požadováno. Konstruktoru objektu. Závorky lze vynechat, pokud konstruktoru nezadávaly žádné argumenty.  
  
 `arguments`  
 Volitelné. Všechny argumenty mají být předány konstruktor nový objekt.  
  
## <a name="remarks"></a>Poznámky  
 `new` Operátor provádí následující úlohy:  
  
-   Vytvoří objekt bez členů.  
  
-   Volá v konstruktoru pro daný objekt předávání ukazatel na nově vytvořený objekt, jako `this` ukazatel.  
  
-   Konstruktor inicializuje pak objekt podle argumentů předaných konstruktoru.  
  
 Toto jsou příklady platné použití **nové** operátor.  
  
```JavaScript  
my_object = new Object;  
my_array = new Array();  
my_date = new Date("Jan 5 1996");  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Function – příkaz](../../javascript/reference/function-statement-javascript.md)