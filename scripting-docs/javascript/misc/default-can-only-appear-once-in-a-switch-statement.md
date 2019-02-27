---
title: "'default' může být pouze jednou v příkazu 'switch' | Dokumentace Microsoftu"
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT1027
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: a94100f4-6ee5-4759-b635-9d309e47111e
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a5d31a74900e8eee5daa97bb7f9af5146b237e04
ms.sourcegitcommit: 23feea519c47e77b5685fec86c4bbd00d22054e3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/26/2019
ms.locfileid: "56842179"
---
# <a name="default-can-only-appear-once-in-a-switch-statement"></a>Klíčové slovo 'default' může být v příkazu 'switch' použito pouze jednou
Pokusili jste se použít **výchozí** příkazu více než jednou v rámci příkazu switch. Výchozí případ je vždy posledního příkazu case v příkazu switch (to je případ propuštěním).  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   Odeberte všechny další **výchozí** malá a velká příkazy z vaší `switch` – příkaz (použijte na většině jeden výchozí case – příkaz v příkazu switch).  
  
## <a name="see-also"></a>Viz také  
 [Switch – příkaz](../../javascript/reference/switch-statement-javascript.md)   
 [Řízení toku programu](../../javascript/controlling-program-flow-javascript.md)   
 [JavaScript – vyhrazená slova](../../javascript/reference/javascript-reserved-words.md)