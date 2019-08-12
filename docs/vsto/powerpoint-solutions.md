---
title: Řešení aplikace PowerPoint
ms.date: 02/02/2017
ms.topic: conceptual
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
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 9d2c85a4af986c62d3e3f3c3a3f4333baa2975ee
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68926429"
---
# <a name="powerpoint-solutions"></a>Řešení aplikace PowerPoint
  Visual Studio poskytuje šablony projektů, pomocí kterých můžete vytvářet doplňky VSTO pro systém Microsoft Office PowerPointu. Doplňky VSTO můžete použít k automatizaci PowerPointu, rozšiřování funkcí PowerPointu nebo přizpůsobení uživatelského rozhraní (UI) PowerPointu.

 Další informace o doplňcích VSTO najdete v tématu Začínáme s [programováním doplňků VSTO](../vsto/getting-started-programming-vsto-add-ins.md) a [architektury doplňků VSTO](../vsto/architecture-of-vsto-add-ins.md). Pokud začínáte s programováním pomocí systém Microsoft Office, přečtěte si téma Začínáme s vývojem pro [ &#40;Office v sadě Visual Studio&#41;](../vsto/getting-started-office-development-in-visual-studio.md).

 [!INCLUDE[appliesto_pptallapp](../vsto/includes/appliesto-pptallapp-md.md)]

> [!NOTE]
> Zajímá vás vývoj řešení, které rozšiřují Office prostředí napříč [více platforem](https://dev.office.com/add-in-availability)? Podívejte se na nové [Office Add-ins modelu](https://dev.office.com/docs/add-ins/overview/office-add-ins). Doplňky sady Office mají malé náklady v porovnání s doplňky VSTO a řešení a je můžete vytvořit s využitím téměř jakékoli webové programování technologie, jako je například HTML5, JavaScript, CSS3 a XML.

 ![odkaz na video](../vsto/media/playvideo.gif "odkaz na video") Související video ukázku najdete v tématu [návody: Vytvořit doplněk pro Microsoft PowerPoint? ](http://go.microsoft.com/fwlink/?LinkId=132767).

## <a name="automate-powerpoint-by-using-the-powerpoint-object-model"></a>Automatizace PowerPointu pomocí objektového modelu aplikace PowerPoint
 Model objektu aplikace PowerPoint zpřístupňuje mnoho typů, které lze použít k automatizaci aplikace PowerPoint. Tyto typy umožňují psát kód pro provádění běžných úloh:

- Vytváření a formátování prezentací prostřednictvím kódu programu

- Přidejte nebo odeberte snímky z prezentací.

- Přidání nebo změna tvarů na snímku.

  Pro přístup k objektovému modelu aplikace PowerPoint z doplňku VSTO použijte `Application` pole `ThisAddIn` třídy v projektu. Pole vrátí aplikační objekt, který představuje aktuální instanci aplikace PowerPoint. [](/previous-versions/office/developer/office-2010/ff764034(v=office.14)) `Application` Další informace najdete v tématu [programové doplňky VSTO](../vsto/programming-vsto-add-ins.md).

  Při volání do modelu objektu aplikace PowerPoint použijete typy, které jsou k dispozici v primárním sestavení vzájemné spolupráce pro PowerPoint. Primární definiční sestavení funguje jako most mezi spravovaným kódem v doplňku VSTO a objektovým modelem COM v PowerPointu. Všechny typy v primárním sestavení spolupráce PowerPointu jsou definované v oboru názvů [Microsoft. Office. Interop. PowerPoint](/previous-versions/office/developer/office-2010/ff763170(v=office.14)) . Další informace o primárních sestaveních vzájemné spolupráce najdete v tématu věnovaném [vývoji řešení pro Office &#40;přehled VSTO&#41; ](../vsto/office-solutions-development-overview-vsto.md) a [sestavení primární spolupráce Office](../vsto/office-primary-interop-assemblies.md).

## <a name="WordOMDocumentation"></a>Použití dokumentace modelu objektu aplikace PowerPoint
 Úplné informace o objektovém modelu aplikace PowerPoint naleznete v odkazu na primární definiční sestavení aplikace PowerPoint (PIA) a referenční materiály k objektovému modelu VBA.

### <a name="primary-interop-assembly-reference"></a>Odkaz na primární definiční sestavení
 Referenční dokumentace k aplikaci PowerPoint PIA popisuje typy v primárním sestavení vzájemné spolupráce pro aplikaci PowerPoint. Tato dokumentace je k dispozici v následujícím umístění: [Odkaz na primární definiční sestavení aplikace PowerPoint 2010](http://go.microsoft.com/fwlink/?LinkId=189588)

 Další informace o návrhu aplikace PowerPoint PIA, jako jsou rozdíly mezi třídami a rozhraními PIA a jak jsou implementovány události v PIA, naleznete v tématu [Přehled tříd a rozhraní v primárních sestaveních vzájemné spolupráce pro systém Office](http://go.microsoft.com/fwlink/?LinkId=199885).

### <a name="vba-object-model-reference"></a>Referenční dokumentace modelu objektu VBA
 Model objektu VBA odkazuje na dokument model objektu aplikace PowerPoint, protože je vystavený pro kód jazyk Visual Basic for Application (VBA). Další informace najdete v tématu [referenční materiály k objektovému modelu powerpointu 2010](http://go.microsoft.com/fwlink/?LinkId=199770).

 Všechny objekty a členy v referencích objektového modelu VBA odpovídají typům a členům v primárním sestavení Interop (PIA) aplikace PowerPoint. Například objekt prezentace v odkazu modelu objektu VBA odpovídá typu [prezentace](/previous-versions/office/developer/office-2010/ff761925(v=office.14)) v aplikaci PowerPoint PIA. I když Reference k objektovému modelu VBA poskytuje příklady kódu pro většinu vlastností, metod a událostí, je nutné překládat kód VBA v tomto odkazu na Visual Basic nebo C# vizuál, pokud je chcete použít v projektu doplňku aplikace PowerPoint VSTO, který vytvoříte pomocí pomocí sady Visual Studio.

## <a name="customize-the-user-interface-of-powerpoint"></a>Přizpůsobení uživatelského rozhraní aplikace PowerPoint
 Uživatelské rozhraní aplikace PowerPoint můžete upravit následujícími způsoby.

|Úloha|Další informace|
|----------|--------------------------|
|Vytvoření vlastního podokna úloh.|[Vlastní podokna úloh](../vsto/custom-task-panes.md)|
|Přidejte na pás karet vlastní karty.|[Přehled pásu karet](../vsto/ribbon-overview.md)|
|Přidejte vlastní skupiny na integrovanou kartu na pásu karet.|[Postupy: Přizpůsobení předdefinované karty](../vsto/how-to-customize-a-built-in-tab.md)|

 Další informace o přizpůsobení uživatelského rozhraní aplikace PowerPoint a dalších systém Microsoft Officech aplikací najdete v tématu [přizpůsobení uživatelského rozhraní systému Office](../vsto/office-ui-customization.md).

## <a name="see-also"></a>Viz také:
- [Návod: Vytvoření prvního doplňku VSTO pro PowerPoint](../vsto/walkthrough-creating-your-first-vsto-add-in-for-powerpoint.md)
- [Začínáme s programováním doplňků VSTO](../vsto/getting-started-programming-vsto-add-ins.md)
- [Přehled &#40;vývoje řešení pro systém Office VSTO&#41;](../vsto/office-solutions-development-overview-vsto.md)
- [Architektura doplňků VSTO](../vsto/architecture-of-vsto-add-ins.md)
- [Postupy: Vytváření projektů Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md)
- [Programové doplňky VSTO](../vsto/programming-vsto-add-ins.md)
- [Psaní kódu v řešeních pro systém Office](../vsto/writing-code-in-office-solutions.md)
- [Sestavení primární spolupráce pro Office](../vsto/office-primary-interop-assemblies.md)
- [Přizpůsobení uživatelského rozhraní systému Office](../vsto/office-ui-customization.md)
- [PowerPoint 2010 ve vývoji pro Office](http://go.microsoft.com/fwlink/?LinkId=199015)
