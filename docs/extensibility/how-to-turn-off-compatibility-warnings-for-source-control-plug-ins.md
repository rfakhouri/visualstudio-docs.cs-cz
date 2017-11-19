---
title: "Vypnout kompatibility upozornění pro zdroj ovládacího prvku zásuvné moduly | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- source control plug-ins, turning off compatibility warnings
- compatibility warnings, turning off
ms.assetid: ba318e12-921b-4b7a-a8c2-12c712be1dbf
caps.latest.revision: "21"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 93db7526e7d6ba3eccf86e8c9769a1d9e9af3519
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-turn-off-compatibility-warnings-for-source-control-plug-ins"></a>Postupy: vypnutí kompatibility upozornění pro moduly plug-in programu zdroj ovládacího prvku
Uživatel může zobrazit několik kompatibility upozornění, když využívání zdrojového kódu v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Upozornění uvedené závisí na možnostech modulu plug-in zdrojového kódu a je možné zakázat jako podrobné sem.  
  
### <a name="to-disable-the-warning-to-ensure-optimal-source-control-integration-with-visual-studio"></a>Chcete-li zakázat upozornění: "zajistit optimální zdroj integrace ovládacích prvků pomocí sady Visual Studio..."  
  
-   Nastavte následující položku registru (přidání hodnota v případě potřeby):  
  
     HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\8.0\SourceControl\DontDisplayCheckDotNETCompatible = DWORD: 00000001  
  
     Toto upozornění se zobrazí u všech jinou hodnotu než[!INCLUDE[vsvss](../extensibility/includes/vsvss_md.md)] moduly plug-in.  
  
### <a name="to-disable-the-warning-the-installed-source-control-provider-does-not-support-all-the-capabilities"></a>Chcete-li zakázat upozornění: "poskytovatele správy nainstalované zdrojového kódu... všechny funkce nepodporuje"  
  
-   Nastavte následující hodnoty registru dva (přidání hodnoty v případě potřeby):  
  
     HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\8.0\SourceControl\WarnedOldMSSCCIProvider = DWORD: 00000000  
  
     HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\8.0\SourceControl\UseOldSCC = DWORD: 00000001  
  
     Toto upozornění se zobrazí, pokud modul plug-in správy zdroje nepodporuje explicitně vícenásobný přístup pro více projektů (tj. Pokud ho můžete zkontrolovat ve pouze jeden soubor a projekt v čase).  
  
     Je nejvhodnější pro podporu vícenásobný přístup (`SCC_CAP_REENTRANT` schopností); to se odebrat toto upozornění. Ale pokud tato podpora není možné, můžete nastavit tyto položky registru.  
  
## <a name="see-also"></a>Viz také  
 [Příznaky schopností](../extensibility/capability-flags.md)