---
title: "Řešení pro aplikaci Visio | Microsoft Docs"
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
- Office projects [Office development in Visual Studio], Visio
- solutions [Office development in Visual Studio], Visio
- Visio [Office development in Visual Studio]
- templates [Office development in Visual Studio], Visio
- projects [Office development in Visual Studio], Visio
- Office solutions [Office development in Visual Studio], Visio
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 558ddc7a9c0fee5305052143edaca2b88b097723
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="visio-solutions"></a>Řešení pro aplikaci Visio
  Visual Studio poskytuje šablony projektů, které můžete použít k vytvoření doplňků VSTO pro aplikaci Microsoft Office Visio. Doplňků VSTO můžete automatizovat Visio, rozšířit funkce aplikace Visio nebo přizpůsobení uživatelského rozhraní (UI) aplikace Visio.  
  
 Další informace o doplňků VSTO najdete v tématu [získávání VSTO spuštění programování doplňků](../vsto/getting-started-programming-vsto-add-ins.md) a [architektura VSTO doplňky](../vsto/architecture-of-vsto-add-ins.md). Pokud jste ještě programování s Microsoft Office, najdete v části [Začínáme & #40; vývoj pro Office v sadě Visual Studio & #41;](../vsto/getting-started-office-development-in-visual-studio.md).  
  
 **Platí pro:** informace v tomto tématu se vztahují na projekty doplňku VSTO pro Visio 2010. Další informace najdete v tématu [dostupné funkce podle aplikace Office a typu projektu](../vsto/features-available-by-office-application-and-project-type.md).  
  
> [!NOTE]  
>  Máte zájem o vývoji řešení, které rozšiřují Office prostředí napříč [více platforem](https://dev.office.com/add-in-availability)? Podívejte se na [Office Add in modelu](https://dev.office.com/docs/add-ins/overview/office-add-ins). Doplňky Office mají malé nároky ve srovnání s doplňků VSTO a řešení a můžete je vytvořit pomocí téměř jakoukoli webové programování technologie, jako je například HTML5, JavaScript, CSS3 a XML.  
  
## <a name="automating-visio-by-using-the-visio-object-model"></a>Automatizace aplikace Visio s použitím modelu objektů aplikace Visio  
 Visio – objektový model zpřístupní mnoho tříd, které můžete použít k automatizaci Visio pro vytvoření diagramy pro organizační diagramy, na vývojových diagramech, časové osy projektu, síťové diagramy, office mezery a další. Rozhraní API umožňuje psát kód k provádění běžných úloh:  
  
-   Vytvořit a umístit je v diagramech tvary a text.  
  
-   Spravovat tvar chování na základě obchodní logiky a vstup uživatele.  
  
-   Ovládací prvek diagram vizualizace například posouvání a přibližování.  
  
-   Přizpůsobení uživatelského rozhraní aplikace.  
  
-   Import externích dat do aplikace Visio a propojit obrazce grafické zobrazení na stránce.  
  
 Můžete zobrazit podrobné postupy a příklady pro použití v objektovém modelu aplikace Visio pro práci s dokumenty a obrazce v kódu [práce s dokumenty aplikace Visio](../vsto/working-with-visio-documents.md) a [práce s obrazci aplikace Visio](../vsto/working-with-visio-shapes.md).  
  
 Pro přístup k modelu objektů aplikace Visio z doplňku VSTO, použijte `Application` pole z `ThisAddIn` třídy ve vašem projektu. `Application` Pole vrátí objekt Microsoft.Office.Interop.Visio.Application, který představuje aktuální instanci aplikace Visio. Další informace najdete v tématu [programování doplňků VSTO](../vsto/programming-vsto-add-ins.md).  
  
 Při volání do modelu objektů aplikace Visio použijete typy, které jsou uvedeny v primární spolupracující sestavení (PIA) pro aplikaci Visio. PRIMÁRNÍ pracuje jako most mezi spravovaného kódu v doplňku VSTO a objektového modelu COM v aplikaci Visio. Všechny typy v aplikaci Visio PIA jsou definovány v oboru názvů Microsoft.Office.Interop.Visio. Další informace o primární spolupracující sestavení najdete v tématu [přehled vývoje řešení pro systém Office & #40; VSTO & #41; ](../vsto/office-solutions-development-overview-vsto.md) a [primární spolupracující sestavení Office](../vsto/office-primary-interop-assemblies.md).  
  
## <a name="visio-object-model-overview"></a>Přehled modelu objektů aplikace Visio  
 Přehled modelu objektů aplikace Visio v můžete najít [přehled modelu objektů aplikace Visio](../vsto/visio-object-model-overview.md), který obsahuje odkazy na odkaz modelu objektů aplikace Visio a sady SDK.  
  
## <a name="customizing-the-user-interface-of-visio"></a>Přizpůsobení uživatelského rozhraní aplikace Visio  
 Uživatelské rozhraní aplikace Visio obsahuje následující možnosti přizpůsobení.  
  
|Úloha|Další informace|  
|----------|--------------------------|  
|Přizpůsobení pásu karet.|[Přehled pásu karet](../vsto/ribbon-overview.md)|  
  
 Informace o přizpůsobení uživatelského rozhraní aplikace Visio najdete v tématu referenční dokumentaci VBA pro [Visio.UIObject](https://msdn.microsoft.com/library/office/ff765763.aspx) třídy.  
  
## <a name="see-also"></a>Viz také  
 [Začínáme programováním doplňků VSTO](../vsto/getting-started-programming-vsto-add-ins.md)   
 [Přehled vývoje řešení pro systém Office & #40; VSTO & #41;](../vsto/office-solutions-development-overview-vsto.md)   
 [Architektura doplňků VSTO](../vsto/architecture-of-vsto-add-ins.md)   
 [Postupy: vytváření projektů Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [Programování doplňků VSTO](../vsto/programming-vsto-add-ins.md)   
 [Psaní kódu v řešeních pro systém Office](../vsto/writing-code-in-office-solutions.md)   
 [Primární spolupracující sestavení sady Office](../vsto/office-primary-interop-assemblies.md)   
 [Přizpůsobení uživatelského rozhraní sady Office](../vsto/office-ui-customization.md)   
 [Přehled modelu objektů aplikace Visio](../vsto/visio-object-model-overview.md)   
 [Visio 2010 v vývoj pro Office](http://go.microsoft.com/fwlink/?LinkId=199017)  
  
  