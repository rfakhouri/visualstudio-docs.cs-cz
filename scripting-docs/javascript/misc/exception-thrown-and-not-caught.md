---
title: Vyvolána výjimka, která nebyla zachycena | Dokumentace Microsoftu
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT5022
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: b5235490-a8e7-42e3-804e-d85235bc6f05
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bae4ed0a335a9c12d16cb46208f77c4b66f12547
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62946326"
---
# <a name="exception-thrown-and-not-caught"></a>Byla vyvolána výjimka, která nebyla zachycena
Můžete zahrnout `throw` příkaz v kódu, ale nebyl uzavřený do složených závorek **zkuste** bloku, nebo byla již přidružené **catch** bloku zachytávat chyby. Jsou výjimky vyvolány v rámci **zkuste** blokovat, s využitím **throw** příkaz a zachycené mimo **zkuste** blokovat s **catch** příkaz.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
- Vložte kód, který může vyvolat výjimku v **zkuste** blokovat a zkontrolujte je odpovídající **catch** bloku.  
  
- Ujistěte se, že se že váš příkaz catch očekává správnou formu výjimky.  
  
- Pokud je znovu vyvolána výjimka, ujistěte se, že existuje jiný odpovídajícího příkazu catch.  
  
## <a name="see-also"></a>Viz také  
 [Error – objekt](../../javascript/reference/error-object-javascript.md)   
 [Throw – příkaz](../../javascript/reference/throw-statement-javascript.md)   
 [try...catch...finally – příkaz](../../javascript/reference/try-dot-dot-dot-catch-dot-dot-dot-finally-statement-javascript.md)