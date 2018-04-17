---
title: 'Postupy: procházení databázových záznamů na listu | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- databases [Office development in Visual Studio], scrolling records
- records [Office development in Visual Studio], scrolling
- data [Office development in Visual Studio], scrolling database records
- worksheets [Office development in Visual Studio], scrolling records
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: a092cec68e59914b498ab3b935f58b6ef0c37f05
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-scroll-through-database-records-in-a-worksheet"></a>Postupy: Procházení databázových záznamů na listu
  Následující postup ukazuje, jak používat návrháře zobrazíte jediné pole z tabulky databáze v tabulku aplikace Microsoft Office Excel s ovládacími prvky, které umožňují koncovým uživatelům procházet všechny záznamy.  
  
 Můžete použít Návrháře jenom v projektech na úrovni dokumentu. Můžete však také přidání ovládacích prvků a navázat je dat prostřednictvím kódu programu za běhu. Další informace najdete v tématu [návod: jednoduché datové vazby v VSTO doplňku projektu](../vsto/walkthrough-simple-data-binding-in-vsto-add-in-project.md).  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
### <a name="to-scroll-through-database-records-in-a-worksheet"></a>Procházení databázových záznamů na listu  
  
1.  Otevřete projekt aplikace Excel v sadě Visual Studio.  
  
2.  Otevřete **zdroje dat** okno a vytvořte zdroj dat z databáze. Další informace najdete v tématu [přidat nová připojení](../data-tools/add-new-connections.md).  
  
3.  Rozbalte tabulka, která obsahuje data, která chcete zobrazit a vybrat konkrétní sloupec.  
  
4.  Otevře se seznam ovládací prvky a vyberte **NamedRange**.  
  
5.  Přetáhněte <xref:Microsoft.Office.Tools.Excel.NamedRange> na buňky, kam chcete data zobrazí ovládací prvek.  
  
6.  Z **Windows Forms** kartě **sada nástrojů**, přidejte <xref:System.Windows.Forms.BindingNavigator> řízení do listu a nastavit ovládací prvky, které chcete použít. Další informace najdete v tématu [BindingNavigator – Přehled ovládacího prvku &#40;Windows Forms&#41;](/dotnet/framework/winforms/controls/bindingnavigator-control-overview-windows-forms).  
  
## <a name="see-also"></a>Viz také  
 [Vazba dat k ovládacím prvkům v řešeních pro systém Office](../vsto/binding-data-to-controls-in-office-solutions.md)  
  
  