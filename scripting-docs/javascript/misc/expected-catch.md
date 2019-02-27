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
ms.openlocfilehash: 4a25f72fccfd072243d6d0fdfd1d311c1a3bb6f4
ms.sourcegitcommit: 23feea519c47e77b5685fec86c4bbd00d22054e3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/26/2019
ms.locfileid: "56841444"
---
# <a name="expected-catch"></a>Byl očekáván příkaz 'catch'
Použít zpracování výjimek **zkuste** blokovat, ale nezapsal přidruženého **catch** příkazu. Mechanismus zpracování výjimek vyžaduje, aby kód, který může selhat, spolu s kódem, který by neměl být spuštěn pokud dojde k výjimce uzavřou uvnitř **zkuste** bloku. Jsou výjimky vyvolány v rámci **zkuste** blokovat, s využitím **throw** příkaz a zachycené mimo **zkuste** blok s jednou nebo více **catch**příkazy.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   Přidat přidruženého **catch** bloku.  
  
-   Zkuste použít **nakonec** blokovat místo **catch** bloku.  
  
## <a name="see-also"></a>Viz také  
 [Try... catch... finally – příkaz](../../javascript/reference/try-dot-dot-dot-catch-dot-dot-dot-finally-statement-javascript.md)   
 [Error – objekt](../../javascript/reference/error-object-javascript.md)