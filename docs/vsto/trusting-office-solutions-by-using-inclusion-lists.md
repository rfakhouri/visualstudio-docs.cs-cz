---
title: Vztah důvěryhodnosti řešení Office s použitím seznamech povolených položek
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- permissions [Office development in Visual Studio]
- inclusion lists [Office development in Visual Studio], about inclusion lists
- security [Office development in Visual Studio], inclusion lists
- inclusion lists [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 9e2fea115b941af4b119b59dade16114cab3383d
ms.sourcegitcommit: ce154aee5b403d5c1c41da42302b896ad3cf8d82
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/07/2018
ms.locfileid: "34844222"
---
# <a name="trust-office-solutions-by-using-inclusion-lists"></a>Vztah důvěryhodnosti řešení Office s použitím seznamech povolených položek
  Seznamy povolených povolit uživatelům udělit vztah důvěryhodnosti řešení pro systém Office, které jsou podepsané certifikátem, který identifikuje vydavatele. Zahrnutí seznamy jsou specifické pro uživatele a mohou být použity pro přizpůsobení na úrovni dokumentu a doplňků VSTO.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 Když uživatel spustí řešení Office, který nebyl udělen vztahu důvěryhodnosti pro tohoto uživatele, řešení Microsoft Office vyzve k rozhodnutí zabezpečení se mu [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] výzvu vztahu důvěryhodnosti. Pokud se uživatel rozhodne důvěřovat řešení, spustí přizpůsobení a uživatel nebude vyzván k dalším.  
  
## <a name="inclusion-list-and-windows-installer"></a>Seznam povolených položek a instalační služba systému Windows  
 Instalace do řešení pro systém Office *Program Files* adresáře pomocí Instalační služby systému Windows vyžaduje oprávnění správce. Pro řešení Office *Program Files* adresář, protože řešení pro systém Office již bylo uděleno oprávnění FullTrust sady Visual Studio Tools for Office runtime už zkontroluje seznam povolených položek.  
  
## <a name="clickonce-trust-prompt"></a>Vztahu důvěryhodnosti ClickOnce  
 Pomocí [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] implementace pro řešení Office, správci můžete nakonfigurovat úroveň důvěryhodnosti výzva povolení výzvy, zakažte výzvy nebo vyžadují důvěryhodný certifikát. Tato konfigurace se provádí pomocí klíče registru, který určuje přístup do seznamu povolených.  
  
 Pokud je zakázána výzvy, lze nainstalovat pouze řešení, které mají certifikát důvěryhodným a známým. Pokud nabízení úroveň je nastavená na požadované Authenticode, řešení musí být podepsané certifikátem od známých autority, ale nevyžaduje certifikát který je zřetězen do důvěryhodného kořenového úřadu (důvěryhodný certifikát). Pokud je povolen výzvy, řešení by mohly být podepsány certifikátem identitou neznámé. V tomto scénáři je odložení rozhodnutí o vztahu důvěryhodnosti pro koncového uživatele a dočasné certifikátu by dostatečná k instalaci řešení.  
  
 Další informace najdete v tématu [postupy: konfigurace zabezpečení se seznamem povolených](../vsto/how-to-configure-inclusion-list-security.md) a tabulka 2, s názvem výzvy úroveň registru klíč hodnota spusťte důsledky, v [konfigurace ClickOnce důvěryhodného vydavatele](http://go.microsoft.com/fwlink/?LinkId=94774).  
  
## <a name="structure-of-the-inclusion-list"></a>Struktura seznam povolených položek  
 Položka seznamu platný zahrnutí má dvě části: cesta k manifestu nasazení a veřejný klíč používaný k podepisování řešení. Po řešení se přidá do seznamu povolených, bude považován za důvěryhodný. Při spuštění řešení Office, aplikace Office porovná veřejný klíč v seznamu povolených s podpisový klíč v manifestu nasazení, aby ověřte, zda řešení, které běží v současné době je stejný jako původní verze důvěryhodné.  
  
## <a name="see-also"></a>Viz také:  
 [Vztah důvěryhodnosti grant řešení pro systém Office](../vsto/granting-trust-to-office-solutions.md)   
 [Zabezpečení řešení pro systém Office](../vsto/securing-office-solutions.md)  
  
  