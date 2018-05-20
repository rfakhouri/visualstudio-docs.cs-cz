---
title: InfoPath – řešení
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
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
manager: douge
ms.workload:
- office
ms.openlocfilehash: f61607f904740a48bc73d7b4b310e36b3894df17
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/17/2018
---
# <a name="infopath-solutions"></a>InfoPath – řešení
  Visual Studio poskytuje šablony projektů, které můžete použít k vytvoření doplňků VSTO pro Microsoft Office InfoPath 2013 a InfoPath 2010. InfoPath není k dispozici v Office 2016.  
  
> [!NOTE]  
>  Můžete přesto vytvořit doplňku VSTO pro aplikaci InfoPath i v případě, že jste nainstalovali Office 2016. Stačí nainstalujte InfoPath 2013 nebo Office 2013-souběžného s Office 2016.  
  
 [!INCLUDE[appliesto_infoallapp](../vsto/includes/appliesto-infoallapp-md.md)]  
  
> [!NOTE]  
>  Máte zájem o vývoji řešení, které rozšiřují Office prostředí napříč [více platforem](https://dev.office.com/add-in-availability)? Podívejte se na [Office Add in modelu](https://dev.office.com/docs/add-ins/overview/office-add-ins). Doplňky Office mají malé nároky ve srovnání s doplňků VSTO a řešení a můžete je vytvořit pomocí téměř jakoukoli webové programování technologie, jako je například HTML5, JavaScript, CSS3 a XML.  
  
 Doplňků VSTO pro aplikaci InfoPath jsou podobná doplňků VSTO pro jiné aplikace Microsoft Office. Tyto typy řešení obsahují sestavení zavedená aplikace. Koncoví uživatelé mohou mít přístup k funkci toto sestavení bez ohledu na to, které tvoří nebo formuláře šablony je otevřený. Další informace o doplňků VSTO najdete v tématu [Začínáme s programováním doplňků VSTO](../vsto/getting-started-programming-vsto-add-ins.md) a [architektura VSTO doplňky](../vsto/architecture-of-vsto-add-ins.md).  
  
> [!NOTE]  
>  Visual Studio 2015 nezahrnuje InfoPath formuláře šablony projektů, které byly poskytnuty v předchozích verzích sady Visual Studio. Visual Studio 2015 nemůžete použít také otevřít nebo upravit InfoPath formuláře šablony projektu, který byl vytvořen v předchozí verzi sady Visual Studio. Můžete však otevřít a upravit projektu šablony aplikace InfoPath formuláře pomocí nástrojů Visual Studio Tools for Applications. Další informace najdete v tématu [práce s projekty VSTO 2008 v Infopathu 2010.](http://go.microsoft.com/fwlink/?LinkID=218903).  
  
## <a name="automate-infopath-by-using-an-add-in"></a>Pomocí doplňku automatizovat InfoPath  
 Pro přístup k modelu objektu InfoPath z Office VSTO doplňku vytvořili pomocí nástroje pro vývoj pro Office v sadě Visual Studio, použijte `Application` pole z `ThisAddIn` třídy ve vašem projektu. `Application` Pole vrátí <xref:Microsoft.Office.Interop.InfoPath.Application> objekt, který představuje aktuální instanci aplikace InfoPath. Další informace najdete v tématu [doplňků Program VSTO](../vsto/programming-vsto-add-ins.md).  
  
 Při volání do modelu objektu InfoPath z doplňku VSTO můžete používat typy, které jsou uvedeny v primární spolupracující sestavení pro aplikaci InfoPath. Primární spolupracující sestavení pracuje jako most mezi spravovaného kódu v doplňku VSTO a objektového modelu COM v aplikaci InfoPath. Všechny typy v sestavení primární spolupráce InfoPath jsou definovány v <xref:Microsoft.Office.Interop.InfoPath> oboru názvů. Další informace o sestavení primární spolupráce InfoPath najdete v tématu [o aplikaci Microsoft Office InfoPath primární spolupracující sestavení](http://msdn.microsoft.com/en-us/1b3ae03c-6951-49e4-a489-4712d3f7ba72). Další informace o primární spolupracující sestavení obecně platí, najdete v části [přehled vývoje řešení pro systém Office &#40;VSTO&#41; ](../vsto/office-solutions-development-overview-vsto.md) a [primární spolupracující sestavení Office](../vsto/office-primary-interop-assemblies.md).  
  
## <a name="customize-the-user-iterface-of-infopath-by-using-an-add-in"></a>Přizpůsobit iterface uživatele aplikace InfoPath pomocí doplňku  
 Když vytvoříte doplňku VSTO pro aplikaci InfoPath, máte několik různých možností přizpůsobení uživatelského rozhraní. Následující tabulka uvádí některé z těchto možností.  
  
|Úloha|Další informace|  
|----------|--------------------------|  
|Vytvoření vlastního podokna úloh.|[Vlastní podokna úloh](../vsto/custom-task-panes.md)|  
|Přidáte vlastní karty na pásu karet v aplikaci InfoPath.|[Přizpůsobení pásu karet pro aplikaci InfoPath](../vsto/customizing-a-ribbon-for-infopath.md)|  
  
 Další informace o přizpůsobení uživatelského rozhraní InfoPath a další aplikace Microsoft Office, najdete v části [přizpůsobení uživatelského rozhraní Office](../vsto/office-ui-customization.md).  
  
## <a name="see-also"></a>Viz také  
 [O aplikaci Microsoft Office InfoPath sestavení primární spolupráce](http://msdn.microsoft.com/en-us/1b3ae03c-6951-49e4-a489-4712d3f7ba72)   
 [Začínáme s programováním doplňků VSTO](../vsto/getting-started-programming-vsto-add-ins.md)   
 [Přehled vývoje řešení pro systém Office &#40;VSTO&#41;](../vsto/office-solutions-development-overview-vsto.md)   
 [Architektura doplňků VSTO](../vsto/architecture-of-vsto-add-ins.md)   
 [Postupy: vytváření projektů Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [Program doplňků VSTO](../vsto/programming-vsto-add-ins.md)   
 [Psaní kódu v řešeních pro systém Office](../vsto/writing-code-in-office-solutions.md)   
 [Primární spolupracující sestavení sady Office](../vsto/office-primary-interop-assemblies.md)   
 [Přizpůsobení uživatelského rozhraní sady Office](../vsto/office-ui-customization.md)   
 [InfoPath 2010 v vývoj pro Office](http://go.microsoft.com/fwlink/?LinkId=199012)  
  
  