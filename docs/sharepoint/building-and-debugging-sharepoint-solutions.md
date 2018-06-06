---
title: Sestavování a ladění řešení služby SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, building and debugging
- SharePoint development in Visual Studio, debugging
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 4d0bc3185b0684f96bf31cc127cd852448afe772
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/05/2018
ms.locfileid: "34765067"
---
# <a name="build-and-debug-sharepoint-solutions"></a>Vytváření a ladění řešení služby SharePoint
  Sestavování a ladění řešení služby SharePoint je obecně stejná jako sestavování a ladění jiné typy projektů v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. Témata v této části popisují rozdíly, které existují.  
  
## <a name="project-output-for-sharepoint-solutions"></a>Výstup projektu pro řešení služby SharePoint
 Sestavování řešení služby SharePoint vytvoří sestavení a balíčku řešení (*WSP*) souboru. Následující tabulka uvádí umístění těchto souborů během sestavení.  
  
|Vytvoření položky|Výstupní složky|  
|----------------|-------------------|  
|Sestavení, program databáze (*PDB*), a *WSP* soubory.|*{Název projektu} \bin\debug* nebo *\bin\release {ProjectName}*|  
|Soubory položky projektu služby SharePoint.|*{Název projektu} \pkg\debug* nebo *\pkg\release {ProjectName}*|  
|Sestavení zprostředkující souborů.|*{Název projektu} \obj\debug* nebo *\obj\release {ProjectName}*|  
|Zprostředkující soubory balíčku.|*{Název projektu} \pkgobj\debug* nebo *\pkgobj\release {ProjectName}*|  
  
## <a name="build-sharepoint-solutions"></a>Sestavení řešení služby SharePoint
 K sestavení řešení služby SharePoint, musí mít vývojovém počítači správnou verzi serveru SharePoint nainstalována. Jinak, vytváření řešení služby SharePoint je stejný jako vytváření jiné typy projektů v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. Další informace najdete v tématu [postupy: sestavení řešení služby SharePoint](../sharepoint/how-to-build-sharepoint-solutions.md).  
  
## <a name="debug-and-test-sharepoint-solutions"></a>Ladění a testování řešení služby SharePoint
 Před ladění, [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] kopie *WSP* balíček pro server služby SharePoint, aktivuje lokalitu a součásti pro celý Web a v některých případech spustí projektu. V ostatních případech budete muset ručně otevřete projekt. Další informace najdete v tématu [řešení potíží s řešení služby SharePoint](../sharepoint/troubleshooting-sharepoint-solutions.md) a [ladění řešení služby SharePoint](../sharepoint/debugging-sharepoint-solutions.md).  
  
## <a name="debug-and-verify-sharepoint-solutions-by-using-alm-features"></a>Ladění a ověřit řešení služby SharePoint pomocí funkce ALM
 Visual Studio ALM funkce jako je testování částí a IntelliTrace umožňují další přesně přesně stanovit problémy ve vašem řešení služby SharePoint. Profilace umožňuje vyhledat a identifikovat výkonu problémových oblastí v řešení služby SharePoint. Další informace najdete v tématu [ověření a ladění kódu pro SharePoint](../sharepoint/verifying-and-debugging-sharepoint-code.md) a [profilace výkonu aplikací služby SharePoint](../sharepoint/profiling-the-performance-of-sharepoint-applications.md).  
  
## <a name="security-during-the-build-process"></a>Zabezpečení během procesu sestavení
 Balíček nebo nasazení řešení služby SharePoint, [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] musí mít oprávnění ke kopírování souborů do serveru SharePoint. Je nutné spustit [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] jako zvýšenými proces a uživatel musí být účet správce kolekce webů na serveru SharePoint. Kromě toho musíte zadat, zda je váš projekt řešení v izolovaném prostoru nebo řešení farmy. Další informace najdete v tématu [rozdíly mezi řešeními v izolovaném prostoru a řešení ve farmách](../sharepoint/differences-between-sandboxed-and-farm-solutions.md).  
  
## <a name="using-the-clean-command"></a>Pomocí příkazu vyčištění  
 Při řešení služby SharePoint je nainstalován na serveru služby SharePoint pro ladění, **Vyčistit** příkaz neodinstaluje řešení. Místo toho je nutné deaktivovat funkce prostřednictvím konfigurace služby SharePoint.  
  
## <a name="see-also"></a>Viz také:
 [Vývoj řešení služby SharePoint](../sharepoint/developing-sharepoint-solutions.md)   
 [Procházení připojení služby SharePoint pomocí Průzkumníka serveru](../sharepoint/browsing-sharepoint-connections-using-server-explorer.md)   
 [Balení a nasazení řešení služby SharePoint](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)  
  
 