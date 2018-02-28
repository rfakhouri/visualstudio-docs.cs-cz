---
title: "Očekávaný & č. 39;] & č. 39; v regulárním výrazu (JavaScript) | Microsoft Docs"
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
- VS.WebClient.Help.SCRIPT5019
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 1ca2079a-44dd-479f-a1e3-e04a14d0739e
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4c59dcbeea91a1bc01e870d0a49fd22cace6562d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="expected-3939-in-regular-expression-javascript"></a>Očekávaný & č. 39;] & č. 39; v regulárním výrazu (JavaScript)
Proběhl pokus o vytvoření třídy znaků shody regulárního výrazu, ale neobsahuje pravé závorky. Kombinace jednotlivých literálu znaků lze sestavit do třídy znaků tím, že je v závorkách. Třídy znaků odpovídá jeden libovolný znak, které obsahuje. Například / [abc] / vyhledá kterýkoli ze znaků "a", "b", nebo "c".  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   Přidejte pravou hranatou závorku regulárnímu výrazu.  
  
    > [!NOTE]
    >  Pokud chcete porovnat jeden závorky, vyhnuli obráceným lomítkem - \\[– aby nebyl interpretován jako speciální znak podle [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)].  
  
## <a name="see-also"></a>Viz také  
 [Objekt regulárního výrazu](../../javascript/reference/regular-expression-object-javascript.md)   
 [Syntaxi regulárního výrazu (JavaScript)](http://msdn.microsoft.com/en-us/ab0766e1-7037-45ed-aa23-706f58358c0e)