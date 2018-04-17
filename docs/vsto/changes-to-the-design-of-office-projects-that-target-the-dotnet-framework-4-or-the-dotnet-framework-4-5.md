---
title: Změny v návrhu projektů Office cílených rozhraní .NET Framework 4 nebo .NET Framework 4.5 | Microsoft Docs
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
ms.openlocfilehash: 2c6f050e98665d55c7a64261131cef7ba31c684f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="changes-to-the-design-of-office-projects-that-target-the-net-framework-4-or-the-net-framework-45"></a>Změny v návrhu projektů Office cílených na rozhraní .NET Framework 4 nebo .NET Framework 4.5
  Počínaje [!INCLUDE[vs_dev10_long](../sharepoint/includes/vs-dev10-long-md.md)], Visual Studio zavedená některé změny v návrhu projektů Office cílených [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo novější. Pokud jste obeznámeni s projekty Office v předchozích verzích sady Visual Studio, byste měli mít věděli o těchto změnách před vyvíjet projektech Office cílených rozhraní .NET Framework 4.0 nebo novější verzí. Ve výchozím nastavení všechny projekty, které vytvoříte pomocí sady Visual Studio 2013 nebo novější cílové rozhraní .NET Framework 4.0 nebo novější.  
  
 Následující části popisují těchto změn v návrhu projektů Office.  
  
## <a name="understanding-the-interface-based-design-of-the-visual-studio-2010-tools-for-office-runtime"></a>Princip návrhu na základě rozhraní nástroje sady Visual Studio 2010 Tools for Office Runtime  
 Když vyvíjíte projekt Office, která je cílena [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo novější, jsou většinu typů, které používáte ve Visual Studio 2010 Tools for Office Runtime rozhraní. Toto je hlavní změny z předchozích verzí [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)], kde jsou tyto typy třídy. Například pokud cílíte [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo novější, <xref:Microsoft.Office.Tools.Excel.Worksheet> a <xref:Microsoft.Office.Tools.Word.Document> typy jsou rozhraní namísto třídy. Další informace najdete v tématu [Visual Studio Tools for Office Runtime přehled](../vsto/visual-studio-tools-for-office-runtime-overview.md).  
  
 Pro všechny typy, které může vytvořit instanci přímo v předchozích verzích [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)], teď použít metody objektu Globals.Factory získat instance těchto typů. Pro příklad, jak získat objekt, který implementuje <xref:Microsoft.Office.Tools.Excel.SmartTag> rozhraní, použijte metodu Globals.Factory.CreateSmartTag. Další informace naleznete v následujících tématech:  
  
-   [Aktualizace projektů Excel a Word při migraci na rozhraní .NET Framework 4 nebo .NET Framework 4.5](../vsto/updating-excel-and-word-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md)  
  
-   [Aktualizace vlastních nastavení pásu karet v projektech Office při migraci na rozhraní .NET Framework 4 nebo .NET Framework 4.5](../vsto/updating-ribbon-customizations-in-office-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md)  
  
-   [Aktualizace oblastí formulářů v projektech Outlook při migraci na rozhraní .NET Framework 4 nebo .NET Framework 4.5](../vsto/updating-form-regions-in-outlook-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md)  
  
### <a name="new-base-classes-in-office-projects"></a>Nové základní třídy v projektech pro systém Office  
 Nový návrh založené na rozhraní Visual Studio 2010 Tools for Office Runtime ovlivňuje generované třídy v projektech Office, jako například `ThisDocument`, `ThisWorkbook`, a `ThisAddIn`. V projektech Office cílených rozhraní .NET Framework 3.5 a předchozích verzích rozhraní, tyto generované třídy odvozeny od třídy v [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] například Microsoft.Office.Tools.Word.Document, Microsoft.Office.Tools.Excel.Worksheet, a Microsoft.Office.Tools.AddIn. V projektech cílených [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo novější, tyto [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] třídy jsou nyní rozhraní. Proto můžete generované třídy v projektech Office již odvozeny jejich provádění z nich. Místo toho generované třídy jsou odvozeny od nové základní třídy, jako <xref:Microsoft.Office.Tools.Word.DocumentBase>, <xref:Microsoft.Office.Tools.Excel.WorksheetBase>, a <xref:Microsoft.Office.Tools.AddInBase>. Další informace najdete v tématu [programování doplňků VSTO](../vsto/programming-vsto-add-ins.md) a [programování přizpůsobení na úrovni dokumentu](../vsto/programming-document-level-customizations.md).  
  
 Základní třídy, které nejsou součástí [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] redistributable. Místo toho jsou definovány v sestaveních nástroje, které jsou součástí sady Visual Studio. Těchto sestavení se zkopírují do výstupní složky při sestavování projektů Office a musí být nasazený s vaším řešením. Další informace o sestavení nástroje najdete v tématu [sestavení sady Visual Studio Tools for Office Runtime](../vsto/assemblies-in-the-visual-studio-tools-for-office-runtime.md).  
  
## <a name="breaking-changes-in-office-projects-that-are-retargeted-to-the-net-framework-4"></a>Nejnovější změny v projektech Office, které jsou změnit cíl na rozhraní .NET Framework 4 Necílené  
 Následující tabulka uvádí hlavní nejnovějších změn v projektech Office, které jsou změnit cíl na necílené se můžete setkat [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo novější. Další podrobnosti najdete v tématu [migrace řešení pro systém Office na rozhraní .NET Framework 4 nebo novější](../vsto/migrating-office-solutions-to-the-dotnet-framework-4-or-later.md).  
  
|Nejnovější změny|Důsledkem|  
|---------------------|-----------------|  
|<xref:System.Security.SecurityTransparentAttribute> Je už používá nebo v projektech pro systém Office podporované.|Tento atribut je nutné odebrat ze souboru AssemblyInfo kódu v projektech Office, které upgradujete z Visual Studio 2008. Další informace najdete v tématu [požadované změny pro spouštění projektů Office, které při migraci na rozhraní .NET Framework 4 nebo .NET Framework 4.5](../vsto/required-changes-to-run-office-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md).|  
|ExcelLocale1033Attribute se už používá nebo podporováno v projekty aplikace Excel.|Tento atribut je nutné odebrat ze souboru AssemblyInfo kódu v projekty aplikace Excel. Další informace najdete v tématu [aktualizace projektů Excel a Word, při migraci na rozhraní .NET Framework 4 nebo .NET Framework 4.5](../vsto/updating-excel-and-word-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md).|  
|Programovací model **pásu karet (vizuálního návrháře)** došlo ke změně položky projektu.|V projektu, musíte upravit soubor kódu pro všechny položky pásu karet. Také je třeba upravit kód, který vytvoří ovládacích prvků pásu karet za běhu, zpracovává události pásu karet nebo nastaví pozici součásti pásu karet prostřednictvím kódu programu. Další informace najdete v tématu [aktualizace vlastních nastavení pásu karet v Office projekty, že při migraci na rozhraní .NET Framework 4 nebo .NET Framework 4.5](../vsto/updating-ribbon-customizations-in-office-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md).|  
|Došlo ke změně programovací model oblastí formulářů aplikace Outlook.|V projektu a kód, který vytvoří instanci určité třídy oblasti formuláře za běhu, musíte upravit soubor kódu pro všechny oblasti formuláře. Další informace najdete v tématu [aktualizace oblastí formulářů v aplikaci Outlook projekty, že při migraci na rozhraní .NET Framework 4 nebo .NET Framework 4.5](../vsto/updating-form-regions-in-outlook-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md).|  
|Došlo ke změně programovací model pro inteligentních značek v projektech Excelu a Wordu. Inteligentní značky nepoužívají v [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)] a [!INCLUDE[Word_14_short](../vsto/includes/word-14-short-md.md)].|Pokud řešení používá inteligentních značek, dojde k chybám při sestavování projektu. Protože inteligentní značky nepoužívají v [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)] a [!INCLUDE[Word_14_short](../vsto/includes/word-14-short-md.md)], než budete testovat a ladění řešení v, musíte odebrat značek [!INCLUDE[vs_dev12](../vsto/includes/vs-dev12-md.md)] nebo novější.|  
|Došlo ke změně syntaxe getvstoobject – a hasvstoobject – metody|Při přístupu na nativní objekty z primární spolupracující sestavení (PIA) nebo dostanete tyto metody na objekt, který je vrácen vlastností Globals.Factory ve vašem projektu, je nutné předat objekt Globals.Factory do těchto metod. Další informace najdete v tématu [aktualizace projektů Excel a Word, při migraci na rozhraní .NET Framework 4 nebo .NET Framework 4.5](../vsto/updating-excel-and-word-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md).|  
|Události obsahu ovládací prvky aplikace Word jsou přidruženy k nové delegáti.|Je třeba upravit kód, který zpracovává události obsahu ovládací prvky aplikace Word k určení nového delegáti. Další informace najdete v tématu [aktualizace projektů Excel a Word, při migraci na rozhraní .NET Framework 4 nebo .NET Framework 4.5](../vsto/updating-excel-and-word-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md).|  
|Objekt OLE a OLEControl třídy byly přejmenovány.|Je třeba upravit kód, který používá instancemi těchto tříd používat <xref:Microsoft.Office.Tools.Excel.ControlSite> nebo <xref:Microsoft.Office.Tools.Word.ControlSite> objekty místo. Další informace najdete v tématu [aktualizace projektů Excel a Word, při migraci na rozhraní .NET Framework 4 nebo .NET Framework 4.5](../vsto/updating-excel-and-word-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md).|  
|Hostování tříd položek, jako například `ThisWorkbook`, `Sheet` *n*, `ThisDocument`, a `ThisAddIn`, nadále poskytovat žádné metody Dispose, které můžete přepsat.|Musíte přesunout žádný kód v přepsání metody Dispose k obslužné rutině událostí vypnutí ve třídě hostitele položky, například `ThisAddIn_Shutdown`a odeberte přepsání metody Dispose z vaší třídy položky hostitele.|  
  
## <a name="see-also"></a>Viz také  
 [Migrace řešení Office na rozhraní .NET Framework 4 nebo novější](../vsto/migrating-office-solutions-to-the-dotnet-framework-4-or-later.md)   
 [Co je nového v vývoj pro Office](http://msdn.microsoft.com/en-us/bf054af2-c896-4723-aa15-6381145b14bb)   
 [Přehled nástrojů Visual Studio Tools for Office runtime](../vsto/visual-studio-tools-for-office-runtime-overview.md)  
  
  