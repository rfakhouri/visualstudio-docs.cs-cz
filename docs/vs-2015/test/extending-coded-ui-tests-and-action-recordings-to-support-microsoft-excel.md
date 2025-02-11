---
title: Rozšiřování programových testů uživatelského rozhraní a záznamů akcí pro podporu Microsoft Excel | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-test
ms.topic: conceptual
ms.assetid: 6b0f72a4-70ca-4e55-b236-2ea1034fd8a7
caps.latest.revision: 32
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 6eb44970cc29198ad9044281e566727a64b893c8
ms.sourcegitcommit: 2da366ba9ad124366f6502927ecc720985fc2f9e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68871568"
---
# <a name="extending-coded-ui-tests-and-action-recordings-to-support-microsoft-excel"></a>Rozšiřování programových testů UI a záznamů akcí k podpoře Microsoft Excel
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Testovací rozhraní pro programové testy uživatelského rozhraní a záznamy akcí nepodporuje všechny možné uživatelské rozhraní. Nemusí podporovat konkrétní uživatelské rozhraní, které chcete testovat. Například nelze okamžitě vytvořit programový test uživatelského rozhraní nebo záznam akce pro [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] tabulku. Můžete však vytvořit vlastní rozšíření pro programový test uživatelského rozhraní, které bude podporovat vaše konkrétní uživatelské rozhraní, a využít tak rozšíření programového testu uživatelského rozhraní. Následující téma obsahuje příklad, jak rozšiřuje rámec na podporu vytváření programových testů uživatelského rozhraní a záznamů akcí pro [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)]. Další informace o podporovaných platformách naleznete v části [podporované konfigurace a platformy pro programové testy uživatelského rozhraní a záznamy akcí](../test/supported-configurations-and-platforms-for-coded-ui-tests-and-action-recordings.md).

 **Požadavky**

- Visual Studio Enterprise

  Tato část obsahuje rozšíření programového testu uživatelského rozhraní, které může nahrávat a přehrávat zpětných testů excelových listů. Jednotlivé části rozšíření jsou vysvětleny v této části a v komentářích kódu pro vývojáře, kteří chtějí vytvořit pouze takové rozšíření.

  ![Architektura testu uživatelského rozhraní](../test/media/ui-testarch.png "UI_TestArch") Přehled architektury

## <a name="download-the-sample"></a>Stažení ukázky
 Ukázka se skládá ze čtyř projektů v `CodedUIExtensibilitySample.sln` řešení:

- CodedUIextensibilitySample

- ExcelCodedUIAddInHelper

- ExcelUICommunicationHelper

- SampleTestProject

  Získejte ukázku z tohoto [příspěvku na blogu](http://go.microsoft.com/fwlink/?LinkID=185592).

> [!NOTE]
> Ukázka je určena pro použití v aplikaci Microsoft Excel 2010. Ukázka může pracovat s jinými verzemi aplikace Microsoft Excel, ale v současné době není podporována.

## <a name="details-about-the-sample"></a>Podrobnosti o ukázce
 Následující části obsahují informace o ukázce a její struktuře.

### <a name="microsoft-excel-add-in-excelcodeduiaddinhelper"></a>Doplněk pro Microsoft Excel: ExcelCodedUIAddinHelper
 Tento projekt obsahuje doplněk, který běží v procesu aplikace Excel. Stručný přehled projektu doplňku naleznete v tématu [vzorový doplněk Excelu pro programové testování uživatelského rozhraní](../test/sample-excel-add-in-for-coded-ui-testing.md) .

 Další informace najdete v tématu [Návod: Vytvoření prvního doplňku VSTO pro Excel](https://msdn.microsoft.com/library/a855e2be-3ecf-4112-a7f5-ec0f7fad3b5f)

### <a name="excel-ui-communication-exceluicommunicationhelper"></a>Komunikace uživatelského rozhraní Excelu: ExcelUIcommunicationHelper
 Tento projekt obsahuje `IExcelUICommunication` rozhraní a třídy informací, které slouží k předávání dat mezi rozhraním programového testování uživatelského rozhraní a Excelu. Další informace najdete v tématu [ukázka rozhraní Excel Communicator](../test/sample-excel-communicator-interface.md).

### <a name="coded-ui-test-extension-codeduiexentsibilitysample"></a>Rozšíření programového testu uživatelského rozhraní: CodedUIExentsibilitySample
 Tento projekt obsahuje vlastní třídy, které se používají v testech excelového listu. Kód pro každou z těchto tříd je poměrně samozřejmý. Poskytujeme ale krátký popis každé vlastní třídy. Další informace najdete v tématu [Ukázka rozšíření programového testu UI pro Excel](../test/sample-coded-ui-test-extension-for-excel.md).

### <a name="deploying-your-add-in-and-extension"></a>Nasazení doplňku a rozšíření
 Po vytvoření všech projektů a objektů spusťte zadaný `CopyDrop.bat` soubor jako správce. Tento soubor zkopíruje `ExcelCodedUIAddinHelper` soubory DLL a PDB do:

 "`%CommonProgramFiles(x86)%\Microsoft Shared\VSTT\<version number>\UITestExtensionPackages\*.*`", kde číslo verze může být 11,0, 12,0 atd. v závislosti na vaší verzi sady Visual Studio.

 Soubory DLL a PDB jsou zkopírovány do `"%ProgramFiles(x86)%\Microsoft Visual Studio <version number>\Common7\IDE\PrivateAssemblies”`. `ExcelUICommunicationHelper`

 Možná budete muset upravit přesné cesty kopírování, ale nevyžaduje se žádná další instalace. Na 64 počítači pomocí příkazového řádku 32 bitové Visual Studio Enterprise spusťte `CopyDrop.bat` soubor.

### <a name="testing-excel-with-the-sampletestproject"></a>Testování aplikace Excel pomocí SampleTestProject
 Test můžete spustit v poskytnutém testovacím projektu, který používá konkrétní verzi aplikace Excel, kterou nesmíte mít, nebo vytvořte vlastní testovací projekt a zaznamenejte vlastní test. Další informace naleznete v tématu [vytváření programových testů uživatelského rozhraní](../test/use-ui-automation-to-test-your-code.md#VerifyingCodeUsingCUITCreate).

## <a name="see-also"></a>Viz také:

- <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestPropertyProvider>
- <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyElement>
- [UITestActionFilter](/previous-versions/visualstudio/visual-studio-2012/dd985757(v=vs.110))
- <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITestExtensionPackage>
- [Použití automatizace uživatelského rozhraní k testování kódu](../test/use-ui-automation-to-test-your-code.md)
- [Doporučené postupy pro programové testy UI](../test/best-practices-for-coded-ui-tests.md)
- [Podporované konfigurace a platformy pro programové testy uživatelského rozhraní a zaznamenávání akcí](../test/supported-configurations-and-platforms-for-coded-ui-tests-and-action-recordings.md)
