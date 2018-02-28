---
title: "Nejčastější dotazy týkající se ladění snímku | Microsoft Docs"
ms.date: 11/07/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugger
ms.assetid: 944f1eb0-a74b-4d28-ae2b-a370cd869add
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: fd2ca2bf48c50b0ea5b44654d0711ba162313f04
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="frequently-asked-questions-for-snapshot-debugging-in-visual-studio"></a>Nejčastější dotazy k ladění snímku v sadě Visual Studio

Tady je seznam dotazů, které by mohlo dojít při ladění aplikací pro živé Azure pomocí ladicího programu snímku.

#### <a name="what-is-the-performance-cost-of-taking-a-snapshot"></a>Co je výkonu náklady na pořízení snímku?

Když ladicí program snímku zaznamená snímek vaší aplikace, je větvení proces aplikace a pozastavení forked kopie. Při ladění snímku, kterou ladíte forked kopii proces. Tento proces trvá jenom 10 20 milisekund ale nekopíruje haldě úplné aplikace; Namísto toho zkopíruje pouze tabulky stránky, zkopírujte na zápis na stránkách. Pokud některé z vaší aplikace objektů při změně haldy, jejich příslušné stránky se pak zkopírují. Každý snímek proto má velmi malé náklady v paměti (v řádu stovky kilobajtech pro většinu aplikací). 

#### <a name="what-happens-if-i-have-a-scaled-out-azure-app-service-multiple-instances-of-my-app"></a>Co se stane, když mám instancemi Azure App Service (více instance Moje aplikace)?

Až budete mít více instancí aplikace, snappoints použije na všechny jednu instanci. Pouze první snappoint narazí s podmínky zadané vytvoří snímek. Pokud máte více snappoints, další snímky pocházet ze stejné instance, který vytvořili první snímku. Logpoints posílá ve výstupním okně zobrazí pouze zprávy z jedné instance při logpoints odeslat protokoly aplikací odesílání zpráv z všechny instance. 

#### <a name="how-does-the-snapshot-debugger-load-symbols"></a>Jak načíst ladicí program snímku symboly?

Ladicí program snímku vyžaduje mít odpovídající symboly pro vaši aplikaci buď místně nebo nasadit do Azure App Service (vložené soubory PDB nejsou aktuálně podporovány). Ladicí program snímku automaticky stáhne symboly z Azure App Service. Od verze Visual Studio 2017 nasadí verze 15.2, nasazení do Azure App Service také symboly vaší aplikace.

#### <a name="does-the-snapshot-debugger-work-against-release-builds-of-my-application"></a>Funguje ladicí program snímku proti verze sestavení Moje aplikace?

Ano – snímku ladicí program měla fungovat s verzí sestavení. Když snappoint je umístěn ve funkci, znovu zkompiluje zpět do ladicí verze, takže je debuggable funkce. Pokud zastavíte ladicí program snímku, funkce se vrátíte na jejich sestavení pro vydání. 

#### <a name="can-logpoints-cause-side-effects-in-my-production-application"></a>Může způsobit logpoints vedlejší účinky v mé produkční aplikace?

Prakticky žádná - vyhodnocují všechny zprávy protokolu, které přidáte do vaší aplikace. V aplikaci nelze způsobí žádné vedlejší účinky. Některé nativní vlastnosti však nemusí být přístupné pomocí logpoints. 

#### <a name="does-the-snapshot-debugger-work-if-my-server-is-under-load"></a>Funguje snímku ladicí program, pokud je server zatížen?

Ano, ladění snímku lze pracují pro servery zatížení. Ladicí program snímku omezí generovaný a není zachycení snímků v situacích, kdy se nízkou množství volné paměti na serveru.

#### <a name="how-do-i-uninstall-the-snapshot-debugger"></a>Jak odinstaluji snímku ladicí program?

Můžete odinstalovat rozšíření lokality snímku ladicí program na App Service pomocí následujících kroků:

1. Vypnout aplikaci služby buď pomocí Průzkumníku cloudu v sadě Visual Studio nebo portálu Azure.
1. Přejít na Web App Service Kudu (tedy yourappservice. **SCM**. azurewebsites.net) a přejděte do **lokality rozšíření**.
1. Klikněte na tlačítko X na rozšíření lokality ladicí program snímku jeho odebrání.

## <a name="see-also"></a>Viz také

[Ladění v sadě Visual Studio](../debugger/index.md)  
[Ladění za provozu aplikace ASP.NET pomocí snímku ladicí program](../debugger/debug-live-azure-applications.md)  
[Řešení potíží a známé problémy pro ladění snímku](../debugger/debug-live-azure-apps-troubleshooting.md)
