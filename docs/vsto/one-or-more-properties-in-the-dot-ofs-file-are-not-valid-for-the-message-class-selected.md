---
title: "Jeden nebo více vlastností v souboru .ofs nejsou pro vybranou třídu zpráv platné | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VSTO.NewFormRegionWizard.OFSPropertyError
dev_langs:
- VB
- CSharp
ms.assetid: ca9e2ec1-df96-45ca-9611-cec47edfe1e4
caps.latest.revision: "8"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: ddaad272326c4cd77e0e54bd7216974181c77a72
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="one-or-more-properties-in-the-ofs-file-are-not-valid-for-the-message-class-selected"></a>Jedna nebo více vlastností v souboru .ofs nejsou pro vybranou třídu zpráv platné.
  Tato chyba se zobrazí, když importujete oblasti formuláře navržené v aplikaci Outlook, ale nejsou kompatibilní s třídami zpráv, které jste vybrali na poslední stránce minimálně jedno pole v oblasti formuláře **nové oblasti formuláře** průvodce.  
  
 Například můžete vybrat **úloh (IPM. Úlohy)** na poslední stránce **nové oblasti formuláře** průvodce. Pokud obsahuje oblasti formuláře **podnikání** pole, zobrazí se tato chyba protože úloha nemá adresu firmy. Proto **podnikání** pole není kompatibilní s IPM. Třída zpráva úlohy.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   Na poslední stránce **nové oblasti formuláře** průvodce, vyberte třídu zpráv, který je kompatibilní s pole v oblasti formuláře.  
  
-   V Návrháři formulářů v aplikaci Outlook odebrat pole, která nejsou kompatibilní s třídami zpráv, které chcete na poslední stránce vyberte **nové oblasti formuláře** průvodce.  
  
## <a name="see-also"></a>Viz také  
 [Návod: Import oblasti formuláře navržené v aplikaci Outlook](../vsto/walkthrough-importing-a-form-region-that-is-designed-in-outlook.md)  
  
  