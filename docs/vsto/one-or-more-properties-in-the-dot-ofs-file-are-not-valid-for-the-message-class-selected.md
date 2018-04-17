---
title: Jeden nebo více vlastností v souboru .ofs nejsou pro vybranou třídu zpráv platné | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VSTO.NewFormRegionWizard.OFSPropertyError
dev_langs:
- VB
- CSharp
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 7ac9f5ab05ba6ed858946b5f665d850eea51c230
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="one-or-more-properties-in-the-ofs-file-are-not-valid-for-the-message-class-selected"></a>Jedna nebo více vlastností v souboru .ofs nejsou pro vybranou třídu zpráv platné.
  Tato chyba se zobrazí, když importujete oblasti formuláře navržené v aplikaci Outlook, ale nejsou kompatibilní s třídami zpráv, které jste vybrali na poslední stránce minimálně jedno pole v oblasti formuláře **nové oblasti formuláře** průvodce.  
  
 Například můžete vybrat **úloh (IPM. Úlohy)** na poslední stránce **nové oblasti formuláře** průvodce. Pokud obsahuje oblasti formuláře **podnikání** pole, zobrazí se tato chyba protože úloha nemá adresu firmy. Proto **podnikání** pole není kompatibilní s IPM. Třída zpráva úlohy.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   Na poslední stránce **nové oblasti formuláře** průvodce, vyberte třídu zpráv, který je kompatibilní s pole v oblasti formuláře.  
  
-   V Návrháři formulářů v aplikaci Outlook odebrat pole, která nejsou kompatibilní s třídami zpráv, které chcete na poslední stránce vyberte **nové oblasti formuláře** průvodce.  
  
## <a name="see-also"></a>Viz také  
 [Návod: Import oblasti formuláře navržené v aplikaci Outlook](../vsto/walkthrough-importing-a-form-region-that-is-designed-in-outlook.md)  
  
  