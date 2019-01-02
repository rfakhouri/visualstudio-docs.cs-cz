---
title: Jedna nebo více vlastností v souboru .ofs nejsou pro vybranou třídu zpráv platné.
ms.date: 02/02/2017
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
ms.openlocfilehash: 6d6469c48def1a5d21eb160cb4ad6d14704bc101
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53909122"
---
# <a name="one-or-more-properties-in-the-ofs-file-are-not-valid-for-the-message-class-selected"></a>Jedna nebo více vlastností v souboru .ofs nejsou pro vybranou třídu zpráv platné.
  Tato chyba se zobrazí, když importujete oblasti formuláře navržené v aplikaci Outlook, ale nejsou kompatibilní s tříd zpráv, které jste vybrali na poslední stránce jednoho nebo více polí v oblasti formuláře **novou oblast formuláře** průvodce.  

Například můžete vybrat **úkolů (IPM. Úkol)** na poslední stránce **novou oblast formuláře** průvodce. Pokud má oblast formuláře **adresa do zaměstnání** pole, protože úloha nemá pracovní adresy obdržíte k této chybě. Proto **adresa do zaměstnání** pole není kompatibilní s `IPM.Task` message – třída.  
  
 Můžete vybrat **úkolů (IPM. Úkol)** na poslední stránce **novou oblast formuláře** průvodce. Pokud má oblast formuláře **adresa do zaměstnání** pole, protože úloha nemá pracovní adresy obdržíte k této chybě. Proto **adresa do zaměstnání** pole není kompatibilní s `IPM.Task` message – třída.  
  
## <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   Na poslední stránce **novou oblast formuláře** průvodce, vyberte třídu zpráv, který je kompatibilní s poli na oblast formuláře.  
  
-   V Návrháři formulářů v Outlooku odeberte pole, která nejsou kompatibilní s tříd zpráv. Odebrat pole, která máte v plánu vyberte na poslední stránce **novou oblast formuláře** průvodce.  
  
## <a name="see-also"></a>Viz také:  
 [Návod: Import oblasti formuláře navržené v aplikaci Outlook](../vsto/walkthrough-importing-a-form-region-that-is-designed-in-outlook.md)  
