---
title: Zajistit jeho důvěryhodnost do řešení pro systém Office
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- security [Office development in Visual Studio], trust
- inclusion lists [Office development in Visual Studio], about inclusion lists
- trust [Office development in Visual Studio], 2007 Office system
- granting trust [Office development in Visual Studio]
author: John-Hart
ms.author: johnhart
manager: douge
ms.workload:
- office
ms.openlocfilehash: 49b2e66f35bf320d6eca04fd1b171a5e0c65132e
ms.sourcegitcommit: f6dd17b0864419083d0a1bf54910023045526437
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/27/2018
ms.locfileid: "53804783"
---
# <a name="grant-trust-to-office-solutions"></a>Zajistit jeho důvěryhodnost do řešení pro systém Office
  Zajistit jeho důvěryhodnost Office řešení znamená úpravy zásady zabezpečení v každém cílovém počítači důvěřovat řešení sestavení, manifest aplikace, manifest nasazení a dokumentu. Vztah důvěryhodnosti můžete vy nebo koncového uživatele udělit řešení pro Office.

 Úplný vztah důvěryhodnosti řešení pro Office můžete udělit pomocí podepisování manifestů aplikace a nasazení.

 Koncovým uživatelům můžete udělit důvěryhodnost řešení pro Office tak, že rozhodnutí o důvěryhodnosti [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] výzvu vztahu důvěryhodnosti.

 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]

##  <a name="Signing"></a> Vztah důvěryhodnosti řešení pomocí podepsání manifestů aplikace a nasazení
 Všechny aplikace a manifestů nasazení pro Office řešení musí být podepsané certifikátem, který identifikuje vydavatele. Certifikáty poskytují základ pro rozhodování o důvěryhodnosti.

 Dočasný certifikát je pro vás vytvořili a udělen vztah důvěryhodnosti v okamžiku sestavení, takže řešení se spustí při ladění. Pokud publikujete, který je podepsaný certifikátem dočasné řešení, koncový uživatel se vyzve k provedení rozhodnutí důvěryhodnosti.

 Pokud se řešení pomocí známého a důvěryhodného certifikátu řešení se automaticky nainstalují bez zobrazení výzvy koncového uživatele k provedení rozhodnutí důvěryhodnosti. Další informace o tom, jak získat certifikát pro podepisování najdete v tématu [ClickOnce and Authenticode](../deployment/clickonce-and-authenticode.md). Po získání certifikátu se certifikát musí být explicitně důvěryhodná přidáním do seznamu Důvěryhodní vydavatelé. Další informace najdete v tématu [jak: Přidání důvěryhodného vydavatele na klientský počítač pro aplikace ClickOnce](../deployment/how-to-add-a-trusted-publisher-to-a-client-computer-for-clickonce-applications.md).

 Pokud vývojář podepisuje řešení dočasné certifikátem, Správce může znovu podepsat přizpůsobení pomocí známého a důvěryhodného certifikátu pomocí Manifest Generation and Editing Tool (*mage.exe*), což je jedna z Nástroje sady Microsoft .NET Framework. Další informace o podepisování řešení najdete v tématu [jak: Podepisování řešení pro Office](../vsto/how-to-sign-office-solutions.md) a [jak: Podepsání manifestů aplikace a nasazení](../ide/how-to-sign-application-and-deployment-manifests.md).

##  <a name="TrustPrompt"></a>Vztah důvěryhodnosti řešení pomocí vztahu důvěryhodnosti ClickOnce
 [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] vyzve koncovému uživateli umožňují rozhodnutí důvěryhodnosti, pokud není žádná celou organizaci zásada, která důvěřuje certifikátu řešení. Pokud koncový uživatel uděluje vztah důvěryhodnosti k řešení, se vytvoří položka seznamu povolených položek, který obsahuje adresu URL a veřejný klíč pro uložení tohoto rozhodnutí důvěryhodnosti. Když důvěryhodné přizpůsobení je spustit později, koncový uživatel vyzván znovu.

 Správci mohou zakázat [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] důvěryhodný dotaz nebo vyžadovat, že dojde k řádku pouze pro řešení, které jsou podepsané certifikátem Authenticode. Další informace o tom, jak změnit tato nastavení pro tento počítač, LocalIntranet, Internet, TrustedSites a UntrustedSites zóny najdete v tématu [jak: Konfigurace chování výzvy důvěryhodnosti ClickOnce](../deployment/how-to-configure-the-clickonce-trust-prompt-behavior.md).

## <a name="see-also"></a>Viz také:

- [Zabezpečení řešení pro systém Office](../vsto/securing-office-solutions.md)
- [Zajistit jeho důvěryhodnost do dokumentů](../vsto/granting-trust-to-documents.md)
- [Řešení potíží se zabezpečením řešení pro systém Office](../vsto/troubleshooting-office-solution-security.md)
- [Specifické aspekty zabezpečení pro řešení pro systém Office](../vsto/specific-security-considerations-for-office-solutions.md)