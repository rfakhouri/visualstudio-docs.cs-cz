---
title: Použití profilace z příkazového řádku nástroje | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3b64bf3733fc99a63a3b8334174a59db8c1e5f29
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="using-the-profiling-tools-from-the-command-line"></a>Použití nástrojů pro profilaci z příkazového řádku
Můžete použít nástroje příkazového řádku z [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nástrojích pro profilaci do profilu aplikace příkazového řádku a automatizovat profilace skriptu a pomocí dávkové soubory. Můžete taky Generovat sestavy soubory na příkazovém řádku. Prosté samostatného profileru můžete použít ke shromažďování dat na počítačích, které nemají [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nainstalována.  
  
> [!NOTE]
>  Funkce Rozšířené zabezpečení v systému Windows 8 a Windows Server 2012 vyžaduje významné změny ve způsobu, jakým Visual Studio profiler shromažďuje data na těchto platformách. Aplikace UWP také vyžadují nové techniky kolekce. V tématu [nástroje pro sledování výkonu v aplikacích pro Windows 8 a Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
## <a name="common-tasks"></a>Obecné úlohy  
  
|Úloha|Související obsah|  
|----------|---------------------|  
|**Nastavte umístění symbolů:** Pokud chcete zobrazit názvy parametrů a funkce, profileru musí mít přístup k souborům symbolu (.pdb) PROFILOVANÉHO binárních souborů. Tyto soubory by měly obsahovat soubory symbolů pro Microsoft operační systém a aplikace, které chcete zobrazit v analýzy. Abyste měli jistotu, že máte správný PDB soubory pro binární soubory Microsoft můžete veřejného serveru Microsoft symbol.|-   [Postupy: určení umístění souboru se symboly z příkazového řádku](../profiling/how-to-specify-symbol-file-locations-from-the-command-line.md)|  
|**Profil aplikace:** nástroje příkazového řádku a možnosti, které použijete k profilu cílová aplikace závisí na typu aplikace, v případě metody profilování a jestli je cílový spravovaným nebo nativním aplikace.|-   [Použití metod profilace z příkazového řádku](../profiling/using-profiling-methods-to-collect-performance-data-from-the-command-line.md)<br />-   [Profilace samostatných aplikací](../profiling/command-line-profiling-of-stand-alone-applications.md)<br />-   [Profilace webových aplikací ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)<br />-   [Profilace služeb](../profiling/command-line-profiling-of-services.md)|  
|**Vytváření sestav .xml a CSV:** profilování na příkazovém řádku vytvoří datové soubory, které lze zobrazit v rozhraní pro [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Můžete také vygenerovat .xml nebo soubory hodnot oddělených čárkami (.csv) dat pomocí vsperfreport – nástroj příkazového řádku.|-   [Vytváření sestav profileru z příkazového řádku](../profiling/creating-profiler-reports-from-the-command-line.md)<br />-   [Vsperfreport –](../profiling/vsperfreport.md)|  
|**Profilování kódu v počítačích bez sady Visual Studio:** samostatného profileru nástrojích pro profilaci můžete použít ke shromažďování dat pro aplikace v počítačích, které nemají [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nainstalována.|-   [Postupy: Instalace samostatného profileru](../profiling/how-to-install-the-stand-alone-profiler.md)|  
  
## <a name="reference"></a>Odkaz  
 [Profilování nástroje pro příkazový řádek](../profiling/command-line-profiling-tools-reference.md)  
  
## <a name="see-also"></a>Viz také  
 [Prohlížeč výkonu](../profiling/performance-explorer.md)