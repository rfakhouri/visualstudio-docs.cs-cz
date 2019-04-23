---
title: Očekávaný šestnáctková číslice | Dokumentace Microsoftu
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT1023
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 67a86df7-49f9-43cb-99c6-99b1a427827a
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2c2507acd42336511dadc3dedd2eba15fe0d5b76
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60050072"
---
# <a name="expected-hexadecimal-digit"></a>Byla očekávána šestnáctková číslice.
Vytvořili jste nesprávný řídicí sekvence Unicode. Řídicí sekvence Unicode začněte s \u, za nímž následuje přesně čtyřmi šestnáctkovými číslicemi (ne více a méně). Šestnáctková číslice v kódování Unicode mohou obsahovat pouze číslice 0 – 9, velká písmena A – F a malá písmena – f. Následující příklad ukazuje správně vytvořená řídicí sekvence Unicode.  
  
```JavaScript  
z = "\u1A5F";  
```  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
- Ujistěte se, že vaše šestnáctkové číslice v kódování Unicode začněte s \u, obsahuje pouze číslice 0 – 9, velká písmena A – F, malá písmena – f; a jsou seskupeny do čtyř číslic.  
  
    > [!NOTE]
    >  Pokud chcete použít \u text literálu v řetězci, a pak pomocí dvě zpětná lomítka - (\\\u) – jeden řídicí první zpětné lomítko.  
  
## <a name="see-also"></a>Viz také  
 [Datové typy](../../javascript/data-types-javascript.md)