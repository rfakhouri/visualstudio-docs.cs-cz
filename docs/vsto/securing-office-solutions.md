---
title: Zabezpečení řešení pro systém Office
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office development in Visual Studio, security
- Office applications [Office development in Visual Studio], security
- security [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: dd86b7c15fa198b37ce15c75b13d2863f56ca3ba
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34693367"
---
# <a name="secure-office-solutions"></a>Zabezpečení řešení pro systém Office
  Model zabezpečení pro řešení pro systém Office zahrnuje několik technologií: [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)], [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)], v Centru zabezpečení v Microsoft Office a zónu lokalit s omezeným přístupem aplikace Internet Explorer. Následující části popisují, jak fungují funkce různých zabezpečení:  
  
-   [Vztah důvěryhodnosti grant řešení pro systém Office](#GrantingTrustToSolutions)  
  
-   [Udělení důvěryhodnosti do dokumentů](#GrantingTrustToDocuments)  
  
-   [Udělit vztah důvěryhodnosti, při použití Instalační služby systému Windows](#GrantingTrustWindowsInstaller)  
  
-   [Specifické aspekty zabezpečení pro řešení Office](#Security)  
  
-   [Zabezpečení během vývoje](#SecurityDuringDeployment)  
  
-   [Visual Studio Tools for Office runtime](#VisualStudioToolsForOfficeRuntime)  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
##  <a name="GrantingTrustToSolutions"></a> Vztah důvěryhodnosti grant řešení pro systém Office  
 Udělení vztah důvěryhodnosti řešení pro systém Office znamená úprava zásady zabezpečení jednotlivých koncových uživatelů tak, aby důvěřoval řešení Office podle následujících informací:  
  
-   Certifikát použitý k podepsání manifestu nasazení.  
  
-   Adresa URL manifest nasazení.  
  
 Další informace najdete v tématu [udělit vztah důvěryhodnosti řešení pro systém Office](../vsto/granting-trust-to-office-solutions.md).  
  
##  <a name="GrantingTrustToDocuments"></a> Udělení důvěryhodnosti do dokumentů  
 Přizpůsobení na úrovni dokumentu vyžaduje, aby v adresáři, který je určený jako důvěryhodné umístění dokumentu. Další informace najdete v tématu [udělit vztah důvěryhodnosti k dokumentům](../vsto/granting-trust-to-documents.md).  
  
##  <a name="GrantingTrustWindowsInstaller"></a> Udělit vztah důvěryhodnosti, při použití Instalační služby systému Windows  
 Instalační služba systému Windows můžete použít k vytvoření souboru MSI instalace řešení pro systém Office do adresář Program Files, který vyžaduje oprávnění správce. Řešení Office v adresáři Program Files Visual Studio 2010 Tools for Office runtime zvažuje těchto řešení pro systém Office být důvěryhodné a nezobrazuje vztahu důvěryhodnosti ClickOnce.  
  
##  <a name="Security"></a> Specifické aspekty zabezpečení pro řešení Office  
 Funkce zabezpečení poskytované [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)], [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)], a aplikace Microsoft Office může pomoct chránit proti celou řadu možných bezpečnostních hrozeb v řešeních pro systém Office. Další informace najdete v tématu [specifické aspekty zabezpečení pro řešení Office](../vsto/specific-security-considerations-for-office-solutions.md).  
  
##  <a name="SecurityDuringDeployment"></a> Zabezpečení během vývoje  
 Visual Studio pro usnadnění vývojových procesech nastaví zásady zabezpečení, které jsou potřeba ke spuštění a ladění řešení ve vašem počítači pokaždé, když vytváříte projekt. V některých scénářích může být nutné provést další bezpečnostní kroky k vývoji projektu.  
  
### <a name="document-level-solutions"></a>Řešení na úrovni dokumentu  
 Plně kvalifikovaná cesta dokumentu musí přidat do seznamu důvěryhodných lokalit v aplikaci Microsoft Office, pokud vyvíjíte následující typy projektů:  
  
-   Řešení, které jsou v síťové sdílené složky, například na úrovni dokumentu  *\\\servername\sharename*.  
  
-   Dokument úrovni řešení pro Word, použít *.doc* nebo *DOCM* soubory.  
  
 Zahrnout podadresáře umístění dokumentu přidejte do seznamu důvěryhodných umístění nebo konkrétně zahrnout ladění a vytvořit složky. Další informace najdete v článku Microsoft Office Online nápověda [Create, odebrat nebo změnit důvěryhodném umístění pro soubory](https://support.office.com/en-au/article/Create-remove-or-change-a-trusted-location-for-your-files-f5151879-25ea-4998-80a5-4208b3540a62).  
  
### <a name="temporary-certificates"></a>Dočasné certifikáty  
 Visual Studio vytvoří dočasný certifikátu, pokud podpisový certifikát již neexistuje. Doporučujeme použít toto dočasný certifikát pouze během vývoje a zakoupit certifikát oficiální pro nasazení.  
  
 Po první sestavení projektu služby Office, se vygeneruje dočasné certifikát. Při příštím stisknutí klávesy **F5**, protože projekt je označen jako změnit, pokud je certifikát přidat, je znovu sestavit projekt.  
  
 Po chvíli se může být velký počet certifikátů dočasné, byste měli vymazat, někdy dočasné certifikáty.  
  
##  <a name="VisualStudioToolsForOfficeRuntime"></a> Visual Studio Tools for Office runtime  
 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Funkce k ověření identity vydavatele a oprávnění, kterým je uděleno oprávnění k přizpůsobení. Ověří, tato oprávnění prostřednictvím sekvenci kontroly zabezpečení.  
  
### <a name="security-during-customization-loading"></a>Zabezpečení během přizpůsobování načítání  
 Při načítání přizpůsobení na úrovni dokumentu [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] vždy zkontroluje, jestli dokument v seznamu důvěryhodných umístění. Kromě toho modul runtime zkontroluje, jestli řešení požadavky FullTrust v manifestu aplikace. Při načítání přizpůsobení provádí žádné další kontroly zabezpečení.  
  
### <a name="sequence-of-security-checks-during-installation"></a>Pořadí kontrol zabezpečení během instalace  
 Při instalaci nebo aktualizaci, řešení Office [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] provádí řadu kontrol zabezpečení v konkrétní pořadí slouží k určení důvěryhodnosti. Řešením je instalace nebo aktualizace pouze v případě, že modul runtime určuje řešení, které je důvěryhodný.  
  
 Můžete spustit proces instalace čtyři způsoby: spuštěním instalačního programu, otevřením manifest nasazení, otevřením hostitele aplikace Microsoft Office nebo spuštěním *VSTOInstaller.exe*.  
  
 První kontrola zabezpečení se vztahuje pouze na úrovni dokumentu řešení. Dokument řešení úrovni dokumentu musí být v důvěryhodném umístění. Pokud dokument je ve sdílené složce vzdálené sítě, nebo má *.doc* nebo *DOCM* příponou názvu souboru dokumentu umístění musí být přidána do seznamu důvěryhodných umístění. Další informace najdete v tématu [udělit vztah důvěryhodnosti k dokumentům](../vsto/granting-trust-to-documents.md).  
  
 ![Zabezpečení VSTO – instalace z aplikace Microsoft Office](../vsto/media/host-install.png "zabezpečení VSTO – instalace z aplikace Microsoft Office")  
  
 Další sadu kontrol zabezpečení jsou z [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] a ClickOnce. Předávání těchto kontrol, musíte požádat o oprávnění FullTrust řešení pro systém Office, byly podepsány certifikátem, který není uveden v seznamu nedůvěryhodné vydavatele a může být v umístění, která není v zóně Internet Explorer s omezeným přístupem. Pokud je certifikát v seznamu Důvěryhodné vydavatele, řešení nainstalována okamžitě. Jinak pokud ji nedošlo k selhání jednoho kontrol, řešení nadále závěrečné sady kontroly.  
  
 ![Zabezpečení VSTO pro instalaci řešení](../vsto/media/installing.png "zabezpečení VSTO pro instalaci řešení")  
  
 Pokud [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] výzvu vztahu důvěryhodnosti je povolen a řešení dosud nebyl udělen vztahu důvěryhodnosti, modulu runtime vám umožní rozhodnutí o vztahu důvěryhodnosti má být provedeno koncovým uživatelem. Pokud uživatel uděluje vztah důvěryhodnosti k řešení, bude položka přidána do seznamu povolených uživatelů. Všechna řešení v seznamu uživatelů zahrnutí úplný vztah důvěryhodnosti a může být nainstalován a spuštěn.  
  
 Spouštění v sadě Visual Studio 2010, je seznam povolených položek přeskočí, pokud řešení Office je nainstalované pomocí Instalační služby systému Windows (MSI) do adresář Program Files. Další informace najdete v tématu [řešení důvěřovat Office s použitím seznamech povolených položek](../vsto/trusting-office-solutions-by-using-inclusion-lists.md).  
  
 ![Zabezpečení VSTO – instalace pomocí instalačního programu](../vsto/media/setup-vstoinstaller.png "zabezpečení VSTO – instalace pomocí instalačního programu")  
  
## <a name="see-also"></a>Viz také:  
 [Vztah důvěryhodnosti grant řešení pro systém Office](../vsto/granting-trust-to-office-solutions.md)   
 [Udělení důvěryhodnosti do dokumentů](../vsto/granting-trust-to-documents.md)   
 [Vztah důvěryhodnosti řešení Office s použitím seznamech povolených položek](../vsto/trusting-office-solutions-by-using-inclusion-lists.md)   
 [Postupy: konfigurace zabezpečení se seznamem povolených](../vsto/how-to-configure-inclusion-list-security.md)   
 [Postupy: podepisování řešení pro systém Office](../vsto/how-to-sign-office-solutions.md)   
 [Odstraňování problémů se zabezpečením řešení Office](../vsto/troubleshooting-office-solution-security.md)   
 [Manifesty aplikace pro řešení pro systém Office](../vsto/application-manifests-for-office-solutions.md)   
 [Manifesty nasazení pro řešení Office](../vsto/deployment-manifests-for-office-solutions.md)   
 [Referenční dokumentace technologie ClickOnce](/visualstudio/deployment/clickonce-reference)   
 [Nasazení řešení Office](../vsto/deploying-an-office-solution.md)  
  
  