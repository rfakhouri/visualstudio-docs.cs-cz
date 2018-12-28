---
title: Byl očekáván 'příkaz catch' | Dokumentace Microsoftu
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
- VS.WebClient.Help.SCRIPT1033
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: f1cd947f-eba2-411e-8e84-8ca86f608643
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 244635605abafc5c0bd22c5203b105aa6e7dc669
ms.sourcegitcommit: f6dd17b0864419083d0a1bf54910023045526437
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/27/2018
ms.locfileid: "53801973"
---
# <a name="expected-catch"></a>Byl očekáván příkaz 'catch'
Použít zpracování výjimek **zkuste** blokovat, ale nezapsal přidruženého **catch** příkazu. Mechanismus zpracování výjimek vyžaduje, aby kód, který může selhat, spolu s kódem, který by neměl být spuštěn pokud dojde k výjimce uzavřou uvnitř **zkuste** bloku. Jsou výjimky vyvolány v rámci **zkuste** blokovat, s využitím **throw** příkaz a zachycené mimo **zkuste** blok s jednou nebo více **catch**příkazy.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   Přidat přidruženého **catch** bloku.  
  
-   Zkuste použít **nakonec** blokovat místo **catch** bloku.  
  
## <a name="see-also"></a>Viz také  
 [Try... catch... finally – příkaz](../../javascript/reference/try-dot-dot-dot-catch-dot-dot-dot-finally-statement-javascript.md)   
 [Error – objekt](../../javascript/reference/error-object-javascript.md)