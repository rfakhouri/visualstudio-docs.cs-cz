---
title: "Může & č. 39; mít t & č. 39; pozastavení & č. 39; uveden mimo smyčku | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- javascript
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.WebClient.Help.SCRIPT1019
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 11d02172-2a78-4705-a730-d21111db5f42
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bb23f1bc3de087515cad9ba4910cf2ebaf640353
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="can39t-have-39break39-outside-of-loop"></a>Může & č. 39; mít t & č. 39; pozastavení & č. 39; uveden mimo smyčku
Jste se pokusili použít **zalomení** – klíčové slovo mimo smyčku. **Zalomení** – klíčové slovo se používá k ukončení smyčky nebo `switch` příkaz. Musí být vložený do těla smyčky nebo `switch` příkaz. Ale **popisek** můžete postupovat podle klíčového slova přerušení.  
  
```  
break labelname;  
```  
  
 Potřebujete jenom s popiskem formu **zalomení** – klíčové slovo při použití vnořených smyčky nebo `switch` příkazy a nutnosti přerušení mimo smyčku, která není ta, nejvnitřnější.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   Zajistěte, aby **zalomení** – klíčové slovo se zobrazí uvnitř příkazu nadřazených smyčky nebo přepínač.  
  
## <a name="see-also"></a>Viz také  
 [Příkaz BREAK](../../javascript/reference/break-statement-javascript.md)   
 [Řízení toku programu](../../javascript/controlling-program-flow-javascript.md)   
 [Řešení potíží se skripty](../../javascript/advanced/troubleshooting-your-scripts-javascript.md)