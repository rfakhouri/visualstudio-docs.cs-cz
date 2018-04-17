---
title: Přístup k oblasti formuláře za běhu | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Inspectors [Office development in Visual Studio]
- Explorers [Office development in Visual Studio]
- form regions [Office development in Visual Studio], accessing at run time
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: e1a7d2ad69adff4462379f223f4f6bab397511d4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="accessing-a-form-region-at-run-time"></a>Přístup k oblasti formuláře za běhu


|Platí pro|  
|----------------|  
|Informace v tomto tématu se vztahují jenom na tyto typy projektů a verze Microsoft Office. Další informace najdete v tématu [dostupné funkce podle aplikace Office a typu projektu](../vsto/features-available-by-office-application-and-project-type.md).<br /><br /> **Typ projektu**<br /><br /> -Projekty doplňku VSTO<br /><br /> **Verze aplikace Microsoft Office**<br /><br /> -   [!INCLUDE[Outlook_14_short](../vsto/includes/outlook-14-short-md.md)]|  

 Použití `Globals` třídy oblasti formuláře přístup odkudkoli v rámci projektu aplikace Outlook. Další informace o `Globals` třídy najdete v tématu [globální přístup k objektům v projektech Office](../vsto/global-access-to-objects-in-office-projects.md).  

 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  

## <a name="accessing-form-regions-that-appear-in-a-specific-outlook-inspector-window"></a>Přístup k oblasti formuláře, které se zobrazují v okně kontroly konkrétní aplikace  
 Chcete-li získat přístup k všechny oblasti formuláře, které se zobrazují v konkrétní Kontrola aplikace Outlook, volejte `FormRegions` vlastnost `Globals` třídy a předat <xref:Microsoft.Office.Interop.Outlook.Inspector> objekt, který představuje funkci Kontrola.  

 Následující příklad načte kolekci oblastí formulářů, které se zobrazují v Inspector, který má právě fokus. Tento příklad následně přistupuje k oblasti formuláře v kolekci s názvem `formRegion1` a nastaví text, který se zobrazí v textovém poli na `Hello World`.  

 [!code-vb[Trin_Outlook_FR_Access#2](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Access_O12/ThisAddIn.vb#2)]
 [!code-csharp[Trin_Outlook_FR_Access#2](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Access_O12/ThisAddIn.cs#2)]  

## <a name="accessing-form-regions-that-appear-in-a-specific-outlook-explorer-window"></a>Přístup k oblasti formuláře, které se zobrazují v okně Průzkumníka konkrétní aplikace Outlook  
 Chcete-li získat přístup k všechny oblasti formuláře, které se zobrazují v konkrétní Explorer Outlook, volejte `FormRegions` vlastnost `Globals` třídy a předat <xref:Microsoft.Office.Interop.Outlook.Explorer> objekt, který reprezentuje Průzkumníku.  

 Následující příklad načte kolekci oblastí formulářů, které se zobrazují v Průzkumníku, který má právě fokus. Tento příklad následně přistupuje k oblasti formuláře v kolekci s názvem `formRegion1` a nastaví text, který se zobrazí v textovém poli na `Hello World`.  

 [!code-vb[Trin_Outlook_FR_Access#3](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Access_O12/ThisAddIn.vb#3)]
 [!code-csharp[Trin_Outlook_FR_Access#3](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Access_O12/ThisAddIn.cs#3)]  

## <a name="accessing-all-form-regions"></a>Přístup k všechny oblasti formuláře  
 Chcete-li získat přístup k všechny oblasti formuláře, které se zobrazují v všechny Průzkumníci a všechny kontroly, volejte `FormRegions` vlastnost `Globals` třída.  

 Následující příklad načte kolekci oblastí formulářů, které se zobrazují v všechny Průzkumníci a všechny kontroly. Tento příklad následně přistupuje k oblasti formuláře s názvem `formRegion1` a nastaví text, který se zobrazí v textovém poli na `Hello World`.  

 [!code-vb[Trin_Outlook_FR_Access#1](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Access_O12/ThisAddIn.vb#1)]
 [!code-csharp[Trin_Outlook_FR_Access#1](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Access_O12/ThisAddIn.cs#1)]  

## <a name="accessing-controls-on-a-form-region"></a>Přístup k ovládacím prvkům v oblasti formuláře  
 K řízení přístupu na oblasti formuláře pomocí `Globals` třídy, je třeba ovládací prvky přístupné kódu mimo souboru kódu oblasti formuláře.  

### <a name="form-regions-designed-in-the-form-region-designer"></a>Oblasti formuláře navržené v Návrháři oblasti formuláře  
 Pro jazyk C# změňte modifikátor každý ovládací prvek, který chcete získat přístup. To pokud chcete udělat, vyberte každý ovládací prvek v Návrháři oblasti formuláře a změňte **modifikátory** vlastnost **interní** nebo **veřejné** v **vlastnosti** okno. Například, pokud změníte **modifikátor** vlastnost `textBox1` k **interní**, dostanete `textBox1` zadáním `Globals.FormRegions.FormRegion1.textBox1`.  

 V jazyce Visual Basic není potřeba změnit modifikátor.  

### <a name="imported-form-regions"></a>Oblasti formuláře importované  
 Když importujete oblasti formuláře, který byl navržen v aplikaci Outlook, stane privátní modifikátor přístupu každý ovládací prvek v oblasti formuláře. Protože v Návrháři oblasti formuláře nelze použít k úpravě oblast importované formuláře, neexistuje žádný způsob, jak změnit Modifikátor ovládacího prvku v **vlastnosti** okno.  

 Pokud chcete povolit přístup k ovládacímu prvku z mimo souboru kódu oblasti formuláře, vytvořte vlastnost v souboru kódu oblasti formuláře vrátit tuto kontrolu.  

 Další informace o tom, jak vytvořit vlastnosti v jazyce C# najdete v tématu [postupy: deklarování a použití číst vlastnosti zápisu &#40;C&#35; Průvodce programováním&#41;](/dotnet/csharp/programming-guide/classes-and-structs/how-to-declare-and-use-read-write-properties).  

 Další informace o tom, jak vytvořit vlastnosti v jazyce Visual Basic najdete v tématu [postupy: vytvoření vlastnosti (Visual Basic)](/dotnet/visual-basic/programming-guide/language-features/procedures/how-to-create-a-property).  

## <a name="see-also"></a>Viz také  
 [Pokyny pro vytváření oblastí formulářů aplikace Outlook](../vsto/guidelines-for-creating-outlook-form-regions.md)   
 [Postupy: Návrh oblasti formuláře aplikace Outlook](../vsto/walkthrough-designing-an-outlook-form-region.md)   
 [Postupy: přidání oblasti formuláře do projektu doplňku aplikace Outlook](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md)   
 [Vlastní akce v oblastí formulářů aplikace Outlook](../vsto/custom-actions-in-outlook-form-regions.md)   
 [Přidružení oblasti formuláře k třídě zpráv aplikace Outlook](../vsto/associating-a-form-region-with-an-outlook-message-class.md)   
 [Návod: Import oblasti formuláře navržené v aplikaci Outlook](../vsto/walkthrough-importing-a-form-region-that-is-designed-in-outlook.md)   
 [Postupy: zabránění zobrazení oblasti formuláře aplikace Outlook](../vsto/how-to-prevent-outlook-from-displaying-a-form-region.md)   
 [Vytváření oblastí formulářů aplikace Outlook](../vsto/creating-outlook-form-regions.md)   
 [Přístup k pásu karet za běhu](../vsto/accessing-the-ribbon-at-run-time.md)  
