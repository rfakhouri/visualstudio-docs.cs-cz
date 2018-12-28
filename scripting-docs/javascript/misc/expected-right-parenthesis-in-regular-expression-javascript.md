---
title: Byl očekáván ')' v regulárním výrazu (JavaScript) | Dokumentace Microsoftu
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
- VS.WebClient.Help.SCRIPT5020
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 2087ba1d-9783-4d40-b609-e8542f579f7f
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6c344105010e406ef4936fdcca58baffbd610088
ms.sourcegitcommit: f6dd17b0864419083d0a1bf54910023045526437
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/27/2018
ms.locfileid: "53802339"
---
# <a name="expected--in-regular-expression-javascript"></a>V regulárním výrazu byl očekáván znak ')' (JavaScript)
Proběhl pokus o vytvoření zachycení regulárních výrazů, kontrolní výraz nebo skupiny, ale neobsahuje pravou závorku. Závorky mají několik účely v regulárních výrazech. Především se používají k zachycení dílčí výrazy, zadejte kontrolních výrazů nebo seskupení vzory tak, aby položky lze považovat za jednu jednotku podle *, +,?, a tak dále.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   Přidáte úplně vpravo pravými závorkami.  
  
    > [!NOTE]
    >  Pokud chcete najít jeden závorky, před něj zpětné lomítko - \\(– tak, aby nebyl interpretován jako znak zvláštní podle [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)].  
  
## <a name="see-also"></a>Viz také  
 [Objekt regulárního výrazu](../../javascript/reference/regular-expression-object-javascript.md)   
 [Syntaxe regulárního výrazu (JavaScript)](https://msdn.microsoft.com/library/1400241x)