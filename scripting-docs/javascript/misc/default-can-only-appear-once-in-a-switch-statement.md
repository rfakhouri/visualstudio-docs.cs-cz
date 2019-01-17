---
title: "'default' může být pouze jednou v příkazu 'switch' | Dokumentace Microsoftu"
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
- VS.WebClient.Help.SCRIPT1027
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: a94100f4-6ee5-4759-b635-9d309e47111e
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a4f254825e27793999932b772ac4bc2512908fae
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54347304"
---
# <a name="default-can-only-appear-once-in-a-switch-statement"></a>Klíčové slovo 'default' může být v příkazu 'switch' použito pouze jednou
Pokusili jste se použít **výchozí** příkazu více než jednou v rámci příkazu switch. Výchozí případ je vždy posledního příkazu case v příkazu switch (to je případ propuštěním).  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   Odeberte všechny další **výchozí** malá a velká příkazy z vaší `switch` – příkaz (použijte na většině jeden výchozí case – příkaz v příkazu switch).  
  
## <a name="see-also"></a>Viz také  
 [Switch – příkaz](../../javascript/reference/switch-statement-javascript.md)   
 [Řízení toku programu](../../javascript/controlling-program-flow-javascript.md)   
 [JavaScript – vyhrazená slova](../../javascript/reference/javascript-reserved-words.md)