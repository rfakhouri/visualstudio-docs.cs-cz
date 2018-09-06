---
title: Řešení potíží se zabezpečením řešení pro systém Office
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- security [Office development in Visual Studio], troubleshooting
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 347cd6cfa1e773d3900e7294d691f061d91a762d
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/06/2018
ms.locfileid: "35676441"
---
# <a name="troubleshoot-office-solution-security"></a>Řešení potíží se zabezpečením řešení pro systém Office
  Toto téma obsahuje tipy pro řešení běžných problémů, které můžete narazit při práci s zabezpečení řešení pro Office.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
## <a name="trusted-solutions-cannot-be-installed-from-restricted-sites"></a>Řešení pro důvěryhodného nelze nainstalovat z lokalit s omezeným přístupem  
 Uživatelé nemůžou instalovat řešení z webového umístění, pokud je uvedená na webu v zóně Internet Exploreru lokalit s omezeným přístupem. To platí i v případě, že toto řešení je podepsaná důvěryhodným certifikátem.  
  
 Adresa URL v manifestu nasazení lze rozdělit do jedné z pěti zón:  
  
-   Tento počítač  
  
-   Internet  
  
-   Místní intranet  
  
-   Důvěryhodných serverů  
  
-   Servery s omezeným přístupem  
  
 Pokud byla přiřazena umístění manifestu nasazení pro zónu lokalit s omezeným přístupem [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] není možné nainstalovat řešení. Pokud se označuje umístění a může být důvěryhodný, uživatel můžete odebrat umístění z zónu lokalit s omezeným přístupem a nainstalovat řešení. Informace o tom, jak spravovat zóny najdete v tématu [konfigurace ClickOnce Důvěryhodní vydavatelé](http://go.microsoft.com/fwlink/?LinkId=94774).  
  
## <a name="solutions-cannot-be-installed-from-network-file-shares-or-web-locations-when-internet-explorer-enhanced-security-configuration-or-internet-explorer-7-is-installed"></a>Řešení nelze nainstalovat ze síťové sdílené složky nebo webové umístění při instalaci konfigurace rozšířeného zabezpečení aplikace Internet Explorer nebo Internet Explorer 7  
 Internet Explorer rozšířené zabezpečení konfigurace (IEESC) ve Windows serveru 2003 a vyšší a prohlížeče Internet Explorer 7 a vyšší, výrazně omezuje možnost uživatelů procházet Internet. Co uživatelé vyzkouší nainstalovat řešení pro systém Office ze souboru sdílené složky nebo webové umístění v síti, může se zobrazit následující chybová zpráva: "vlastní funkce v této aplikaci nebude fungovat, protože tento certifikát umožňuje podepsat manifest nasazení pro *SolutionName* není důvěryhodný. Požádejte správce o pomoc. "  
  
 S IEESC a Internet Explorer 7 a vyšší Pokud adresa URL v manifestu nasazení jsou rozdělené do kategorií v zóně Internet, manifest musí mít certifikát od důvěryhodné vydavatele nebo řešení nelze nainstalovat. Bez IEESC je výchozí chování výzvu k provedení rozhodnutí důvěryhodnosti.  
  
 Ke správě účinek IEESC a Internet Explorer 7 a vyšší, identifikovat webových stránek a universal naming convention (UNC) cesty, které důvěřujete a přidat je do jedné ze zón zabezpečení pro důvěryhodného (místní intranet nebo Důvěryhodné servery). Informace o tom, jak spravovat zóny najdete v tématu [konfigurace ClickOnce důvěryhodného vydavatele](http://go.microsoft.com/fwlink/?LinkId=94774).  
  
## <a name="see-also"></a>Viz také:  
 [Zabezpečení řešení pro systém Office](../vsto/securing-office-solutions.md)  
  
  