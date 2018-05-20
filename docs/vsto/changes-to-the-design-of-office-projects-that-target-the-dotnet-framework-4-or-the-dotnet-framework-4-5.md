---
title: Změny v návrhu projektů Office cílených rozhraní .NET Framework
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office development in Visual Studio, what's new
- what's new [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 84a755d420da494f77397dbad445b7a649f0c943
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/17/2018
---
# <a name="changes-to-the-design-of-office-projects-that-target-the-net-framework-4-or-the-net-framework-45"></a>Změny v návrhu projektů Office cílených na rozhraní .NET Framework 4 nebo .NET Framework 4.5
  Počínaje [!INCLUDE[vs_dev10_long](../sharepoint/includes/vs-dev10-long-md.md)], Visual Studio zavedená některé změny v návrhu projektů Office cílených [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo novější. Pokud jste obeznámeni s projekty Office v předchozích verzích sady Visual Studio, byste měli mít věděli o těchto změnách před vyvíjet projektech Office cílených rozhraní .NET Framework 4.0 nebo novější verzí. Ve výchozím nastavení všechny projekty, které vytvoříte pomocí sady Visual Studio 2013 nebo novější cílové rozhraní .NET Framework 4.0 nebo novější.  
  
 Následující části popisují těchto změn v návrhu projektů Office.  
  
## <a name="understand-the-interface-based-design-of-the-visual-studio-2010-tools-for-office-runtime"></a>Porozumět návrhu na základě rozhraní Visual Studio 2010 Tools for Office runtime  
 Když vyvíjíte projekt Office, která je cílena [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo novější, jsou většinu typů, které používáte ve Visual Studio 2010 Tools pro systém Office runtime rozhraní. Toto je hlavní změny z předchozích verzí [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)], kde jsou tyto typy třídy. Například pokud cílíte [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo novější, <xref:Microsoft.Office.Tools.Excel.Worksheet> a <xref:Microsoft.Office.Tools.Word.Document> typy jsou rozhraní namísto třídy. Další informace najdete v tématu [Visual Studio Tools for Office runtime přehled](../vsto/visual-studio-tools-for-office-runtime-overview.md).  
  
 Pro všechny typy, které může vytvořit instanci přímo v předchozích verzích [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)], teď použít metody `Globals.Factory` objekt, který chcete získat instancí těchto typů. Pro příklad, jak získat objekt, který implementuje <xref:Microsoft.Office.Tools.Excel.SmartTag> rozhraní, použijte `Globals.Factory.CreateSmartTag` metoda. Další informace naleznete v následujících tématech:  
  
-   [Aktualizace projektů Excel a Word, které při migraci na rozhraní .NET Framework 4 nebo .NET Framework 4.5](../vsto/updating-excel-and-word-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md)  
  
-   [Aktualizace vlastních nastavení pásu karet v projektech Office při migraci na rozhraní .NET Framework 4 nebo .NET Framework 4.5](../vsto/updating-ribbon-customizations-in-office-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md)  
  
-   [Aktualizace oblastí formulářů v projektech Outlook při migraci na rozhraní .NET Framework 4 nebo .NET Framework 4.5](../vsto/updating-form-regions-in-outlook-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md)  
  
### <a name="new-base-classes-in-office-projects"></a>Nové základní třídy v projektech pro systém Office  
 Nový návrh založené na rozhraní Visual Studio 2010 Tools for Office runtime ovlivňuje generované třídy v projektech Office, jako například `ThisDocument`, `ThisWorkbook`, a `ThisAddIn`. V projektech Office cílených rozhraní .NET Framework 3.5 a předchozích verzích rozhraní, tyto generované třídy odvozeny od třídy v [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] například `Microsoft.Office.Tools.Word.Document`, `Microsoft.Office.Tools.Excel.Worksheet`, a `Microsoft.Office.Tools.AddIn`. V projektech cílených [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo novější, tyto [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] třídy jsou nyní rozhraní. Proto můžete generované třídy v projektech Office již odvozeny jejich provádění z nich. Místo toho generované třídy jsou odvozeny od nové základní třídy, jako <xref:Microsoft.Office.Tools.Word.DocumentBase>, <xref:Microsoft.Office.Tools.Excel.WorksheetBase>, a <xref:Microsoft.Office.Tools.AddInBase>. Další informace najdete v tématu [doplňků Program VSTO](../vsto/programming-vsto-add-ins.md) a [programu úpravy na úrovni dokumentů](../vsto/programming-document-level-customizations.md).  
  
 Základní třídy, které nejsou součástí [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] redistributable. Místo toho jsou definovány v sestaveních nástroje, které jsou součástí sady Visual Studio. Těchto sestavení se zkopírují do výstupní složky při sestavování projektů Office a musí být nasazený s vaším řešením. Další informace o sestavení nástroje najdete v tématu [sestavení sady Visual Studio Tools for Office runtime](../vsto/assemblies-in-the-visual-studio-tools-for-office-runtime.md).  
  
## <a name="breaking-changes-in-office-projects-that-are-retargeted-to-the-net-framework-4"></a>Nejnovější změny v projektech Office, které jsou změnit cíl na rozhraní .NET Framework 4 necílené  
 Následující tabulka uvádí hlavní nejnovějších změn v projektech Office, které jsou změnit cíl na necílené se můžete setkat [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo novější. Další podrobnosti najdete v tématu [řešení Office migraci na rozhraní .NET Framework 4 nebo novější](../vsto/migrating-office-solutions-to-the-dotnet-framework-4-or-later.md).  
  
|Nejnovější změny|Důsledkem|  
|---------------------|-----------------|  
|<xref:System.Security.SecurityTransparentAttribute> Je už používá nebo v projektech pro systém Office podporované.|Tento atribut je nutné odebrat ze souboru AssemblyInfo kódu v projektech Office, které upgradujete z Visual Studio 2008. Další informace najdete v tématu [požadované změny pro spouštění projektů Office migrovaných na rozhraní .NET Framework 4 nebo .NET Framework 4.5](../vsto/required-changes-to-run-office-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md).|  
|**ExcelLocale1033Attribute** se už používá nebo je podporováno v projekty aplikace Excel.|Je nutné odebrat tento atribut z *AssemblyInfo* souboru kódu v projekty aplikace Excel. Další informace najdete v tématu [aktualizace Excelu a Wordu projekty, které při migraci na rozhraní .NET Framework 4 nebo .NET Framework 4.5](../vsto/updating-excel-and-word-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md).|  
|Programovací model **pásu karet (vizuálního návrháře)** došlo ke změně položky projektu.|V projektu, musíte upravit soubor kódu pro všechny položky pásu karet. Také je třeba upravit kód, který vytvoří instanci ovládacích prvků pásu karet za běhu, zpracovává události pásu karet nebo nastaví pozici součásti pásu karet prostřednictvím kódu programu. Další informace najdete v tématu [přizpůsobení aktualizace pásu karet v projektech Office při migraci na rozhraní .NET Framework 4 nebo .NET Framework 4.5](../vsto/updating-ribbon-customizations-in-office-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md).|  
|Došlo ke změně programovací model oblastí formulářů aplikace Outlook.|V projektu a kód, který vytvoří instanci určité třídy oblasti formuláře za běhu, musíte upravit soubor kódu pro všechny oblasti formuláře. Další informace najdete v tématu [aktualizace oblastí formulářů v projektech Outlook při migraci na rozhraní .NET Framework 4 nebo .NET Framework 4.5](../vsto/updating-form-regions-in-outlook-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md).|  
|Došlo ke změně programovací model pro inteligentních značek v projektech Excelu a Wordu. Inteligentní značky nepoužívají v [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)] a [!INCLUDE[Word_14_short](../vsto/includes/word-14-short-md.md)].|Pokud řešení používá inteligentních značek, dojde k chybám při sestavování projektu. Protože inteligentní značky nepoužívají v [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)] a [!INCLUDE[Word_14_short](../vsto/includes/word-14-short-md.md)], než budete testovat a ladění řešení v, musíte odebrat značek [!INCLUDE[vs_dev12](../vsto/includes/vs-dev12-md.md)] nebo novější.|  
|Syntaxe `GetVstoObject` a `HasVstoObject` došlo ke změně metody|Je nutné předat `Globals.Factory` objekt, který chcete tyto metody při přístupu na nativní objekty z primární spolupracující sestavení (PIA) nebo dostanete tyto metody na objekt, který je vrácený `Globals.Factory` vlastnost ve vašem projektu. Další informace najdete v tématu [aktualizace Excelu a Wordu projekty, které při migraci na rozhraní .NET Framework 4 nebo .NET Framework 4.5](../vsto/updating-excel-and-word-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md).|  
|Události obsahu ovládací prvky aplikace Word jsou přidruženy k nové delegáti.|Je třeba upravit kód, který zpracovává události obsahu ovládací prvky aplikace Word k určení nového delegáti. Další informace najdete v tématu [aktualizace Excelu a Wordu projekty, které při migraci na rozhraní .NET Framework 4 nebo .NET Framework 4.5](../vsto/updating-excel-and-word-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md).|  
|`OLEObject` a `OLEControl` přejmenovaná třídy.|Je třeba upravit kód, který používá instancemi těchto tříd používat <xref:Microsoft.Office.Tools.Excel.ControlSite> nebo <xref:Microsoft.Office.Tools.Word.ControlSite> objekty místo. Další informace najdete v tématu [aktualizace Excelu a Wordu projekty, které při migraci na rozhraní .NET Framework 4 nebo .NET Framework 4.5](../vsto/updating-excel-and-word-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md).|  
|Hostování tříd položek, jako například `ThisWorkbook`, `Sheet` *n*, `ThisDocument`, a `ThisAddIn`, nadále poskytovat žádné `Dispose` metoda, která můžete přepsat.|Je třeba přesunout žádný kód `Dispose` metoda přepsání nastavení za účelem `Shutdown` obslužné rutiny událostí v hostiteli třída položky, například `ThisAddIn_Shutdown`a odeberte `Dispose` metoda přepsání z vaší třídy položky hostitele.|  
  
## <a name="see-also"></a>Viz také  
 [Migrace řešení Office na rozhraní .NET Framework 4 nebo novější](../vsto/migrating-office-solutions-to-the-dotnet-framework-4-or-later.md)   
 [Co je nového v vývoj pro Office](http://msdn.microsoft.com/en-us/bf054af2-c896-4723-aa15-6381145b14bb)   
 [Visual Studio Tools for Office runtime – přehled](../vsto/visual-studio-tools-for-office-runtime-overview.md)  
  
  