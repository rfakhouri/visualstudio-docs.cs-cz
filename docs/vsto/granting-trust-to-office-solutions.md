---
title: "Udělení důvěry pro řešení pro Office | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- security [Office development in Visual Studio], trust
- inclusion lists [Office development in Visual Studio], about inclusion lists
- trust [Office development in Visual Studio], 2007 Office system
- granting trust [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 41ecf50a7306025913f228500036d133918dd31b
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="granting-trust-to-office-solutions"></a>Udělení důvěry řešením pro systém Office
  Udělení vztah důvěryhodnosti řešení pro systém Office znamená, úprava zásady zabezpečení o každém cílovém počítači tak, aby důvěřoval sestavení řešení, manifest aplikace, manifest nasazení a dokumentu. Vztah důvěryhodnosti lze udělit řešení Office vy nebo koncový uživatel.  
  
 Úplný vztah důvěryhodnosti k řešení Office můžete udělit pomocí podepisování manifestů aplikace a nasazení.  
  
 Koncovým uživatelům můžete udělit vztah důvěryhodnosti řešení Office tak, že rozhodnutí o vztahu důvěryhodnosti [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] výzvu vztahu důvěryhodnosti.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
##  <a name="Signing"></a>Manifesty důvěřující řešení pomocí podepisování aplikace a nasazení  
 Všechny aplikace a nasazení manifesty pro Office řešení musí být podepsané certifikátem, který identifikuje vydavatele. Certifikáty poskytují základ pro rozhodování o vztahu důvěryhodnosti.  
  
 Dočasné certifikát je vytvořená a udělit vztah důvěryhodnosti v okamžiku sestavení tak, aby řešení spuštěno při ladění ho. Pokud publikujete řešení, který je podepsaný certifikátem dočasné, koncový uživatel se vyzve k rozhodnutí o vztahu důvěryhodnosti.  
  
 Pokud podepíšete řešení s certifikátem známé a důvěryhodné, řešení se automaticky nainstalují bez zobrazení výzvy koncového uživatele k provedení rozhodnutí vztah důvěryhodnosti. Další informace o tom, jak získat certifikát pro podepisování najdete v tématu [ClickOnce a kód Authenticode](/visualstudio/deployment/clickonce-and-authenticode). Po získání certifikátu, certifikát musí být explicitně důvěryhodný přidáním do seznamu důvěryhodných vydavatelů. Další informace najdete v tématu [postupy: Přidání důvěryhodného vydavatele ke klientskému počítači pro aplikace ClickOnce](/visualstudio/deployment/how-to-add-a-trusted-publisher-to-a-client-computer-for-clickonce-applications).  
  
 Pokud vývojář podepisuje řešení s certifikátem dočasné, může správce znovu podepsat pomocí generování manifestu a úpravy nástroj (mage.exe), který je jedním z nástrojů rozhraní Microsoft .NET Framework přizpůsobení s certifikátem známé a důvěryhodné. Další informace o podepisování řešení najdete v tématu [postupy: řešení pro systém Office přihlašování](../vsto/how-to-sign-office-solutions.md) a [postupy: přihlášení aplikace a manifesty nasazení](/visualstudio/ide/how-to-sign-application-and-deployment-manifests).  
  
##  <a name="TrustPrompt"></a>Důvěřující řešení pomocí vztahu důvěryhodnosti ClickOnce  
 [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]vyzve k zadání koncového uživatele, aby rozhodnutí o vztahu důvěryhodnosti, pokud nejsou žádné zásady celé organizace, která důvěřuje certifikátu na řešení. Pokud koncový uživatel uděluje vztah důvěryhodnosti k řešení, se vytvoří položku seznamu povolených, který obsahuje adresu URL a veřejný klíč slouží k uložení tohoto vztahu důvěryhodnosti rozhodnutí. Když důvěryhodné přizpůsobení se spustí později, koncový uživatel se znovu zobrazí výzva.  
  
 Správci mohou zakázat [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] důvěryhodný dotaz nebo vyžadovat, aby řádku vzniknout jen pro řešení, které jsou podepsané certifikátem Authenticode. Další informace o tom, jak změnit toto nastavení pro tento počítač, LocalIntranet, Internet, TrustedSites a UntrustedSites zóny najdete v tématu [postupy: Konfigurace výzva chování vztahu důvěryhodnosti ClickOnce](/visualstudio/deployment/how-to-configure-the-clickonce-trust-prompt-behavior).  
  
## <a name="see-also"></a>Viz také  
 [Zabezpečení řešení pro systém Office](../vsto/securing-office-solutions.md)   
 [Udělení důvěry dokumentům](../vsto/granting-trust-to-documents.md)   
 [Řešení potíží se zabezpečením řešení Office](../vsto/troubleshooting-office-solution-security.md)   
 [Specifické aspekty zabezpečení u řešení pro systém Office](../vsto/specific-security-considerations-for-office-solutions.md)  
  
  