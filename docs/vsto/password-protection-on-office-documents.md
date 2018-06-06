---
title: Ochrana heslem v dokumentech Office | Microsoft Docs
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
- workbooks [Office development in Visual Studio], restricted permissions
- passwords [Office development in Visual Studio], document protections
- documents [Office development in Visual Studio], restricted permissions
- Office documents [Office development in Visual Studio, restricted permissions
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: a278677b40f8da703c7f3287851c2f82fb95a21c
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/01/2018
ms.locfileid: "34572709"
---
# <a name="password-protection-on-office-documents"></a>Ochrana heslem v dokumentech Office
  Je možné nastavit heslo na dokumenty aplikace Microsoft Office Word a sešitů aplikace Microsoft Office Excel tak, aby se nedá otevřít někdo, kdo není znát heslo. Tato možnost se nazývá **heslo při otevření**.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 Můžete vytvořit pomocí existující dokumenty a sešity, které mají projekty na úrovni dokumentu **heslo při otevření** povolena. Chování v sadě Visual Studio se liší pro dokumenty aplikace Word a Excel, které mají **heslo při otevření** povolena.  
  
 Informace o povolení **heslo při otevření**, najdete v nápovědě k aplikaci Word či Excel.  
  
## <a name="behavior-of-excel-and-word"></a>Chování aplikace Excel a Word  
 Při každém otevření sešitu aplikace Excel v sadě Visual Studio, který má **heslo při otevření** povoleno, aplikace Excel zobrazí výzvu k zadání hesla. Při sestavování řešení pro vás vyzve k zadání hesla znovu, protože otevření dokumentu během vytváření sestavení.  
  
 Při prvním otevření dokument aplikace Word v sadě Visual Studio, který má **heslo při otevření** povoleno, Word vás vyzve k zadání hesla. Po úspěšném zadání hesla, **heslo při otevření** se odebere z dokumentu a otevření dokumentu se už nevyžadují heslo. Pokud chcete dokument ve vašem řešení se vyžaduje heslo dříve, než se dá otevřít, musíte povolit **heslo při otevření** po posledním buildu a před nasazením řešení.  
  
## <a name="see-also"></a>Viz také:  
 [Ochrana dokumentů v řešeních na úrovni dokumentu](../vsto/document-protection-in-document-level-solutions.md)   
 [Přehled rozšíření spravovaného kódu a Správa přístupových práv](../vsto/information-rights-management-and-managed-code-extensions-overview.md)   
 [Postupy: povolení kód pro spuštění pozadí dokumentů s omezenými oprávněními](../vsto/how-to-permit-code-to-run-behind-documents-with-restricted-permissions.md)   
 [Návrh a vytvoření řešení pro systém Office](../vsto/designing-and-creating-office-solutions.md)  
  
  