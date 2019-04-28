---
title: Byl očekáván ' @' | Dokumentace Microsoftu
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT1032
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 82ff8b74-1710-4358-9a26-dc92ab29c53b
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: aa2728306d9e650bf7f8b446b6af5a409a39d0e0
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62935246"
---
# <a name="expected-"></a>Byl očekáván '\@.
Pokus o vytvoření proměnné pro použití s příkazy podmíněné kompilace pomocí `@set` příkazu, ale vliv zavináč "**@**" před název proměnné.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
- Přidat zavináč "**@**" bezprostředně před název proměnné. Příklad:  
  
    ```JavaScript  
    @set @myvar = 1  
    ```  
  
## <a name="see-also"></a>Viz také  
 [@set – Příkaz](../../javascript/reference/at-set-statement-javascript.md)   
 [Podmíněná kompilace](../../javascript/advanced/conditional-compilation-javascript.md)   
 [Proměnné podmíněné kompilace](../../javascript/advanced/conditional-compilation-variables-javascript.md)
