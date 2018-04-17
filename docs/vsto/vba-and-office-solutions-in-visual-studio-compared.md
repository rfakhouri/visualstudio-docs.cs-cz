---
title: VBA a řešení pro systém Office v sadě Visual Studio porovnání | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- VBA code, managed code extensions
- managed code extensions [Office development in Visual Studio], VBA compared to
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: a5a92727f08729fc7f8a871d0528c9e652d92f8a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="vba-and-office-solutions-in-visual-studio-compared"></a>Srovnání řešení VBA a řešení pro systém Office v sadě Visual Studio
  Microsoft Visual Basic for Applications (VBA) používá nespravovaného kódu, který je úzce integrovaná s aplikací Office. Projekty aplikace Microsoft Office, které jsou vytvořené pomocí sady Visual Studio umožňují využít výhod rozhraní .NET Framework a nástrojů Visual Studio návrhu.  
  
 Informace o typech řešení pro systém Office, můžete vytvořit pomocí sady Visual Studio najdete v tématu [přehled vývoje řešení pro systém Office &#40;VSTO&#41;](../vsto/office-solutions-development-overview-vsto.md).  
  
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
 [Přehled vývoje řešení pro systém Office &#40;VSTO&#41;](../vsto/office-solutions-development-overview-vsto.md)   
 [Volání kódu v doplňcích VSTO z jiných řešení pro systém Office](../vsto/calling-code-in-vsto-add-ins-from-other-office-solutions.md)   
 [Kombinování VBA pro vytváření a úpravy na úrovni dokumentů](../vsto/combining-vba-and-document-level-customizations.md)   
 [Architektura přizpůsobení na úrovni dokumentu](../vsto/architecture-of-document-level-customizations.md)   
 [Architektura doplňků VSTO](../vsto/architecture-of-vsto-add-ins.md)   
 [Zabezpečení řešení pro systém Office](../vsto/securing-office-solutions.md)   
 [Začínáme &#40;vývoj pro Office v sadě Visual Studio&#41;](../vsto/getting-started-office-development-in-visual-studio.md)  
  
  