---
title: InfoPath – řešení
ms.date: 08/14/2019
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
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: d227e3c87810156e6e4262a79cfcc9b126d68417
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/16/2019
ms.locfileid: "69551734"
---
# <a name="infopath-solutions"></a>InfoPath – řešení
  Visual Studio poskytuje šablony projektů, pomocí kterých můžete vytvářet doplňky VSTO pro systém Microsoft Office InfoPath 2013 a InfoPath 2010. Aplikace InfoPath není v sadě Office 2016 k dispozici.

> [!NOTE]
> Doplněk VSTO pro InfoPath můžete přesto vytvořit i v případě, že jste nainstalovali Office 2016. Stačí nainstalovat InfoPath 2013 nebo Office 2013 souběžně s Office 2016.

 [!INCLUDE[appliesto_infoallapp](../vsto/includes/appliesto-infoallapp-md.md)]

[!include[Add-ins note](includes/addinsnote.md)]

 Doplňky VSTO pro InfoPath jsou podobné doplňkům VSTO pro jiné aplikace systém Microsoft Office. Tyto typy řešení se skládají ze sestavení, které je načteno aplikací. Koncoví uživatelé mohou mít přístup k funkcím tohoto sestavení bez ohledu na to, který formulář nebo šablonu formuláře jsou otevřené. Další informace o doplňcích VSTO najdete v tématu Začínáme s [programováním doplňků VSTO](../vsto/getting-started-programming-vsto-add-ins.md) a [architektury doplňků VSTO](../vsto/architecture-of-vsto-add-ins.md).

> [!NOTE]
> Visual Studio 2015 neobsahuje projekty šablon formuláře aplikace InfoPath, které byly zadány v předchozích verzích sady Visual Studio. Nelze také použít sadu Visual Studio 2015 k otevření nebo úpravám projektu šablony formuláře aplikace InfoPath, který byl vytvořen v předchozí verzi sady Visual Studio. Můžete však otevřít a upravit projekt šablony formuláře aplikace InfoPath pomocí Visual Studio Tools for Applications. Další informace najdete v tématu [práce s projekty VSTO 2008 v infopathu 2010.](http://go.microsoft.com/fwlink/?LinkID=218903).

## <a name="automate-infopath-by-using-an-add-in"></a>Automatizace InfoPathu pomocí doplňku
 Chcete-li získat přístup k objektovému modelu aplikace InfoPath z doplňku Office VSTO vytvořeného pomocí nástrojů pro vývoj pro Office v `Application` sadě Visual Studio `ThisAddIn` , použijte pole třídy v projektu. `Application` Pole<xref:Microsoft.Office.Interop.InfoPath.Application> vrátí objekt, který představuje aktuální instanci aplikace InfoPath. Další informace najdete v tématu [programové doplňky VSTO](../vsto/programming-vsto-add-ins.md).

 Při volání do objektového modelu aplikace InfoPath z doplňku VSTO použijete typy, které jsou k dispozici v primárním sestavení vzájemné spolupráce pro aplikaci InfoPath. Primární definiční sestavení funguje jako most mezi spravovaným kódem v doplňku VSTO a objektovým modelem COM v aplikaci InfoPath. Všechny typy v primárním sestavení vzájemné spolupráce aplikace InfoPath jsou definovány <xref:Microsoft.Office.Interop.InfoPath> v oboru názvů. Další informace o sestavení primární spolupráce aplikace InfoPath najdete v tématu [informace o primárním sestavení vzájemné spolupráce aplikace systém Microsoft Office InfoPath](https://msdn.microsoft.com/1b3ae03c-6951-49e4-a489-4712d3f7ba72). Další informace o primárních sestaveních vzájemné spolupráce najdete v tématu [vývoj řešení pro &#40;Office&#41; přehled VSTO](../vsto/office-solutions-development-overview-vsto.md) a [sestavení primární spolupráce Office](../vsto/office-primary-interop-assemblies.md).

## <a name="customize-the-user-interface-of-infopath-by-using-an-add-in"></a>Přizpůsobení uživatelského rozhraní aplikace InfoPath pomocí doplňku
 Při vytváření doplňku VSTO pro InfoPath máte několik různých možností přizpůsobení uživatelského rozhraní. Některé z těchto možností jsou uvedené v následující tabulce.

|Úloha|Další informace|
|----------|--------------------------|
|Vytvoření vlastního podokna úloh.|[Vlastní podokna úloh](../vsto/custom-task-panes.md)|
|Přidejte vlastní karty na pás karet v aplikaci InfoPath.|[Přizpůsobení pásu karet pro aplikaci InfoPath](../vsto/customizing-a-ribbon-for-infopath.md)|

 Další informace o přizpůsobení uživatelského rozhraní aplikace InfoPath a dalších systém Microsoft Officech aplikací najdete v tématu [přizpůsobení uživatelského rozhraní systému Office](../vsto/office-ui-customization.md).

## <a name="see-also"></a>Viz také:
- [O sestaveních primární spolupráce aplikace systém Microsoft Office InfoPath](https://msdn.microsoft.com/1b3ae03c-6951-49e4-a489-4712d3f7ba72)
- [Začínáme s programováním doplňků VSTO](../vsto/getting-started-programming-vsto-add-ins.md)
- [Přehled &#40;vývoje řešení pro systém Office VSTO&#41;](../vsto/office-solutions-development-overview-vsto.md)
- [Architektura doplňků VSTO](../vsto/architecture-of-vsto-add-ins.md)
- [Postupy: Vytváření projektů Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md)
- [Programové doplňky VSTO](../vsto/programming-vsto-add-ins.md)
- [Psaní kódu v řešeních pro systém Office](../vsto/writing-code-in-office-solutions.md)
- [Sestavení primární spolupráce pro Office](../vsto/office-primary-interop-assemblies.md)
- [Přizpůsobení uživatelského rozhraní systému Office](../vsto/office-ui-customization.md)
- [InfoPath 2010 ve vývoji pro Office](http://go.microsoft.com/fwlink/?LinkId=199012)
