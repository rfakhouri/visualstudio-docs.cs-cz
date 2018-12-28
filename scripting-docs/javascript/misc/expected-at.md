---
title: Byl očekáván ' @' | Dokumentace Microsoftu
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
- VS.WebClient.Help.SCRIPT1032
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 82ff8b74-1710-4358-9a26-dc92ab29c53b
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 191402a9ba265e5acfb15d1931e260f6b366687e
ms.sourcegitcommit: f6dd17b0864419083d0a1bf54910023045526437
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/27/2018
ms.locfileid: "53804549"
---
# <a name="expected-"></a>Byl očekáván znak '@'
Pokus o vytvoření proměnné pro použití s příkazy podmíněné kompilace pomocí `@set` příkazu, ale vliv zavináč "**@**" před název proměnné.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   Přidat zavináč "**@**" bezprostředně před název proměnné. Příklad:  
  
    ```JavaScript  
    @set @myvar = 1  
    ```  
  
## <a name="see-also"></a>Viz také  
 [@set – Příkaz](../../javascript/reference/at-set-statement-javascript.md)   
 [Podmíněná kompilace](../../javascript/advanced/conditional-compilation-javascript.md)   
 [Proměnné podmíněné kompilace](../../javascript/advanced/conditional-compilation-variables-javascript.md)