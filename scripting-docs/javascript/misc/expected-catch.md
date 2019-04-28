---
title: Byl očekáván 'příkaz catch' | Dokumentace Microsoftu
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT1033
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: f1cd947f-eba2-411e-8e84-8ca86f608643
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 941d49a530b14e2af64ddcb599dd775feb347de0
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62935396"
---
# <a name="expected-catch"></a>Byl očekáván příkaz 'catch'
Použít zpracování výjimek **zkuste** blokovat, ale nezapsal přidruženého **catch** příkazu. Mechanismus zpracování výjimek vyžaduje, aby kód, který může selhat, spolu s kódem, který by neměl být spuštěn pokud dojde k výjimce uzavřou uvnitř **zkuste** bloku. Jsou výjimky vyvolány v rámci **zkuste** blokovat, s využitím **throw** příkaz a zachycené mimo **zkuste** blok s jednou nebo více **catch**příkazy.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
- Přidat přidruženého **catch** bloku.  
  
- Zkuste použít **nakonec** blokovat místo **catch** bloku.  
  
## <a name="see-also"></a>Viz také  
 [Try... catch... finally – příkaz](../../javascript/reference/try-dot-dot-dot-catch-dot-dot-dot-finally-statement-javascript.md)   
 [Error – objekt](../../javascript/reference/error-object-javascript.md)