---
title: Řešení projektu
ms.date: 08/14/2019
ms.topic: conceptual
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
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: f2158918aa6c2487719043abd797eb9d5e8f3f2e
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/16/2019
ms.locfileid: "69551395"
---
# <a name="project-solutions"></a>Řešení projektu
  [!INCLUDE[vs_dev12](../vsto/includes/vs-dev12-md.md)]poskytuje šablony projektu, které můžete použít k vytvoření doplňků VSTO pro systém Microsoft Office projekt. Doplňky VSTO můžete použít k automatizaci projektu, rozšiřování funkcí projektu nebo přizpůsobení uživatelského rozhraní (UI) projektu.

 Další informace o doplňcích VSTO najdete v tématu Začínáme s [programováním doplňků VSTO](../vsto/getting-started-programming-vsto-add-ins.md) a [architektury doplňků VSTO](../vsto/architecture-of-vsto-add-ins.md). Pokud začínáte s programováním pomocí systém Microsoft Office, přečtěte si téma Začínáme s vývojem pro [ &#40;Office v sadě Visual Studio&#41;](../vsto/getting-started-office-development-in-visual-studio.md).

 [!INCLUDE[appliesto_projallapp](../vsto/includes/appliesto-projallapp-md.md)]

[!include[Add-ins note](includes/addinsnote.md)]

## <a name="automate-project-by-using-the-project-object-model"></a>Automatizace projektu pomocí objektového modelu projektu
 Objektový model projektu zpřístupňuje mnoho typů, které lze použít k automatizaci projektu. Tyto typy umožňují psát kód pro provádění běžných úloh, jako je programové vytváření a úprava úloh v projektu.

 Pro přístup k objektovému modelu projektu z doplňku VSTO použijte `Application` pole `ThisAddIn` třídy v projektu. `Application` Pole`Microsoft.Office.Interop.MsProject.Application` vrátí objekt, který představuje aktuální instanci projektu. Další informace najdete v tématu [programové doplňky VSTO](../vsto/programming-vsto-add-ins.md).

 Při volání do objektového modelu projektu použijete typy, které jsou k dispozici v primárním sestavení vzájemné spolupráce pro projekt. Primární definiční sestavení funguje jako most mezi spravovaným kódem v doplňku VSTO a objektovým modelem COM v projektu. Všechny typy v primárním definičním sestavení projektu jsou definovány v `Microsoft.Office.Interop.MSProject` oboru názvů. Další informace o primárních sestaveních vzájemné spolupráce najdete v tématu věnovaném [vývoji řešení pro Office &#40;přehled VSTO&#41; ](../vsto/office-solutions-development-overview-vsto.md) a [sestavení primární spolupráce Office](../vsto/office-primary-interop-assemblies.md).

## <a name="use-the-project-object-model-documentation"></a>Použití dokumentace objektového modelu projektu
 Úplné informace o objektovém modelu projektu naleznete v tématu Reference k objektovému modelu projektu VBA. Objekt modelu objektu VBA odkazuje na dokument model objektu projektu, protože je vystavený kódu jazyk Visual Basic for Application (VBA). Další informace najdete v tématu [referenční materiály k objektovému modelu projektu 2010](http://go.microsoft.com/fwlink/?LinkId=199771).

 Všechny objekty a členy v referencích objektového modelu VBA odpovídají typům a členům v primárním definičním sestavení projektu (PIA). Například objekt kalendáře v odkazu modelu objektu VBA odpovídá `Microsoft.Office.Interop.MSProject.Calendar` typu v projektu PIA. I když odkaz na objektový model VBA poskytuje příklady kódu pro většinu vlastností, metod a událostí, je nutné překládat kód VBA v tomto odkazu na Visual Basic nebo vizuál C# , pokud je chcete použít v projektu doplňku VSTO projektu, který vytvoříte pomocí pomocí sady Visual Studio.

> [!NOTE]
> V tuto chvíli neexistuje žádná referenční dokumentace pro primární definiční sestavení projektu.

### <a name="infrastructure-types-in-the-project-primary-interop-assembly"></a>Typy infrastruktury v primárním definičním sestavení projektu
 Při psaní kódu, který používá projekt PIA, si můžete všimnout mnoha typů, které nejsou popsány v referenční příručce jazyka VBA. Tyto další typy usnadňují převod objektů v objektovém modelu založeném na modelu COM projektu na spravovaný kód, nejsou určeny pro použití přímo v kódu.

 Další informace naleznete v tématu [Přehled tříd a rozhraní v primárních sestaveních vzájemné spolupráce pro sadu Office](http://go.microsoft.com/fwlink/?LinkId=189592).

## <a name="customize-the-user-interface-of-project"></a>Přizpůsobení uživatelského rozhraní projektu
 Uživatelské rozhraní projektu můžete přizpůsobit následujícími způsoby.

|Úloha|Další informace|
|----------|--------------------------|
|Přidání vlastních karet na pás karet v projektu|[Přehled pásu karet](../vsto/ribbon-overview.md)|

 Další informace o přizpůsobení uživatelského rozhraní aplikace Project a dalších systém Microsoft Officech aplikací najdete v tématu [přizpůsobení uživatelského rozhraní systému Office](../vsto/office-ui-customization.md).

## <a name="see-also"></a>Viz také:
- [Návod: Vytvoření prvního doplňku VSTO pro Project](../vsto/walkthrough-creating-your-first-vsto-add-in-for-project.md)
- [Začínáme s programováním doplňků VSTO](../vsto/getting-started-programming-vsto-add-ins.md)
- [Přehled &#40;vývoje řešení pro systém Office VSTO&#41;](../vsto/office-solutions-development-overview-vsto.md)
- [Architektura doplňků VSTO](../vsto/architecture-of-vsto-add-ins.md)
- [Postupy: Vytváření projektů Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md)
- [Programové doplňky VSTO](../vsto/programming-vsto-add-ins.md)
- [Psaní kódu v řešeních pro systém Office](../vsto/writing-code-in-office-solutions.md)
- [Sestavení primární spolupráce pro Office](../vsto/office-primary-interop-assemblies.md)
- [Přizpůsobení uživatelského rozhraní systému Office](../vsto/office-ui-customization.md)
- [Project 2010 a Project Server 2010 ve vývoji pro Office](http://go.microsoft.com/fwlink/?LinkId=199016)
