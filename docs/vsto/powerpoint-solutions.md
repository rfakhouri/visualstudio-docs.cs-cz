---
title: "Řešení pro aplikaci PowerPoint | Microsoft Docs"
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
- Office solutions [Office development in Visual Studio], PowerPoint
- templates [Office development in Visual Studio], PowerPoint
- solutions [Office development in Visual Studio], PowerPoint
- projects [Office development in Visual Studio], PowerPoint
- PowerPoint [Office development in Visual Studio]
- Office projects [Office development in Visual Studio], PowerPoint
ms.assetid: 02ebad64-9fd3-495f-ab27-4f6206b3d6d2
caps.latest.revision: "46"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: dd03b3e14599535c99f8a8ddd17314ce7f0cc719
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="powerpoint-solutions"></a>Řešení pro aplikaci PowerPoint
  Visual Studio poskytuje šablony projektů, které můžete použít k vytvoření doplňků VSTO pro Microsoft Office PowerPoint. Doplňků VSTO můžete automatizovat PowerPointu, rozšířit funkce aplikace nebo si přizpůsobit PowerPoint uživatelské rozhraní (UI).  
  
 Další informace o doplňků VSTO najdete v tématu [získávání VSTO spuštění programování doplňků](../vsto/getting-started-programming-vsto-add-ins.md) a [architektura VSTO doplňky](../vsto/architecture-of-vsto-add-ins.md). Pokud jste ještě programování s Microsoft Office, najdete v části [Začínáme &#40; vývoj pro Office v sadě Visual Studio &#41;](../vsto/getting-started-office-development-in-visual-studio.md).  
  
 [!INCLUDE[appliesto_pptallapp](../vsto/includes/appliesto-pptallapp-md.md)]  
  
> [!NOTE]  
>  Máte zájem o vývoji řešení, které rozšiřují Office prostředí napříč [více platforem](https://dev.office.com/add-in-availability)? Podívejte se na [Office Add in modelu](https://dev.office.com/docs/add-ins/overview/office-add-ins). Doplňky Office mají malé nároky ve srovnání s doplňků VSTO a řešení a můžete je vytvořit pomocí téměř jakoukoli webové programování technologie, jako je například HTML5, JavaScript, CSS3 a XML.  
  
 ![odkaz na video](../vsto/media/playvideo.gif "odkaz na video") související Videoukázka, najdete v části [jak I: vytvořit-in pro aplikaci Microsoft PowerPoint?](http://go.microsoft.com/fwlink/?LinkId=132767).  
  
## <a name="automating-powerpoint-by-using-the-powerpoint-object-model"></a>Automatizace PowerPoint pomocí objektového modelu PowerPoint  
 Objektový model PowerPoint zpřístupní mnoho typů, které můžete použít k automatizaci PowerPoint. Tyto typy umožňují napsat kód k provádění běžných úloh:  
  
-   Prostřednictvím kódu programu vytvořte a naformátujte prezentací.  
  
-   Přidat nebo odebrat snímky z prezentací.  
  
-   Přidat nebo změnit tvary na snímku.  
  
 Pro přístup k modelu objektu PowerPoint z doplňku VSTO, použijte `Application` pole z `ThisAddIn` třídy ve vašem projektu. `Application` Pole vrátí <xref:Microsoft.Office.Interop.PowerPoint.Application> objekt, který představuje aktuální instanci aplikace PowerPoint. Další informace najdete v tématu [programování doplňků VSTO](../vsto/programming-vsto-add-ins.md).  
  
 Při volání do modelu objektu PowerPoint použijete typy, které jsou uvedeny v primární spolupracující sestavení pro PowerPoint. Primární spolupracující sestavení pracuje jako most mezi spravovaného kódu v doplňku VSTO a objektového modelu COM v aplikaci PowerPoint. Všechny typy v sestavení primární spolupráce PowerPoint jsou definovány v <xref:Microsoft.Office.Interop.PowerPoint> oboru názvů. Další informace o primární spolupracující sestavení najdete v tématu [přehled vývoje řešení pro systém Office &#40; VSTO &#41; ](../vsto/office-solutions-development-overview-vsto.md) a [primární spolupracující sestavení Office](../vsto/office-primary-interop-assemblies.md).  
  
##  <a name="WordOMDocumentation"></a>Pomocí dokumentace PowerPoint objekt modelu  
 Úplné informace o objektu modelu PowerPoint najdete odkaz na aplikaci PowerPoint primární spolupracující sestavení (PIA) a reference VBA objektu modelu.  
  
### <a name="primary-interop-assembly-reference"></a>Odkaz sestavení primární spolupráce  
 PowerPoint PIA referenční dokumentaci k nástroji popisuje typy v sestavení primární spolupráce pro PowerPoint. Tato dokumentace je k dispozici z následujícího umístění: [odkaz sestavení PowerPoint 2010 primární zprostředkovatel komunikace s objekty](http://go.microsoft.com/fwlink/?LinkId=189588).  
  
 Další informace o návrhu PowerPoint PIA, jako jsou rozdíly mezi třídy a rozhraní v primární a jak jsou implementované události v primární, najdete v části [přehled třídy a rozhraní v primární zprostředkovatel komunikace s objekty sestavení sady Office ](http://go.microsoft.com/fwlink/?LinkId=199885).  
  
### <a name="vba-object-model-reference"></a>Odkaz na objekt modelu VBA  
 Reference objektu modelu VBA dokumenty PowerPoint objektový model, jako je zpřístupněné pro Visual Basic pro aplikace (VBA) kód. Další informace najdete v tématu [odkaz na objekt modelu PowerPoint 2010](http://go.microsoft.com/fwlink/?LinkId=199770)  
  
 Všechny objekty a členy ve model odkaz na VBA odpovídají typy a členy v primární spolupracující sestavení PowerPoint (PIA –). Například objekt prezentace v modelu odkaz na VBA odpovídá <xref:Microsoft.Office.Interop.PowerPoint.Presentation> typu v PowerPoint PIA. I když reference VBA objektu modelu poskytuje příklady kódu pro většinu vlastností, metod a událostí, pokud chcete používat v projektu doplňku VSTO v PowerPointu, který vytvoříte pomocí musí překládat VBA kód v této referenci na Visual Basic a Visual C# Visual Studio.  
  
## <a name="customizing-the-user-interface-of-powerpoint"></a>Přizpůsobení uživatelského rozhraní aplikace PowerPoint  
 PowerPoint uživatelského rozhraní můžete upravit následujícím způsobem.  
  
|Úloha|Další informace|  
|----------|--------------------------|  
|Vytvoření vlastního podokna úloh.|[Vlastní podokona úloh](../vsto/custom-task-panes.md)|  
|Přidáte vlastní karty na pásu karet.|[Přehled pásu karet](../vsto/ribbon-overview.md)|  
|Přidáte vlastní skupiny do předdefinované karty na pásu karet.|[Postupy: Přizpůsobení předdefinované karty](../vsto/how-to-customize-a-built-in-tab.md)|  
  
 Další informace o přizpůsobení uživatelského rozhraní PowerPoint a další aplikace Microsoft Office, najdete v části [přizpůsobení uživatelského rozhraní Office](../vsto/office-ui-customization.md).  
  
## <a name="see-also"></a>Viz také  
 [Návod: Vytvoření vašeho prvního doplňku VSTO pro PowerPoint](../vsto/walkthrough-creating-your-first-vsto-add-in-for-powerpoint.md)   
 [Začínáme programováním doplňků VSTO](../vsto/getting-started-programming-vsto-add-ins.md)   
 [Přehled vývoje řešení pro systém Office &#40; VSTO &#41;](../vsto/office-solutions-development-overview-vsto.md)   
 [Architektura doplňků VSTO](../vsto/architecture-of-vsto-add-ins.md)   
 [Postupy: vytváření projektů Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [Programování doplňků VSTO](../vsto/programming-vsto-add-ins.md)   
 [Psaní kódu v řešeních pro systém Office](../vsto/writing-code-in-office-solutions.md)   
 [Primární spolupracující sestavení sady Office](../vsto/office-primary-interop-assemblies.md)   
 [Přizpůsobení uživatelského rozhraní sady Office](../vsto/office-ui-customization.md)   
 [PowerPoint 2010 v vývoj pro Office](http://go.microsoft.com/fwlink/?LinkId=199015)  
  
  