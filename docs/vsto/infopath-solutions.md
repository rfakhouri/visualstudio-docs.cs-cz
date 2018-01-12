---
title: "InfoPath – řešení | Microsoft Docs"
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
- solutions [Office development in Visual Studio], InfoPath
- templates [Office development in Visual Studio], InfoPath
- InfoPath [Office development in Visual Studio]
- Office development in Visual Studio, InfoPath solutions
- projects [Office development in Visual Studio], InfoPath
- Office solutions [Office development in Visual Studio], InfoPath
- Office projects [Office development in Visual Studio], InfoPath
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 4e59b91ff6159af8f6e5736621c0443d3d96c8b5
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="infopath-solutions"></a>Řešení pro aplikaci InfoPath
  Visual Studio poskytuje šablony projektů, které můžete použít k vytvoření doplňků VSTO pro Microsoft Office InfoPath 2013 a InfoPath 2010. InfoPath není k dispozici v Office 2016.  
  
> [!NOTE]  
>  Můžete přesto vytvořit doplňku VSTO pro aplikaci InfoPath i v případě, že jste nainstalovali Office 2016. Stačí nainstalujte InfoPath 2013 nebo Office 2013-souběžného s Office 2016.  
  
 [!INCLUDE[appliesto_infoallapp](../vsto/includes/appliesto-infoallapp-md.md)]  
  
> [!NOTE]  
>  Máte zájem o vývoji řešení, které rozšiřují Office prostředí napříč [více platforem](https://dev.office.com/add-in-availability)? Podívejte se na [Office Add in modelu](https://dev.office.com/docs/add-ins/overview/office-add-ins). Doplňky Office mají malé nároky ve srovnání s doplňků VSTO a řešení a můžete je vytvořit pomocí téměř jakoukoli webové programování technologie, jako je například HTML5, JavaScript, CSS3 a XML.  
  
 Doplňků VSTO pro aplikaci InfoPath jsou podobná doplňků VSTO pro jiné aplikace Microsoft Office. Tyto typy řešení obsahují sestavení zavedená aplikace. Koncoví uživatelé mohou mít přístup k funkci toto sestavení bez ohledu na to, které tvoří nebo formuláře šablony je otevřený. Další informace o doplňků VSTO najdete v tématu [získávání VSTO spuštění programování doplňků](../vsto/getting-started-programming-vsto-add-ins.md) a [architektura VSTO doplňky](../vsto/architecture-of-vsto-add-ins.md).  
  
> [!NOTE]  
>  Visual Studio 2015 nezahrnuje InfoPath formuláře šablony projektů, které byly poskytnuty v předchozích verzích sady Visual Studio. Visual Studio 2015 nemůžete použít také otevřít nebo upravit InfoPath formuláře šablony projektu, který byl vytvořen v předchozí verzi sady Visual Studio. Můžete však otevřít a upravit projektu šablony aplikace InfoPath formuláře pomocí nástrojů Visual Studio Tools for Applications. Další informace najdete v tématu [práce s projekty 2008 VSTO v Infopathu 2010.](http://go.microsoft.com/fwlink/?LinkID=218903).  
  
## <a name="automating-infopath-by-using-an-add-in"></a>Automatizace aplikace InfoPath pomocí doplňku  
 Pro přístup k modelu objektu InfoPath z Office VSTO doplňku vytvořili pomocí nástroje pro vývoj pro Office v sadě Visual Studio, použijte `Application` pole z `ThisAddIn` třídy ve vašem projektu. `Application` Pole vrátí <xref:Microsoft.Office.Interop.InfoPath.Application> objekt, který představuje aktuální instanci aplikace InfoPath. Další informace najdete v tématu [programování doplňků VSTO](../vsto/programming-vsto-add-ins.md).  
  
 Při volání do modelu objektu InfoPath z doplňku VSTO můžete používat typy, které jsou uvedeny v primární spolupracující sestavení pro aplikaci InfoPath. Primární spolupracující sestavení pracuje jako most mezi spravovaného kódu v doplňku VSTO a objektového modelu COM v aplikaci InfoPath. Všechny typy v sestavení primární spolupráce InfoPath jsou definovány v <xref:Microsoft.Office.Interop.InfoPath> oboru názvů. Další informace o sestavení primární spolupráce InfoPath najdete v tématu [o the Microsoft Office InfoPath primární zprostředkovatel komunikace s objekty sestavení](http://msdn.microsoft.com/en-us/1b3ae03c-6951-49e4-a489-4712d3f7ba72). Další informace o primární spolupracující sestavení obecně platí, najdete v části [přehled vývoje řešení pro systém Office &#40; VSTO &#41; ](../vsto/office-solutions-development-overview-vsto.md) a [primární spolupracující sestavení Office](../vsto/office-primary-interop-assemblies.md).  
  
## <a name="customizing-the-user-interface-of-infopath-by-using-an-add-in"></a>Přizpůsobení uživatelského rozhraní aplikace InfoPath pomocí doplňku  
 Když vytvoříte doplňku VSTO pro aplikaci InfoPath, máte několik různých možností přizpůsobení uživatelského rozhraní. Následující tabulka uvádí některé z těchto možností.  
  
|Úloha|Další informace|  
|----------|--------------------------|  
|Vytvoření vlastního podokna úloh.|[Vlastní podokona úloh](../vsto/custom-task-panes.md)|  
|Přidáte vlastní karty na pásu karet v aplikaci InfoPath.|[Přizpůsobení pásu karet pro aplikaci InfoPath](../vsto/customizing-a-ribbon-for-infopath.md)|  
  
 Další informace o přizpůsobení uživatelského rozhraní InfoPath a další aplikace Microsoft Office, najdete v části [přizpůsobení uživatelského rozhraní Office](../vsto/office-ui-customization.md).  
  
## <a name="see-also"></a>Viz také  
 [O sestavení sady Microsoft Office InfoPath primární spolupráce](http://msdn.microsoft.com/en-us/1b3ae03c-6951-49e4-a489-4712d3f7ba72)   
 [Začínáme programováním doplňků VSTO](../vsto/getting-started-programming-vsto-add-ins.md)   
 [Přehled vývoje řešení pro systém Office &#40; VSTO &#41;](../vsto/office-solutions-development-overview-vsto.md)   
 [Architektura doplňků VSTO](../vsto/architecture-of-vsto-add-ins.md)   
 [Postupy: vytváření projektů Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [Programování doplňků VSTO](../vsto/programming-vsto-add-ins.md)   
 [Psaní kódu v řešeních pro systém Office](../vsto/writing-code-in-office-solutions.md)   
 [Primární spolupracující sestavení sady Office](../vsto/office-primary-interop-assemblies.md)   
 [Přizpůsobení uživatelského rozhraní sady Office](../vsto/office-ui-customization.md)   
 [InfoPath 2010 v vývoj pro Office](http://go.microsoft.com/fwlink/?LinkId=199012)  
  
  