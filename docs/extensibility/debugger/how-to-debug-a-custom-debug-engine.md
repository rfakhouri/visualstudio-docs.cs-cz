---
title: 'Postupy: Ladění modul vlastní ladění | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debug engines, debugging
- debugging [Debugging SDK], custom debug engines
ms.assetid: df27a8d6-3938-45ff-b47f-b684e80b38a0
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 95a2db2bc5e8990f536abc851941c337a1dee277
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-debug-a-custom-debug-engine"></a>Postupy: Ladění modul vlastní ladění
Typ projektu spustí modul ladění (DE) z <xref:Microsoft.VisualStudio.Shell.Interop.IVsDebuggableProjectCfg.DebugLaunch%2A> metoda. To znamená, že je DE spuštění pod kontrolou instanci [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] řízení typ projektu. Ale tuto instanci [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] nelze ladění DE. Jaké způsobem kroky vám umožní ladit vaše vlastní DE.  
  
> [!NOTE]
>  : V postupu "Ladění vlastní ladění modul" je nutné počkat DE spustit předtím, než můžete připojit k němu. Pokud jste na začátku vaší DE, který se zobrazí při spuštění je DE okno se zprávou, můžete připojit v daném okamžiku a zrušte zaškrtnutí pole zpráv pokračujte. Tímto způsobem můžete zachytit všechny DE události.  
  
> [!WARNING]
>  Musíte mít vzdálené ladění nainstalována před provedením následující procedury. V tématu [vzdálené ladění](../../debugger/remote-debugging.md) podrobnosti.  
  
### <a name="debugging-a-custom-debug-engine"></a>Ladění modul vlastní ladění  
  
1.  Spusťte msvsmon.exe, sledování vzdáleného ladění.  
  
2.  Z **nástroje** nabídky v msvsmon.exe, vyberte **možnosti** otevřete **možnosti** dialogové okno.  
  
3.  Vyberte možnost "žádné ověřování" a klikněte na **OK**.  
  
4.  Spuštění instance služby [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] a otevřete vlastní DE projekt.  
  
5.  Spusťte druhou instanci [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] a otevřete váš vlastní projekt, který spouští DE (pro vývoj, to je obvykle v experimentální podregistru, který je nastavený při instalaci VSIP).  
  
6.  V této druhé instance [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], načíst zdrojový soubor z vlastního projektu a spusťte program, který má ladit. Chvíli počkejte umožňující DE zatížení, nebo počkejte, dokud je dosáhl zarážky.  
  
7.  V první instance [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] (s projektu DE), vyberte **připojit k procesu** z **ladění** nabídky.  
  
8.  V **připojit k procesu** dialogové okno, změny **přenosu** k **vzdálené (nativní pouze s bez ověřování)**.  
  
9. Změna **kvalifikátor** na název počítače (Poznámka: není historii položky, takže je třeba zadat název pouze jednou).  
  
10. V **dostupné procesy** vyberte instanci vaše DE, která je spuštěná a klikněte na tlačítko **Attach** tlačítko.  
  
11. Po symboly načten v vaší DE, umístěte zarážky v kódu DE.  
  
12. Pokaždé, když zastavte a znovu spusťte proces ladění, opakujte kroky 6 až 10.  
  
### <a name="debugging-a-custom-project-type"></a>Ladění do vlastního typu projektu  
  
1.  Spustit [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] normální podregistru a zatížení projektu zadejte projektu (to je, zdrojů a typu projektu, není vytvoření instance typu vašeho projektu).  
  
2.  Otevřete vlastnosti projektu a přejděte na **ladění** stránky. Pro **příkaz**, zadejte cestu k [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE (ve výchozím nastavení je to *[jednotka]*\Program Files\Microsoft [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 8\Common7\IDE\devenv.exe).  
  
3.  Pro **argumenty příkazu**, typ `/rootsuffix exp` pro experimentální podregistru (vytvořen při instalaci VSIP).  
  
4.  Klikněte na tlačítko **OK** pro přijetí změn.  
  
5.  Stisknutím klávesy F5 spusťte typ vašeho projektu. Tím se spustí druhé instance [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
6.  V tomto okamžiku můžete umístit zarážky vašeho projektu typu zdrojového kódu.  
  
7.  V druhé instanci [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], načíst, nebo vytvořit novou instanci typu vašeho projektu. Při načítání nebo vytváření vašeho může být zarážky.  
  
8.  Ladění typ vašeho projektu.  
  
9. Pokud zvolíte možnost ladění proces spuštění Zavedenými, můžete provést kroky v postupu "Ladění vlastní ladění modul" pro připojení k vaší DE po jeho spuštění. Tím získáte tři instance [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] systémem: jeden pro váš projekt typu zdroj, druhý pro typu instancí projektu a třetí připojené k vaší DE.  
  
## <a name="see-also"></a>Viz také  
 [Vytvoření vlastního ladicího stroje](../../extensibility/debugger/creating-a-custom-debug-engine.md)