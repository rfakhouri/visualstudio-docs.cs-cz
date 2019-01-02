---
title: Ochrana dokumentů Office heslem
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- permissions [Office development in Visual Studio]
- workbooks [Office development in Visual Studio], restricted permissions
- passwords [Office development in Visual Studio], document protections
- documents [Office development in Visual Studio], restricted permissions
- Office documents [Office development in Visual Studio, restricted permissions
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 4603a6f5722279ccdaf057d30d3bc6e911c4c47e
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53856998"
---
# <a name="password-protection-on-office-documents"></a>Ochrana dokumentů Office heslem
  Je možné nastavit heslo na dokumentů Microsoft Office Word a sešitů aplikace Microsoft Office Excel, aby jejich nelze otevřít někdo, kdo není znát heslo. Tato možnost se nazývá **heslo při otevření**.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 Můžete vytvořit projekty na úrovni dokumentu pomocí stávající dokumenty a sešity, které mají **heslo při otevření** povolena. Chování v sadě Visual Studio se liší pro dokumenty Wordu a Excelu, které mají **heslo při otevření** povolena.  
  
 Informace o povolení **heslo při otevření**, naleznete v tématu nápovědy v aplikaci Word nebo Excel.  
  
## <a name="behavior-of-excel-and-word"></a>Chování Excelu a Wordu  
 Při každém otevření sešitu aplikace Excel v sadě Visual Studio, který má **heslo při otevření** povoleno, aplikace Excel vás vyzve k zadání hesla. Při sestavování řešení se výzva k zadání hesla znovu, protože dokument je otevřen během sestavování.  
  
 Při prvním otevření dokumentu aplikace Word v sadě Visual Studio, který má **heslo při otevření** povolena, Word vás vyzve k zadání hesla. Po úspěšném zadání hesla, **heslo při otevření** se odebere z dokumentu a otevření dokumentu se už nevyžadují heslo. Pokud chcete dokument ve vašem řešení vyžadovat heslo, aby mohli ji můžete otevřít, je nutné povolit **heslo při otevření** po poslední sestavení a před nasazením řešení.  
  
## <a name="see-also"></a>Viz také:  
 [Ochrana dokumentů v řešeních na úrovni dokumentu](../vsto/document-protection-in-document-level-solutions.md)   
 [Přehled rozšíření spravovaného kódu a správy přístupových práv](../vsto/information-rights-management-and-managed-code-extensions-overview.md)   
 [Postupy: Povolit kód ke spuštění pozadí dokumentů s omezenými oprávněními](../vsto/how-to-permit-code-to-run-behind-documents-with-restricted-permissions.md)   
 [Návrh a vytvoření řešení pro systém Office](../vsto/designing-and-creating-office-solutions.md)  
