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
ms.openlocfilehash: e1e34be9f8eab5171af0e2553d5777b0958bf3c2
ms.sourcegitcommit: 23feea519c47e77b5685fec86c4bbd00d22054e3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/26/2019
ms.locfileid: "56840867"
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