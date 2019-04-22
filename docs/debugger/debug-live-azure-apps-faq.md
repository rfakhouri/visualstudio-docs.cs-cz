---
title: Nejčastější dotazy k ladění snímků | Dokumentace Microsoftu
ms.date: 11/07/2017
ms.topic: reference
helpviewer_keywords:
- debugger
ms.assetid: 944f1eb0-a74b-4d28-ae2b-a370cd869add
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7ea593ad5f88ba29f6b1c0d7c64a129b8f71c7f5
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2019
ms.locfileid: "58857071"
---
# <a name="frequently-asked-questions-for-snapshot-debugging-in-visual-studio"></a>Nejčastější dotazy k ladění snímků v sadě Visual Studio

Tady je seznam dotazů, ke kterým může při ladění pomocí ladicího programu snímků živé aplikace Azure.

#### <a name="what-is-the-performance-cost-of-taking-a-snapshot"></a>Co je náklady na pořízení snímku?

Pokud ladicí program snímků zachytí snímek vaší aplikace, větve proces aplikací a pozastaví rozvětveného kopírování. Při ladění snímku, kterou ladíte proti rozvětveného kopii procesu. Tento proces trvá jenom 10-20 MS ale nekopíruje haldě úplné aplikace. Místo toho zkopíruje pouze tabulky stránky a zkopírování při zápisu na stránkách. Pokud některé objekty vaší aplikace na změnu haldy příslušných stránkách s poté zkopírován. To je syrovátky jednotlivých snímků má malé v paměti náklady (v řádu stovek kB pro většinu aplikací).

#### <a name="what-happens-if-i-have-a-scaled-out-azure-app-service-multiple-instances-of-my-app"></a>Co se stane, když mám horizontálním navýšením kapacity služby Azure App Service (více instancí aplikace)?

Pokud máte více instancí vaší aplikace, snímkovacích bodů: použije na každý jednu instanci. Pouze první snímkovací bod k dosažení s podmínkami uvedenými vytvoří snímek. Pokud máte více snímkovacích bodů: novější snímky pocházet ze stejné instance, kterou vytvořili první snímek. Protokolovací body odesílané do okna výstup se zobrazí jen zprávy z jedné instance, zatímco odesílat protokoly aplikací protokolovacích bodů: odesílání zpráv z každé instance.

#### <a name="how-does-the-snapshot-debugger-load-symbols"></a>Jak Snapshot Debugger načíst symboly

Snapshot Debugger vyžaduje, abyste měli odpovídající symboly pro vaši aplikaci, místní nebo nasazenou do služby Azure App Service. (Vložené soubory PDB se momentálně nepodporují.) Snapshot Debugger automaticky stahuje symboly ze služby Azure App Service. Od verze Visual Studio 2017 verze 15.2, nasazení do služby Azure App Service také nasadí symboly vaší aplikace.

#### <a name="does-the-snapshot-debugger-work-against-release-builds-of-my-application"></a>Funguje Snapshot Debugger pro buildy vydaných verzí mojí aplikace?

Ano – Snapshot Debugger by měla fungovat pro buildy vydaných verzí. Pokud snímkovacího bodu je umístěn ve funkci, funkci přepsán zpět do ladicí verze, takže laditelný. Při zastavení ladicího programu snímků vrací funkce verze sestavení pro vydání.

#### <a name="can-logpoints-cause-side-effects-in-my-production-application"></a>Může způsobit protokolovacích bodů: vedlejší účinky v produkční aplikace?

Prakticky ne - vyhodnocují všechny zprávy protokolu, které přidáte do vaší aplikace. Ve vaší aplikaci se nemůže způsobit žádné vedlejší účinky. Některé vlastnosti nativní však nemusí být přístupný pomocí protokolovacích bodů.

#### <a name="does-the-snapshot-debugger-work-if-my-server-is-under-load"></a>Funguje Snapshot Debugger při zatížení serveru?

Ano, ladění snímků může fungovat pro servery v zatížení. Snapshot Debugger omezuje a nebude zachycení snímků v situacích, ve kterých je nízká množství volné paměti na serveru.

#### <a name="how-do-i-uninstall-the-snapshot-debugger"></a>Jak odinstaluji Snapshot Debugger?

Odinstalovat rozšíření pro Snapshot Debugger web ve službě App Service pomocí následujících kroků:

1. Vypnout aplikaci služby prostřednictvím Průzkumníka cloudu v sadě Visual Studio nebo Azure portal.
1. Přejděte na Web App Service Kudu (to znamená, yourappservice. **Správce řízení služeb**. azurewebsites.net) a přejděte do **rozšířením webu**.
1. Kliknutím na křížek v rozšíření webu pro Snapshot Debugger jeho odstranění.

#### <a name="why-are-ports-opened-during-a-snapshot-debugger-session"></a>Proč jsou otevřené porty během relace Snapshot Debugger?

Snapshot Debugger je potřeba otevřít sadu porty Pokud chcete ladit snímkům pořízeným v Azure, jde o stejné porty vyžadované pro vzdálené ladění. [Můžete najít seznam portů zde](../debugger/remote-debugger-port-assignments.md).

## <a name="see-also"></a>Viz také:

- [Ladění v sadě Visual Studio](../debugger/index.md)
- [Ladění živé aplikace v ASP.NET pomocí ladicího programu snímků](../debugger/debug-live-azure-applications.md)
- [Ladění za provozu technologie ASP.NET Azure virtuální Machines\Virtual počítače Škálovací sady pomocí ladicího programu snímků](../debugger/debug-live-azure-virtual-machines.md)
- [Ladění za provozu technologie ASP.NET Kubernetes se službou Azure pomocí ladicího programu snímků](../debugger/debug-live-azure-kubernetes.md)
- [Řešení potíží a známé problémy pro ladění snímků](../debugger/debug-live-azure-apps-troubleshooting.md)