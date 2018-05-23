---
title: Udělení důvěryhodnosti do dokumentů
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
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: f95887d5d540fd1acd95b8af1275c4b4054c8764
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/22/2018
---
# <a name="grant-trust-to-documents"></a>Udělení důvěryhodnosti do dokumentů
  Projekt na úrovni dokumentu a má stejné požadavky na zabezpečení jako projekty na úrovni aplikace: podepisování manifestů s certifikátem nebo kliknutím na výzvu vztahu důvěryhodnosti. Kromě toho dokumentu nebo sešitu musí být umístěny v adresáři, který je určený jako důvěryhodné umístění.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
## <a name="trusted-locations"></a>Důvěryhodná umístění  
 Aplikace v [!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)] a Office 2010 centrech vztahu důvěryhodnosti, kde uživatelé můžou konfigurovat nastavení zabezpečení a ochrana osobních údajů, jako je například důvěryhodného umístění. Pro řešení Office místním počítači považuje za důvěryhodného umístění. Z důvodu vyšší riziko, existují však určité adresáře, které někdy nelze důvěřovat, jako je například dočasných složek pro systém, pro každého uživatele a pro Internet Explorer.  
  
 Další informace o Centru zabezpečení najdete v tématu [zásady a nastavení v Office 2010 a zabezpečení](http://go.microsoft.com/fwlink/?LinkId=89202). Další informace o tom, jak vytvářet, spravovat, odebrat a konfigurovat důvěryhodné složky najdete v tématu [nakonfigurovat důvěryhodné umístění a nastavení důvěryhodné vydavatele v systému Office 2007](http://go.microsoft.com/fwlink/?LinkId=89203) a [Create, odebrat nebo změnit důvěryhodné umístění souborů](https://support.office.com/en-au/article/Create-remove-or-change-a-trusted-location-for-your-files-f5151879-25ea-4998-80a5-4208b3540a62).  
  
## <a name="security-considerations-for-office-solutions"></a>Důležité informace o zabezpečení pro řešení Office  
 Existuje několik aspekty zabezpečení při zvažování složky, které chcete přidat do důvěryhodného umístění:  
  
-   Místní složky jsou považovány za informace zabezpečení a jsou implicitně důvěryhodné. Vzdálených umístěních, jako jsou sdílené složky musí být určeny jako důvěryhodné umístění.  
  
-   Když přidáte do důvěryhodného umístění adresáře, tato akce udělí úplný vztah důvěryhodnosti, nejen pro řešení pro Office, ale také kvůli VBA a ActiveX kódu. Z tohoto důvodu kořenový adresář a *dokumenty* složky by neměl být určen jako důvěryhodné.  
  
-   I když je důvěryhodný samotného dokumentu pomocí důvěryhodného umístění, jsou potřeba další oprávnění tak, aby důvěřoval přizpůsobení. Úplný vztah důvěryhodnosti k přizpůsobení můžete udělit pomocí podepisování manifestů s certifikátem, kliknutím na výzvu vztahu důvěryhodnosti nebo instalace řešení Office *Program Files* adresáře.  
  
-   Můžete uložit dokumentu nebo sešitu řešení úrovni dokumentu ve stejném adresáři jako sestavení nebo v jiném adresáři. Například dokument může nacházet na serveru služby SharePoint a sestavení může být umístěna na síťové sdílené složky. Další informace najdete v tématu [postupy: publikování řešení úrovni dokumentu Office SharePoint Server s použitím technologie ClickOnce](http://msdn.microsoft.com/en-us/2408e809-fb78-42a1-9152-00afa1522e58).  
  
## <a name="see-also"></a>Viz také  
 [Vztah důvěryhodnosti grant řešení pro systém Office](../vsto/granting-trust-to-office-solutions.md)   
 [Odstraňování problémů se zabezpečením řešení Office](../vsto/troubleshooting-office-solution-security.md)   
 [Zabezpečení řešení pro systém Office](../vsto/securing-office-solutions.md)  
  
  