---
title: "Zabezpečení, správy verzí a manifestu problémy v nasazeních ClickOnce | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- versioning, ClickOnce applications
- ClickOnce applications, Windows Vista User Account Control
- ClickOnce applications, versioning issues
- security, ClickOnce applications
- Windows 7, ClickOnce deployments
- ClickOnce applications, manifest issues
- User Account Control, ClickOnce applications
- Windows Vista, ClickOnce deployments
- manifests [ClickOnce]
- ClickOnce applications, security issues
ms.assetid: d5d0c90b-ac1a-44e2-88dc-0d0ffd881624
caps.latest.revision: "21"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: 603ff665e2c01abe62954e4e65e49a095d358b29
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="security-versioning-and-manifest-issues-in-clickonce-deployments"></a>Problémy se zabezpečením, správou verzí a manifestem v nasazeních ClickOnce
Existuje mnoho různých problémů s [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] zabezpečení, správu verzí aplikace a manifestu syntaxe a sémantikou, které může způsobit [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] není pro úspěšné nasazení.  
  
## <a name="clickonce-and-windows-vista-user-account-control"></a>ClickOnce a řízení uživatelských účtů systému Windows Vista  
 V [!INCLUDE[windowsver](../deployment/includes/windowsver_md.md)], ve výchozím nastavení aplikace spustit jako standardní uživatel, i v případě, že aktuální uživatel přihlášen pomocí účtu, který má oprávnění správce. Pokud aplikace musí provést akci, která vyžaduje oprávnění správce, obsahuje informace pro operační systém, který se potom zobrazí výzvu k zadání přihlašovacích údajů správce. Tuto funkci, která se nazývá řízení uživatelských účtů (UAC), zabrání aplikacím v provádění změn, které může mít vliv na celý operační systém bez výslovného souhlasu uživatele. Aplikace systému Windows deklarovat, že vyžadují toto zvýšení oprávnění tak, že zadáte `requestedExecutionLevel` atribut `trustInfo` části jejich manifestu aplikace.  
  
 Z důvodu riziko úniku aplikací útokům zvýšení oprávnění [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace nemůže požádat o zvýšení oprávnění, pokud je povolen nástroj Řízení uživatelských účtů pro klienta. Všechny [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace, která se pokouší nastavit jeho `requestedExecutionLevel` atribut `requireAdministrator` nebo `highestAvailable` nenainstaluje [!INCLUDE[windowsver](../deployment/includes/windowsver_md.md)].  
  
 V některých případech vaše [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace může pokus o spuštění s oprávněními správce z důvodu logika pro detekci instalační program [!INCLUDE[windowsver](../deployment/includes/windowsver_md.md)]. V takovém případě můžete nastavit `requestedExecutionLevel` atribut v manifestu aplikace na `asInvoker`. To způsobí, že je vlastní aplikace běžet bez zvýšení oprávnění. [!INCLUDE[vs_orcas_long](../debugger/includes/vs_orcas_long_md.md)]Tento atribut se automaticky přidá do všech manifestů aplikace.  
  
 Pokud vyvíjíte aplikaci, která vyžaduje oprávnění správce po celou dobu života aplikace, musíte zvážit nasazení aplikace pomocí technologie Instalační služby systému Windows (MSI). Další informace najdete v tématu [základy Instalační služby systému Windows](../extensibility/internals/windows-installer-basics.md).  
  
## <a name="online-application-quotas-and-partial-trust-applications"></a>Kvóty online aplikací a částečného vztahu důvěryhodnosti aplikace  
 Pokud vaše [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] spuštění online namísto prostřednictvím instalace aplikace, musí být přizpůsobena kvóty vyhrazené pro online aplikace. Také síťové aplikace, který je spuštěn v částečné důvěryhodnosti, například s omezenou sadu oprávnění zabezpečení, nemůže být větší než polovinu kvóty velikosti.  
  
 Další informace a pokyny o tom, jak změnit kvóty online aplikací najdete v tématu [ClickOnce – Přehled mezipaměti](../deployment/clickonce-cache-overview.md).  
  
## <a name="versioning-issues"></a>Správa verzí – potíže  
 Pokud přiřadíte silné názvy vaše sestavení a zvýší číslo verze sestavení tak, aby odrážela aktualizace aplikace se můžete setkat s problémy. Žádné sestavení zkompilovaného s odkazem na sestavení se silným názvem musí samotné zopakovat, nebo sestavení se pokusí odkázat na starší verzi. Sestavení se pokusí, protože sestavení používá starou hodnotu verze ve své žádosti vazby.  
  
 Řekněme například, že máte sestavení se silným názvem v jeho vlastní projektu verzi 1.0.0.0. Za kompilace sestavení, přidejte ji jako odkaz na projekt, který obsahuje hlavní aplikace. Pokud aktualizaci sestavení, zvýší na verzi 1.0.0.1 a pokuste se jej nasadit bez překompilování aplikace, aplikace nebude možné načíst sestavení za běhu.  
  
 Této chybě může dojít pouze v případě, že upravujete vaše [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] manifesty ručně; pokud generovat nasazení pomocí této chyby neměl [!INCLUDE[vsprvslong](../code-quality/includes/vsprvslong_md.md)].  
  
## <a name="specifying-individual-net-framework-assemblies-in-the-manifest"></a>Určení jednotlivých sestavení .NET Framework v manifestu  
 Aplikace se nepodaří načíst, pokud jste ručně upravili [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nasazení tak, aby odkazovaly na starší verzi [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] sestavení. Například pokud jste přidali odkaz na sestavení System.Net pro verzi [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] starší než verze zadaná v manifestu, pak by, dojde k chybě. Obecně byste se neměli pokoušet zadávat odkazy na jednotlivé [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] sestavení jako verze [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] na kterém běží aplikace, které je zadána v závislosti na manifest aplikace.  
  
## <a name="manifest-parsing-issues"></a>Analýzy chyb manifestu  
 Soubory manifestu, které jsou používány [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] jsou soubory formátu XML a musí být platný a ve správném formátu: musí orientují pravidla syntaxe jazyka XML a používat pouze elementy a atributy definované v příslušné schématu XML.  
  
 Něco, co může způsobit problémy v souboru manifestu je výběr název aplikace, který obsahuje speciální znaky, jako je například jeden nebo dvojité uvozovky. Název aplikace je součástí jeho [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] identity. [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]aktuálně neanalyzuje identity, které obsahují zvláštní znaky. Pokud vaše aplikace se nepodaří aktivovat, zajistěte, aby se používá pouze abecední a číselné znaky pro název a pokus o nasaďte jej znovu.  
  
 Pokud jste ručně upravili vaše manifesty nasazení nebo aplikace, můžete nechtěně poškozený je. Poškozený manifest zabrání správné [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] instalace. Tyto chyby můžete ladit v době běhu kliknutím **podrobnosti** na **Chyba ClickOnce** dialogové okno a číst chybovou zprávu do protokolu. V protokolu se zobrazí jednu z následujících zpráv:  
  
-   Popis Chyba syntaxe, číslo řádku a znak pozice, kdy došlo k chybě.  
  
-   Název elementu nebo atributu použitého v porušení schéma manifestu. Pokud jste ručně přidali XML do vašich manifestů, budete muset porovnat dodatky se schématem manifestu. Další informace najdete v tématu [Manifest aplikace ClickOnce](../deployment/clickonce-deployment-manifest.md) a [Manifest aplikace ClickOnce](../deployment/clickonce-application-manifest.md).  
  
-   Došlo ke konfliktu ID. Odkazy závislostí v manifestech nasazení a aplikací, musí být jedinečné v obou jejich `name` a `publicKeyToken` atributy. Pokud oba atributy odpovídají mezi dvěma prvky v manifestu, analýza manifestu se nezdaří.  
  
## <a name="precautions-when-manually-changing-manifests-or-applications"></a>Bezpečnostní opatření při ruční změna manifesty nebo aplikace  
 Když aktualizujete manifest aplikace, musíte znovu podepsat manifest aplikace i manifest nasazení. Manifest nasazení obsahuje odkaz na manifest aplikace, která zahrnuje hodnota hash tohoto souboru a jeho digitální podpis.  
  
### <a name="precautions-with-deployment-provider-usage"></a>Opatření používání poskytovatele nasazení  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] – Manifest nasazení má `deploymentProvider` vlastnost, která odkazuje na úplnou cestu k umístění, ze kterých by měla aplikace nainstalována a údržba:  
  
```  
<deploymentProvider codebase="http://myserver/myapp.application" />  
```  
  
 Tato cesta je nastavena, když [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] vytvoří aplikace a je povinná pro nainstalované aplikace. Cesta odkazuje na standardní umístění kde [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] instalační program nainstaluje aplikaci a vyhledejte aktualizace. Pokud používáte **xcopy** příkaz pro kopírování [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace do jiného umístění, ale neumožňuje změnit `deploymentProvider` vlastnost, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] bude nadále odkazovat zpět do původního umístění při pokusu o stažení aplikace.  
  
 Pokud chcete k přesunutí nebo zkopírování aplikace, je nutné také aktualizovat `deploymentProvider` cestu, takže ve skutečnosti instalaci klienta z nového umístění. Aktualizace této cesty obavu, hlavně pokud jste nainstalovali aplikace. Pro online aplikace, které jsou vždy spouštěny prostřednictvím původní adresu URL, nastavení `deploymentProvider` je volitelný. Pokud `deploymentProvider` není nastaven, bude uplatněn; jinak hodnota adresy URL používá ke spuštění aplikace se použije jako základní adresu URL pro stažení souborů aplikace.  
  
> [!NOTE]
>  Při každé aktualizaci manifest musíte také podepsat ji znovu.  
  
## <a name="see-also"></a>Viz také  
 [Řešení potíží s nasazením ClickOnce](../deployment/troubleshooting-clickonce-deployments.md)   
 [Zabezpečování aplikací ClickOnce](../deployment/securing-clickonce-applications.md)   
 [Výběr strategie nasazení ClickOnce](../deployment/choosing-a-clickonce-deployment-strategy.md)