---
title: Nelze přiřadit k & č. 39; to & č. 39; | Microsoft Docs
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
- VS.WebClient.Help.SCRIPT5000
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: ba2b0a2b-f0f8-4698-b335-a4ab6c166671
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c164b9b7d2989076a9dc0ef0bafba6159bc08885
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788778"
---
# <a name="cannot-assign-to-39this39"></a>Nelze přiřadit k & č. 39; to & č. 39;
Pokus o přiřazení hodnoty k **to**. **to** je [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] – klíčové slovo, který odkazuje buď:  
  
-   objekt aktuálně spuštění metody,  
  
-   globální objekt, pokud není žádná aktuální metoda (nebo metodu nepatří do jakýkoliv jiný objekt).  
  
 Je metoda [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] funkci, která je volána prostřednictvím objektu. Uvnitř metody **to** – klíčové slovo je odkaz na objekt metoda byla vyvolána prostřednictvím (který se stane, že jako objekt vytvořený vyvoláním konstruktoru třídy s **nové** operátor).  
  
 Uvnitř metody, můžete použít **to** k odkazování na aktuální objekt, ale nelze přiřadit novou hodnotu na **to**.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   Nepokoušejte se přiřadit **to**. Pro přístup k vlastnosti nebo metody instancí objektu, použijte operátor tečky (například v kruhu **.** RADIUS).  
  
    > [!NOTE]
    >  Nelze název proměnné vytvořené uživatelem **to**; je [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] vyhrazené slovo.  
  
## <a name="see-also"></a>Viz také  
 [Tento příkaz](../../javascript/reference/this-statement-javascript.md)   
 [Řešení potíží se skripty](../../javascript/advanced/troubleshooting-your-scripts-javascript.md)