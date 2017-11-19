---
title: "Projekt řešení | Microsoft Docs"
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
- projects [Office development in Visual Studio], Project
- Office solutions [Office development in Visual Studio], Project
- Project [Office development in Visual Studio]
- templates [Office development in Visual Studio], Project
- Office projects [Office development in Visual Studio], Project
- solutions [Office development in Visual Studio], Project
ms.assetid: 4ce92269-eb6d-44aa-bee3-6d38ec9995f9
caps.latest.revision: "34"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 584f98e9fbe6a8883039cad03e6b0782d225b8bb
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="project-solutions"></a>Projektová řešení
  [!INCLUDE[vs_dev12](../vsto/includes/vs-dev12-md.md)]poskytuje šablony projektů, které můžete použít k vytvoření doplňků VSTO pro aplikaci Microsoft Office Project. Doplňků VSTO můžete automatizovat projektu, rozšířit funkce projektu nebo si přizpůsobit projektu uživatelské rozhraní (UI).  
  
 Další informace o doplňků VSTO najdete v tématu [získávání VSTO spuštění programování doplňků](../vsto/getting-started-programming-vsto-add-ins.md) a [architektura VSTO doplňky](../vsto/architecture-of-vsto-add-ins.md). Pokud jste ještě programování s Microsoft Office, najdete v části [Začínáme &#40; vývoj pro Office v sadě Visual Studio &#41;](../vsto/getting-started-office-development-in-visual-studio.md).  
  
 [!INCLUDE[appliesto_projallapp](../vsto/includes/appliesto-projallapp-md.md)]  
  
> [!NOTE]  
>  Máte zájem o vývoji řešení, které rozšiřují Office prostředí napříč [více platforem](https://dev.office.com/add-in-availability)? Podívejte se na [Office Add in modelu](https://dev.office.com/docs/add-ins/overview/office-add-ins). Doplňky Office mají malé nároky ve srovnání s doplňků VSTO a řešení a můžete je vytvořit pomocí téměř jakoukoli webové programování technologie, jako je například HTML5, JavaScript, CSS3 a XML.  
  
## <a name="automating-project-by-using-the-project-object-model"></a>Automatizace projektu pomocí objektového modelu projektu  
 Objektový model projektu zpřístupní mnoho typů, které můžete použít k automatizaci projektu. Tyto typy umožňují napsat kód pro provádět běžné úkoly jako prostřednictvím kódu programu vytvoření a úprava úloh v projektu.  
  
 Pro přístup k modelu objektu projekt z doplňku VSTO, použijte `Application` pole z `ThisAddIn` třídy ve vašem projektu. `Application` Pole vrátí objekt Microsoft.Office.Interop.MsProject.Application, který představuje aktuální instanci projektu. Další informace najdete v tématu [programování doplňků VSTO](../vsto/programming-vsto-add-ins.md).  
  
 Při volání do modelu objektu projektu použijete typy, které jsou uvedeny v primární spolupracující sestavení pro projekt. Primární spolupracující sestavení pracuje jako most mezi spravovaného kódu v doplňku VSTO a objektového modelu COM v projektu. Všechny typy v sestavení primární spolupráce projektu jsou definovány v oboru názvů Microsoft.Office.Interop.MSProject. Další informace o primární spolupracující sestavení najdete v tématu [přehled vývoje řešení pro systém Office &#40; VSTO &#41; ](../vsto/office-solutions-development-overview-vsto.md) a [primární spolupracující sestavení Office](../vsto/office-primary-interop-assemblies.md).  
  
## <a name="using-the-project-object-model-documentation"></a>Pomocí dokumentace projektu objekt modelu  
 Úplné informace o projektu objektový model najdete odkaz na projekt VBA objektu modelu. Reference jazyka VBA objektu modelu dokumenty objektový model projektu, jako je zpřístupněné pro Visual Basic pro aplikace (VBA) kód. Další informace najdete v tématu [odkaz na objekt modelu projektu 2010](http://go.microsoft.com/fwlink/?LinkId=199771).  
  
 Všechny objekty a členy ve model odkaz na VBA odpovídají typy a členy v primární spolupracující sestavení projektu (PIA). Například objekt kalendáře ve model odkaz na VBA odpovídá typu Microsoft.Office.Interop.MSProject.Calendar v PIA projektu. I když reference VBA objektu modelu poskytuje příklady kódu pro většinu vlastností, metod a událostí, pokud chcete používat v projektu doplňku VSTO projektu, který vytvoříte pomocí musí překládat VBA kód v této referenci na Visual Basic a Visual C# Visual Studio.  
  
> [!NOTE]  
>  V tuto chvíli není žádná referenční dokumentace pro primární spolupracující sestavení projektu.  
  
### <a name="infrastructure-types-in-the-project-primary-interop-assembly"></a>Typy infrastruktury v primární spolupracující sestavení projektu  
 Při psaní kódu, který používá PIA projektu, můžete si všimnout mnoho typů, které nejsou popsané v dokumentaci VBA pro vytváření. Tyto další typy nápovědu překládat objekty v modelu COM na objekt z projektu do spravovaného kódu, není určena pro použití přímo v kódu.  
  
 Další informace najdete v tématu[přehled třídy a rozhraní v primární zprostředkovatel komunikace s objekty sestavení sady Office](http://go.microsoft.com/fwlink/?LinkId=189592).  
  
## <a name="customizing-the-user-interface-of-project"></a>Přizpůsobení uživatelského rozhraní projektu  
 Následujícím způsobem můžete přizpůsobit rozhraní projektu.  
  
|Úloha|Další informace|  
|----------|--------------------------|  
|Přidat vlastní karty na pásu karet v projektu|[Přehled pásu karet](../vsto/ribbon-overview.md)|  
  
 Další informace o přizpůsobení uživatelského rozhraní projektu a další aplikace Microsoft Office, najdete v části [přizpůsobení uživatelského rozhraní Office](../vsto/office-ui-customization.md).  
  
## <a name="see-also"></a>Viz také  
 [Návod: Vytvoření vašeho prvního doplňku VSTO pro projekt](../vsto/walkthrough-creating-your-first-vsto-add-in-for-project.md)   
 [Začínáme programováním doplňků VSTO](../vsto/getting-started-programming-vsto-add-ins.md)   
 [Přehled vývoje řešení pro systém Office &#40; VSTO &#41;](../vsto/office-solutions-development-overview-vsto.md)   
 [Architektura doplňků VSTO](../vsto/architecture-of-vsto-add-ins.md)   
 [Postupy: vytváření projektů Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [Programování doplňků VSTO](../vsto/programming-vsto-add-ins.md)   
 [Psaní kódu v řešeních pro systém Office](../vsto/writing-code-in-office-solutions.md)   
 [Primární spolupracující sestavení sady Office](../vsto/office-primary-interop-assemblies.md)   
 [Přizpůsobení uživatelského rozhraní sady Office](../vsto/office-ui-customization.md)   
 [Project 2010 a Microsoft Project 2010 v vývoj pro Office](http://go.microsoft.com/fwlink/?LinkId=199016)  
  
  