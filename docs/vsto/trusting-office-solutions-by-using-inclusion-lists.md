---
title: Vztah důvěryhodnosti řešení pro systém Office s použitím seznamů povolených položek
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- permissions [Office development in Visual Studio]
- inclusion lists [Office development in Visual Studio], about inclusion lists
- security [Office development in Visual Studio], inclusion lists
- inclusion lists [Office development in Visual Studio]
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 2b0e3df3562fe9a7bcbf2ca9cdc899b9303eb19a
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54868608"
---
# <a name="trust-office-solutions-by-using-inclusion-lists"></a>Vztah důvěryhodnosti řešení pro systém Office s použitím seznamů povolených položek
  Seznamy povolených položek povolit uživatelům, aby měli vztah důvěryhodnosti pro řešení pro Office, které jsou podepsané certifikátem, který identifikuje vydavatele. Seznamy povolených položek jsou specifické pro uživatele a mohou být použity pro přizpůsobení na úrovni dokumentu a doplňky VSTO.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 Když uživatel spustí řešení pro Office, který nebyl udělen vztahu důvěryhodnosti pro tohoto uživatele, řešení pro Microsoft Office mu vyzve k zadání rozhodnutí o zabezpečení s [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] výzvu vztahu důvěryhodnosti. Pokud se uživatel rozhodne důvěřovat řešení, při příštím spuštění vlastního nastavení a uživatel vyzván  
  
## <a name="inclusion-list-and-windows-installer"></a>Seznam povolených položek a instalační služby systému Windows  
 Instalace řešení pro systém Office do *Program Files* adresáře pomocí Instalační služby systému Windows vyžaduje oprávnění správce. Pro řešení pro systém Office v *Program Files* adresáře, protože řešení pro systém Office již bylo uděleno oprávnění FullTrust Visual Studio Tools for Office runtime už zkontroluje seznam povolených položek.  
  
## <a name="clickonce-trust-prompt"></a>Výzvy důvěryhodnosti ClickOnce  
 S použitím [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] implementace pro řešení Office, správci můžete nakonfigurovat úroveň důvěryhodnosti výzvy chcete povolit dotazování, zakažte dotazování nebo vyžadují důvěryhodný certifikát. Tato konfigurace se provádí pomocí klíče registru, který určuje přístup do seznamu povolených položek.  
  
 Pokud dotazování je zakázaná, lze nainstalovat pouze řešení, které mají důvěryhodným a známým certifikátu. Pokud úroveň vyzývá k tomu je nastavena na Authenticode vyžaduje, řešení musí být podepsané certifikátem ze známé autority, ale nevyžaduje certifikát, který je zřetězen k důvěryhodné kořenové autoritě (důvěryhodný certifikát). Pokud je povoleno dotazování, řešení by mohla podepsaný certifikátem s identitou neznámý. V tomto scénáři rozhodnutí důvěryhodnosti je odloženo pro koncového uživatele a dočasné certifikátu by dostatečná k instalaci řešení.  
  
 Další informace najdete v tématu [jak: Konfigurace zabezpečení se seznamem povolených položek](../vsto/how-to-configure-inclusion-list-security.md) a tabulka 2 s názvem dotazování úroveň registru klíč hodnota spuštění efekty, v [konfigurace ClickOnce důvěryhodného vydavatele](http://go.microsoft.com/fwlink/?LinkId=94774).  
  
## <a name="structure-of-the-inclusion-list"></a>Struktura seznamu povolených položek  
 Položka seznamu platný zahrnutí má dvě části: cesta k manifestu nasazení a veřejný klíč používaný k podepisování řešení. Po přidání řešení do seznamu povolených položek se považuje za důvěryhodný. Při spuštění řešení pro Office, aplikace Office porovnává veřejný klíč v seznamu povolených položek s podpisový klíč v manifestu nasazení můžete ověřit, že na řešení, které aktuálně běží stejný jako původní verze důvěryhodné.  
  
## <a name="see-also"></a>Viz také:  
 [Zajistit jeho důvěryhodnost do řešení pro systém Office](../vsto/granting-trust-to-office-solutions.md)   
 [Zabezpečení řešení pro systém Office](../vsto/securing-office-solutions.md)  
