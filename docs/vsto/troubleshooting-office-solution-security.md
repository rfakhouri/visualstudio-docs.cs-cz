---
title: "Řešení potíží se zabezpečením řešení Office | Microsoft Docs"
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
helpviewer_keywords: security [Office development in Visual Studio], troubleshooting
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 2ab3571da02fa56cd905369ee44e372aedea4e36
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="troubleshooting-office-solution-security"></a>Řešení potíží se zabezpečením řešení pro systém Office
  Toto téma obsahuje tipy pro řešení běžných problémů, kterými se můžete setkat při práci s zabezpečení řešení pro systém Office.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
## <a name="trusted-solutions-cannot-be-installed-from-restricted-sites"></a>Důvěryhodné řešení nelze nainstalovat z lokalit s omezeným přístupem  
 Uživatelé nemůžou instalovat z umístění webové řešení, pokud webová stránka je uveden v zóně Internet Explorer lokalit s omezeným přístupem. To platí i v případě, že toto řešení je podepsaná důvěryhodným certifikátem.  
  
 Adresa URL manifest nasazení lze rozdělit do jedné z pěti zón:  
  
-   Počítač  
  
-   Internet  
  
-   Místní intranet  
  
-   Důvěryhodných serverů  
  
-   Servery s omezeným přístupem  
  
 Pokud byl přiřazen umístění manifestu nasazení pro zónu lokalit s omezeným přístupem, [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] nenainstaluje řešení. Pokud umístění je známý a může být důvěryhodný, uživatel může odebrat umístění z servery s omezeným přístupem a nainstalujte řešení. Informace o tom, jak Správa zón najdete v tématu [konfigurace ClickOnce důvěryhodných vydavatelů](http://go.microsoft.com/fwlink/?LinkId=94774).  
  
## <a name="solutions-cannot-be-installed-from-network-file-shares-or-web-locations-when-internet-explorer-enhanced-security-configuration-or-internet-explorer-7-is-installed"></a>Řešení nelze nainstalovat ze síťové sdílené složky nebo webových umístění, pokud Rozšířená konfigurace zabezpečení aplikace Internet Explorer nebo nainstalovaný Internet Explorer 7  
 Internet Explorer rozšířené zabezpečení konfigurace (IEESC) v systému Windows Server 2003 a vyšší a prohlížeče Internet Explorer 7 a vyšší, výrazně omezuje schopnost uživatelů k Internetu. Pokud se uživatelé k instalaci řešení pro systém Office ze souboru sdílenou složku nebo webový umístění v síti, může získají se následující chybová zpráva: "vlastní funkce v této aplikaci nebude fungovat, protože certifikát použít k podepsání manifestu nasazení pro *Název řešení SolutionName* není důvěryhodný. Požádejte správce o další pomoc."  
  
 S IEESC a prohlížeče Internet Explorer 7 a vyšší Pokud adresa URL manifest nasazení je zařazený do kategorie v zóně Internet, manifest musí mít certifikát od důvěryhodného vydavatele nebo řešení nelze nainstalovat. Bez IEESC je výchozí chování pro koncové uživatele vyzvat k rozhodnutí o vztahu důvěryhodnosti.  
  
 Ke správě účinku IEESC a Internet Explorer 7 a vyšší, identifikovat weby a universal naming convention (UNC) cesty, která důvěřujete a přidat je do jedné ze zón zabezpečení důvěryhodné (místní intranet nebo Důvěryhodné servery). Informace o tom, jak Správa zón najdete v tématu [konfigurace ClickOnce důvěryhodných vydavatelů](http://go.microsoft.com/fwlink/?LinkId=94774).  
  
## <a name="see-also"></a>Viz také  
 [Zabezpečení řešení pro systém Office](../vsto/securing-office-solutions.md)  
  
  