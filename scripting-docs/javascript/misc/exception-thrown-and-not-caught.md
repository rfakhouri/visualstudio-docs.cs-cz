---
title: Vyvolána výjimka, která nebyla zachycena | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- javascript
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VS.WebClient.Help.SCRIPT5022
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: b5235490-a8e7-42e3-804e-d85235bc6f05
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 839ff08da4d26406b508a206c809b0813d2b32e1
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54349033"
---
# <a name="exception-thrown-and-not-caught"></a>Byla vyvolána výjimka, která nebyla zachycena
Můžete zahrnout `throw` příkaz v kódu, ale nebyl uzavřený do složených závorek **zkuste** bloku, nebo byla již přidružené **catch** bloku zachytávat chyby. Jsou výjimky vyvolány v rámci **zkuste** blokovat, s využitím **throw** příkaz a zachycené mimo **zkuste** blokovat s **catch** příkaz.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   Vložte kód, který může vyvolat výjimku v **zkuste** blokovat a zkontrolujte je odpovídající **catch** bloku.  
  
-   Ujistěte se, že se že váš příkaz catch očekává správnou formu výjimky.  
  
-   Pokud je znovu vyvolána výjimka, ujistěte se, že existuje jiný odpovídajícího příkazu catch.  
  
## <a name="see-also"></a>Viz také  
 [Error – objekt](../../javascript/reference/error-object-javascript.md)   
 [Throw – příkaz](../../javascript/reference/throw-statement-javascript.md)   
 [try...catch...finally – příkaz](../../javascript/reference/try-dot-dot-dot-catch-dot-dot-dot-finally-statement-javascript.md)