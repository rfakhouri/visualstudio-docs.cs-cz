---
title: Podmíněná kompilace je vypnutá. | Dokumentace Microsoftu
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT1030
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 59a030b0-a6c6-47f2-b90e-c0ed204d5116
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3d3c225df20113308ee7037742ad74efb6a0cc2e
ms.sourcegitcommit: 23feea519c47e77b5685fec86c4bbd00d22054e3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/26/2019
ms.locfileid: "56840351"
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