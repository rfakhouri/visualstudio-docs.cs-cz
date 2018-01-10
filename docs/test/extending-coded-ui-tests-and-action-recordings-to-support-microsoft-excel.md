---
title: "Rozšiřování programových testů UI a záznamů akcí k podpoře Microsoft Excel | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.author: gewarren
manager: ghogen
ms.workload: multiple
author: gewarren
ms.openlocfilehash: ae08752c7687844fbe620bf6314496b474b6e915
ms.sourcegitcommit: 7ae502c5767a34dc35e760ff02032f4902c7c02b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/09/2018
---
# <a name="extending-coded-ui-tests-and-action-recordings-to-support-microsoft-excel"></a>Rozšiřování programových testů UI a záznamů akcí k podpoře Microsoft Excel
Testování framework pro programové testy uživatelského rozhraní a zaznamenávání akcí nepodporuje všechny možné uživatelské rozhraní. Nepodporuje specifické uživatelské rozhraní, který chcete otestovat. Například nelze vytvořit okamžitě programového testu UI nebo záznamu pro akce [!INCLUDE[ofprexcel](../test/includes/ofprexcel_md.md)] tabulky. Můžete však vytvořit vlastní rozšíření programové framework testu uživatelského rozhraní, která bude podporovat vaše specifické uživatelské rozhraní a využívají k rozšiřitelnosti rozhraní programových testů uživatelského rozhraní. V následujícím tématu je uveden příklad toho, jak rozšířit rozhraní pro podporu vytváření programové testy uživatelského rozhraní a zaznamenávání akcí pro [!INCLUDE[ofprexcel](../test/includes/ofprexcel_md.md)]. Další informace o platformy, které jsou podporovány, naleznete v části [podporované konfigurace a platformy pro programové testy uživatelského rozhraní a zaznamenávání akcí](../test/supported-configurations-and-platforms-for-coded-ui-tests-and-action-recordings.md).  
  
 **Požadavky**  
  
-   Visual Studio Enterprise  
  
 Tato část představuje rozšíření programového testu uživatelského rozhraní, můžete záznam a přehrávání testů sešitů aplikace Excel. Jednotlivých součástí rozšíření je vysvětleno v této části a komentáře kódu pro vývojáře, kteří chtějí vytvořit pouze takové rozšíření.  
  
 ![Architektura testu uživatelského rozhraní](../test/media/ui_testarch.png "UI_TestArch")  
Přehled architektury  
  
## <a name="download-the-sample"></a>Stažení ukázky  
 Ukázkový soubor obsahuje čtyři projektů `CodedUIExtensibilitySample.sln` řešení:  
  
-   CodedUIextensibilitySample  
  
-   ExcelCodedUIAddInHelper  
  
-   ExcelUICommunicationHelper  
  
-   SampleTestProject  
  
 Získání vzorku z tohoto [příspěvku na blogu](http://go.microsoft.com/fwlink/?LinkID=185592).  
  
> [!NOTE]
>  Ukázka je určena pro použití s Microsoft Excel 2010. Ukázka může pracovat s další verze aplikace Microsoft Excel, ale není aktuálně podporováno.  
  
## <a name="details-about-the-sample"></a>Podrobnosti o vzorku  
 Následující části obsahují informace o vzorku a jeho strukturu.  
  
### <a name="microsoft-excel-add-in-excelcodeduiaddinhelper"></a>Doplněk Microsoft Excelu: ExcelCodedUIAddinHelper  
 Tento projekt obsahuje doplněk, který běží v procesu aplikace Excel. V tématu [doplněk ukázkové aplikace Excel pro programové testování uživatelského rozhraní](../test/sample-excel-add-in-for-coded-ui-testing.md) stručný přehled projektu doplňku.  
  
 Další informace najdete v tématu [návod: Add-in vytváření vaše první VSTO pro Excel](http://msdn.microsoft.com/Library/a855e2be-3ecf-4112-a7f5-ec0f7fad3b5f).  
  
### <a name="excel-ui-communication-exceluicommunicationhelper"></a>Komunikace uživatelského rozhraní aplikace Excel: ExcelUIcommunicationHelper  
 Tento projekt obsahuje `IExcelUICommunication` rozhraní a třídy informace, které se používají k předávání dat mezi programového Framework testování uživatelského rozhraní a Excel. Další informace najdete v tématu [ukázka rozhraní Komunikátoru Excel](../test/sample-excel-communicator-interface.md).  
  
### <a name="coded-ui-test-extension-codeduiexentsibilitysample"></a>Rozšíření programového testu UI: CodedUIExentsibilitySample  
 Tento projekt obsahuje vlastní třídy, které se používají v testech listu aplikace Excel. Kód pro každé z těchto tříd je docela není potřeba vysvětlovat. Ale poskytujeme krátký popis jednotlivých vlastní třídy. Další informace najdete v tématu [ukázka programového uživatelského rozhraní Test rozšíření pro aplikaci Excel](../test/sample-coded-ui-test-extension-for-excel.md).  
  
### <a name="deploying-your-add-in-and-extension"></a>Nasazení vaší Add-in a rozšíření  
 Po vytvoření všechny projekty a objekty, spusťte poskytnutého `CopyDrop.bat` soubor jako správce. Tento soubor se zkopíruje `ExcelCodedUIAddinHelper` DLL a PDB soubory:  
  
 "`%CommonProgramFiles(x86)%\Microsoft Shared\VSTT\<version number>\UITestExtensionPackages\*.*`", kdy se číslo verze může být 11.0, 12,0 atd podle vaší verze sady Visual Studio.  
  
 `ExcelUICommunicationHelper` DLL a PDB soubory se zkopírují do `"%ProgramFiles(x86)%\Microsoft Visual Studio <version number>\Common7\IDE\PrivateAssemblies"`.  
  
 Možná budete muset upravit přesná kopie cesty, ale je nutná žádná další instalace. Na 64bitový počítač, použijte ke spuštění příkazového řádku Visual Studio Enterprise 32bitová verze `CopyDrop.bat` souboru.  
  
### <a name="testing-excel-with-the-sampletestproject"></a>Testování aplikace Excel pomocí SampleTestProject aplikace  
 Spusťte test v zadané testovacího projektu, který používá určitou verzi aplikace Excel, nemusí mít, nebo vytvořit vlastní testovacího projektu a záznam vlastní test. Další informace najdete v tématu [vytváření programových testů uživatelského rozhraní](../test/use-ui-automation-to-test-your-code.md#VerifyingCodeUsingCUITCreate).  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestPropertyProvider>   
 <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyElement>   
 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter>   
 <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITestExtensionPackage>   
 [Použití automatizace uživatelského rozhraní k testování kódu](../test/use-ui-automation-to-test-your-code.md)   
 [Osvědčené postupy pro programové testy uživatelského rozhraní](../test/best-practices-for-coded-ui-tests.md)   
 [Podporované konfigurace a platformy pro programové testy uživatelského rozhraní a zaznamenávání akcí](../test/supported-configurations-and-platforms-for-coded-ui-tests-and-action-recordings.md)
