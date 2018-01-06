---
title: "VBA a řešení pro systém Office v sadě Visual Studio porovnání | Microsoft Docs"
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
- VBA code, managed code extensions
- managed code extensions [Office development in Visual Studio], VBA compared to
ms.assetid: 31756c2f-8829-4011-ad77-134cb3728344
caps.latest.revision: "29"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 71934d28e7d0c93997cb58d0fdfae5153178047f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="vba-and-office-solutions-in-visual-studio-compared"></a>Srovnání řešení VBA a řešení pro systém Office v sadě Visual Studio
  Microsoft Visual Basic for Applications (VBA) používá nespravovaného kódu, který je úzce integrovaná s aplikací Office. Projekty aplikace Microsoft Office, které jsou vytvořené pomocí sady Visual Studio umožňují využít výhod rozhraní .NET Framework a nástrojů Visual Studio návrhu.  
  
 Informace o typech řešení pro systém Office, můžete vytvořit pomocí sady Visual Studio najdete v tématu [přehled vývoje řešení pro systém Office &#40; VSTO &#41; ](../vsto/office-solutions-development-overview-vsto.md).  
  
## <a name="comparison"></a>Srovnání  
 Následující tabulka uvádí základní srovnání řešení VBA a řešení pro systém Office v sadě Visual Studio.  
  
|Řešení VBA|Řešení Office v sadě Visual Studio|  
|-------------------|---------------------------------------|  
|Kód používá, která je připojena k a zachovat pomocí určitého dokumentu.|Používá kód, který se ukládají odděleně od dokumentu (pro přizpůsobení na úrovni dokumentu), nebo v sestavení zavedená v aplikaci (u doplňků VSTO VSTO).|  
|Funguje s rozhraní API VBA a Office – objektové modely.|Poskytuje přístup k i Office – objektové modely a [!INCLUDE[dnprdnshort](../sharepoint/includes/dnprdnshort-md.md)] rozhraní API.|  
|Určená pro záznam makra a zjednodušená vývojáře prostředí.|Určená pro zabezpečení, jednodušší kód údržby a možnost používat úplnou integrované vývojové prostředí (IDE) sady Visual Studio.|  
|Funguje dobře pro řešení, která těžit z velmi úzkou integraci s aplikací Office.|Funguje dobře pro řešení, která těžit z úplné prostředků sady Visual Studio a [!INCLUDE[dnprdnshort](../sharepoint/includes/dnprdnshort-md.md)].|  
|Má omezení pro podnik, zejména v oblasti zabezpečení a nasazení.|Určený k použití v podnikové síti.|  
  
 Některé věci zůstávají stále usnadňují rychle pomocí VBA pro vytváření. Konkrétně můžete pokračovat v používání VBA pro:  
  
-   List pro vlastní funkce.  
  
-   Makro záznam.  
  
## <a name="combining-vba-solutions-and-office-solutions-created-by-using-visual-studio"></a>Kombinování řešení VBA a řešení pro systém Office vytvořené pomocí sady Visual Studio  
 VBA kód můžete volat z Office řešení vytvořená pomocí sady Visual Studio a můžete také volání kódu v řešeních pro systém Office vytvořené pomocí sady Visual Studio z jazyka VBA. Konkrétní postup se liší v závislosti na tom, jestli je vaše řešení Office doplňku VSTO nebo přizpůsobení na úrovni dokumentu. Další informace najdete v tématu [volání kódu v doplňcích VSTO z jiných řešení pro systém Office](../vsto/calling-code-in-vsto-add-ins-from-other-office-solutions.md) a [kombinování VBA pro vytváření a úpravy na úrovni dokumentů](../vsto/combining-vba-and-document-level-customizations.md).  
  
## <a name="see-also"></a>Viz také  
 [Přehled vývoje řešení pro systém Office &#40; VSTO &#41;](../vsto/office-solutions-development-overview-vsto.md)   
 [Volání kódu v doplňcích VSTO z jiných řešení pro systém Office](../vsto/calling-code-in-vsto-add-ins-from-other-office-solutions.md)   
 [Kombinování VBA pro vytváření a úpravy na úrovni dokumentů](../vsto/combining-vba-and-document-level-customizations.md)   
 [Architektura přizpůsobení na úrovni dokumentu](../vsto/architecture-of-document-level-customizations.md)   
 [Architektura doplňků VSTO](../vsto/architecture-of-vsto-add-ins.md)   
 [Zabezpečení řešení pro systém Office](../vsto/securing-office-solutions.md)   
 [Začínáme &#40; vývoj pro Office v sadě Visual Studio &#41;](../vsto/getting-started-office-development-in-visual-studio.md)  
  
  