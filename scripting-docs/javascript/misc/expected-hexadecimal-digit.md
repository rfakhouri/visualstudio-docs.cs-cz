---
title: "Očekávaný šestnáctková číslice | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: javascript
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VS.WebClient.Help.SCRIPT1023
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 67a86df7-49f9-43cb-99c6-99b1a427827a
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c9e29131c4ecf4f476a30da94ec67676d6bea347
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="expected-hexadecimal-digit"></a>Byla očekávána šestnáctková číslice.
Vytvořili jste nesprávný escape sekvence Unicode. Řídicí sekvence Unicode začínat \u, za nímž následuje přesně čtyři hexadecimální číslice (žádné další a ne menší). Unicode šestnáctkové číslice může obsahovat pouze číslice 0 – 9, velká písmena A-F a malá písmena-f. Následující příklad ukazuje správně vytvořená escape sekvence Unicode.  
  
```JavaScript  
z = "\u1A5F";  
```  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   Ujistěte se, že vaše šestnáctkové číslice Unicode začínat \u, obsahuje pouze číslice 0 – 9, velká písmena A-F, malá písmena-f; a jsou seskupené do čtyři číslice.  
  
    > [!NOTE]
    >  Pokud chcete použít \u literálu text v řetězci, potom použijte dvě zpětná - (\\\u) – jeden, abyste se vyhnuli první zpětné lomítko.  
  
## <a name="see-also"></a>Viz také  
 [Datové typy](../../javascript/data-types-javascript.md)