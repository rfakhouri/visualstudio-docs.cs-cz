---
title: Podmíněná kompilace je vypnutá. | Dokumentace Microsoftu
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
- VS.WebClient.Help.SCRIPT1030
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 59a030b0-a6c6-47f2-b90e-c0ed204d5116
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bcbf844ced2bb74ddfea9bd62d68877b7a3c969c
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54347343"
---
# <a name="conditional-compilation-is-turned-off"></a>Podmíněná kompilace je vypnutá
Pokusili jste se použít na proměnné podmíněné kompilace bez prvního zapnutí podmíněné kompilace. Zapnutí podmíněné kompilace říká [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] kompilátor k interpretaci identifikátory počínaje jako proměnné podmíněné kompilace. To provedete od podmíněného kódu pomocí příkazu:  
  
```js
/*@cc_on @*/  
```  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   Na začátek podmíněného kódu přidejte následující příkaz:  
  
    ```JavaScript  
    /*@cc_on @*/  
    ```  
  
## <a name="see-also"></a>Viz také  
 [Podmíněná kompilace](../../javascript/advanced/conditional-compilation-javascript.md)   
 [Proměnné podmíněné kompilace](../../javascript/advanced/conditional-compilation-variables-javascript.md)   
 [@cc_on – Příkaz](../../javascript/reference/at-cc-on-statement-javascript.md)   
 [@if – Příkaz](../../javascript/reference/at-if-statement-javascript.md)   
 [@set – příkaz](../../javascript/reference/at-set-statement-javascript.md)