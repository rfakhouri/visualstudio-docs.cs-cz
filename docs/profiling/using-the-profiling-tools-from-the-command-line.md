---
title: Pomocí profilace z příkazového řádku nástroje | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- command line, performance tools
- command-line tools, performance tools
- profiling tools,command line
- tools, command-line
- command line, tools
ms.assetid: 6593fa82-181e-4009-a0ed-02aa24c2c063
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 936d2bfe4eecd3e36553cef7c5779f201e190619
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56615816"
---
# <a name="use-the-profiling-tools-from-the-command-line"></a>Použití nástrojů pro profilaci z příkazového řádku
Můžete použít nástroje příkazového řádku [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nástroje pro profilaci sady do profilu aplikace příkazového řádku a k automatizaci profilace pomocí dávkových souborech a skriptování. Můžete také vygenerovat soubory sestav z příkazového řádku. Zjednodušené samostatného profileru můžete použít ke shromažďování dat na počítačích, které nemají [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nainstalované.

> [!NOTE]
>  Rozšířené funkce zabezpečení v systému Windows 8 a Windows Server 2012 vyžadují významné změny ve způsobu, jakým profiler systému Visual Studio na těchto platformách shromažďuje data. U aplikací pro UPW také vyžadují nové techniky kolekce. Zobrazit [nástroje pro výkon v aplikacích Windows 8 a Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).

## <a name="common-tasks"></a>Běžné úkoly

| Úloha | Související obsah |
| - | - |
| **Nastavte umístění symbolů:** Pokud chcete zobrazit názvy funkcí a parametry, profiler musí mít přístup k symbolu (. *soubor PDB*) soubory profilovaných binárních souborů. Tyto soubory by měly obsahovat soubory symbolů pro Microsoft operační systém a aplikace, které chcete zobrazit v analýze. Abyste měli jistotu, že máte správný, můžete použít veřejné Microsoft symbol server. *pdb* soubory pro binární soubory Microsoft. | -   [Jak: Zadejte umístění souborů se symboly z příkazového řádku](../profiling/how-to-specify-symbol-file-locations-from-the-command-line.md) |
| **Profilace aplikace:** Nástroje příkazového řádku a možnosti, které použijete k profilu cílové aplikace závisí na typu aplikace, metodu profilace a určuje, zda je cíl spravované nebo nativní aplikaci. | -   [Použití metod profilace z příkazového řádku](../profiling/using-profiling-methods-to-collect-performance-data-from-the-command-line.md)<br />-   [Samostatné aplikace profilu](../profiling/command-line-profiling-of-stand-alone-applications.md)<br />-   [Webové aplikace ASP.NET profilu](../profiling/command-line-profiling-of-aspnet-web-applications.md)<br />-   [Profil služby](../profiling/command-line-profiling-of-services.md) |
| **Vytvořte sestavy .xml a CSV:** Datové soubory, které lze zobrazit v rozhraní pro profilaci příkazového řádku vytvoří [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Můžete také vygenerovat. *xml* nebo hodnot oddělených čárkami (. *sdílený svazek clusteru*) soubory dat pomocí příkazového řádku nástroje VSPerfReport. | -   [Vytváření sestav profileru z příkazového řádku](../profiling/creating-profiler-reports-from-the-command-line.md)<br />-   [VSPerfReport](../profiling/vsperfreport.md) |
| **Profil kód v počítačích bez sady Visual Studio:** Samostatný profiler nástrojů pro profilaci sady můžete použít ke shromažďování dat pro aplikace na počítače, které nemají [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nainstalované. | -   [Jak: Instalace samostatného profileru](../profiling/how-to-install-the-stand-alone-profiler.md) |

## <a name="reference"></a>Odkaz
- [Odkaz na příkazový řádek nástrojů pro profilaci](../profiling/command-line-profiling-tools-reference.md)

## <a name="see-also"></a>Viz také:
- [Prohlížeč výkonu](../profiling/performance-explorer.md)