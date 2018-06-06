---
title: Visual Studio Tools for Office runtime – přehled
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office runtime [Office development in Visual Studio], about Office runtime
- VSTOLoader.dll
- runtime loader [Office development in Visual Studio]
- Office runtime [Office development in Visual Studio], assemblies
- Office runtime [Office development in Visual Studio]
- runtime [Office development in Visual Studio], assemblies
- vstoee.dll
- Visual Studio Tools for Office runtime
- Office solutions [Office development in Visual Studio], runtime
- solutions [Office development in Visual Studio], runtime
- versions [Office development in Visual Studio], runtime
- assemblies [Office development in Visual Studio], runtime
- runtime [Office development in Visual Studio], about VSTO runtime
- solution loader [Office development in Visual Studio]
- runtime [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: c0bb3c800aece9531d6fe90ba04b9c99a0b4bd69
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/05/2018
ms.locfileid: "34767800"
---
# <a name="visual-studio-tools-for-office-runtime-overview"></a>Visual Studio Tools for Office runtime – přehled
  Ke spuštění řešení, které jsou vytvořené pomocí nástroje Microsoft Office developer tools v sadě Visual Studio, Visual Studio 2010 Tools for Office runtime musí nainstalovat do počítačů koncových uživatelů. Další informace najdete v tématu [postupy: instalace sady Visual Studio Tools for Office runtime redistributable](../vsto/how-to-install-the-visual-studio-tools-for-office-runtime-redistributable.md). Visual Studio 2010 Tools for Office runtime obsahuje dvě hlavní součásti:  
  
-   Rozšíření Office pro rozhraní .NET Framework. Tyto součásti jsou spravovaná sestavení, která poskytují komunikační vrstvu mezi vaším řešením a aplikací Microsoft Office. Další informace najdete v tématu [porozumět Office rozšíření pro rozhraní .NET Framework](#officeextensions).  
  
-   Zavaděč řešení pro Office. Tato součást je sada nespravovaných knihoven DLL, pomocí nichž aplikace Office zavádějí modul runtime a vaše řešení. Další informace najdete v tématu [pochopit zavaděč řešení Office](#UnmanagedLoader).  
  
 K dispozici je několik různých možností, jak nainstalovat modul runtime. V závislosti na konfiguraci počítače jsou při instalaci modulu runtime nainstalovány jeho různé součásti. Další informace najdete v tématu [Visual Studio Tools for Office runtime instalace scénáře](../vsto/visual-studio-tools-for-office-runtime-installation-scenarios.md).  
  
##  <a name="officeextensions"></a> Porozumět Office rozšíření pro rozhraní .NET Framework  
 Visual Studio 2010 Tools for Office runtime zahrnuje Office rozšíření pro rozhraní .NET Framework 3.5 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] a novější. Řešení, která cílí na jednotlivé verze rozhraní .NET Framework, používají příslušné rozšíření pro danou verzi.  
  
 Tato rozšíření jsou tvořena sestaveními, pomocí nichž mohou vaše řešení automatizovat a rozšířit aplikace Office. Když vytvoříte projekt pro Office, sada Visual Studio automaticky přidá odkazy na sestavení, která se používají pro zvolený typ projektu a cílové rozhraní .NET Framework projektu. Další informace o sestavení v Office rozšíření najdete v tématu [sestavení sady Visual Studio Tools for Office runtime](../vsto/assemblies-in-the-visual-studio-tools-for-office-runtime.md).  
  
### <a name="design-differences-in-the-office-extensions"></a>Návrh rozdíly v rozšíření Office  
 Většina typů, které můžete používat v rozšířeních Office pro .NET Framework 3.5, jsou třídy. Jedná se o stejné třídy, které byly zahrnuté v předchozích verzích [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]. Naproti tomu většinu typů, které můžete použít v Office rozšíření pro [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo jsou novější rozhraní. Například pokud cílíte [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo novější, <xref:Microsoft.Office.Tools.Excel.Worksheet> a <xref:Microsoft.Office.Tools.Word.Document> typy jsou rozhraní namísto třídy.  
  
 Ve většině případů kód, který vytváříte v řešeních pro systém Office je stejný, ať řešení cílí na rozhraní .NET Framework 3.5 nebo [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)]. Při cílení na různé verze rozhraní .NET Framework ale některé funkce vyžadují odlišný kód. Další informace najdete v tématu [řešení Office migraci na rozhraní .NET Framework 4 nebo novější](../vsto/migrating-office-solutions-to-the-dotnet-framework-4-or-later.md).  
  
### <a name="interfaces-in-the-office-extensions-for-the-net-framework-4-or-later"></a>Rozhraní rozšíření Office pro rozhraní .NET Framework 4 nebo novější  
 Většina rozhraní v Office rozšíření pro [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo novější není určeno k implementaci pomocí uživatelského kódu. Pouze rozhraní můžete implementovat přímo mít názvy, které začínají písmenem **I**, jako například <xref:Microsoft.Office.Tools.Excel.ISmartTagExtension>.  
  
 Všechna rozhraní, které nemají na začátku písmeno **I** interně implementované Visual Studio 2010 Tools for Office runtime, a tato rozhraní může v budoucích verzích změnit. K vytváření objektů, které implementují tato rozhraní, použít metody poskytované `Globals.Factory` objektu ve vašem projektu. Pro příklad, jak získat objekt, který implementuje <xref:Microsoft.Office.Tools.Excel.SmartTag> rozhraní, použijte `Globals.Factory.CreateSmartTag` metoda. Další informace o `Globals.Factory`, najdete v části [globální přístup k objektům v projektech Office](../vsto/global-access-to-objects-in-office-projects.md).  
  
### <a name="enable-type-equivalence-and-embedded-types-in-projects-that-target-the-net-framework-4-or-later"></a>Povolit ekvivalence typů a vložené typy v projektech cílených na rozhraní .NET Framework 4 nebo novější  
 Protože objektový model pro rozšíření Office [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo později jsou založené na rozhraní, můžete použít funkci typ ekvivalenční v jak Visual C# a Visual Basic v sadě Visual Studio pro vložení informací o typu ze [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] do řešení . Tato funkce umožňuje řešení pro systém Office a [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] verzi nezávisle na sobě navzájem. Například, pokud řešení používá <xref:Microsoft.Office.Tools.Word.Document> rozhraní jako vloženého typu a další verzi modulu runtime přidá členy <xref:Microsoft.Office.Tools.Word.Document> rozhraní, vaše řešení budou i nadále fungovat s další verzi modulu runtime. Pokud vaše řešení nepoužívá <xref:Microsoft.Office.Tools.Word.Document> rozhraní jako vloženého typu, pak bude vaše řešení přestane fungovat v další verzi modulu runtime.  
  
 Ve výchozím nastavení, není povolená funkce ekvivalence typů, při vytváření projektu Office s cílem [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo novější. Pokud chcete tuto funkci povolit, nastavte **vložit zprostředkovatel komunikace s objekty typy** vlastnosti každého následující odkazy na sestavení ve vašem projektu a **True**:  
  
-   Microsoft.Office.Tools.dll  
  
-   Microsoft.Office.Tools.Common.dll  
  
-   Microsoft.Office.Tools.Excel.dll  
  
-   Microsoft.Office.Tools.Outlook.dll  
  
-   Microsoft.Office.Tools.Word.dll  
  
 Když projekt po provedení této změny sestavíte, budou informace o typech pro všechny typy modulu runtime používané projektem vloženy do sestavení řešení. Tyto informace vloženého typu, nikoli typ informace v odkazovaných sestaveních jsou používány řešení za běhu.  
  
##  <a name="UnmanagedLoader"></a> Pochopení zavaděč řešení Office  
 Visual Studio Tools for Office runtime zahrnuje několik nespravované knihoven DLL, které používají aplikace Office načíst modul runtime a řešení pro systém Office. I když by nikdy nemělo být nutné pracovat s těmito knihovnami DLL přímo, znalost účelu těchto knihoven DLL vám může pomoci lépe porozumět architektuře řešení pro Office.  
  
 Informace o tom, jak tyto součásti jsou používány během procesu načítání, najdete v článku [architektura přizpůsobení na úrovni dokumentu](../vsto/architecture-of-document-level-customizations.md) a [architektura VSTO doplňky](../vsto/architecture-of-vsto-add-ins.md).  
  
### <a name="vstoeedll"></a>VSTOEE.dll  
 Když uživatel otevře přizpůsobení na úrovni dokumentu nebo spustí doplňku VSTO, aplikace Office volání *VSTOEE.dll* úkoly vyžadované pro načtení [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)].  
  
 *VSTOEE.dll* je zajištěno, že správnou verzi [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] je načteno pro řešení a nainstalovaná verze systému Office. I když více verzí [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] lze nainstalovat na stejný počítač, pouze jedna instance *VSTOEE.dll* je nainstalován v čase. Toto je *VSTOEE.dll* , který byl součástí modulu runtime v počítači nainstalována nejnovější verze. Další informace o různých verzích [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] který lze použít pro jiná řešení najdete v tématu [spuštění řešení v různých verzích systému Microsoft Office](../vsto/running-solutions-in-different-versions-of-microsoft-office.md).  
  
### <a name="vstoloaderdll"></a>VSTOLoader.dll  
 Po *VSTOEE.dll* načte příslušnou verzi [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)], *VSTOLoader.dll* provádí většinu činností, které je potřeba načíst sestavení řešení. *VSTOLoader.dll* některé věci:  
  
-   Vytvoří doménu aplikace pro každé sestavení řešení.  
  
-   Pomocí kontrol zabezpečení ověří, zda má sestavení řešení oprávnění ke spuštění.  
  
-   Načte verzi rozšíření Office pro rozhraní .NET Framework, které je požadováno řešením.  
  
 *VSTOLoader.dll* také provede několik věcí, které jsou specifické pro doplňky VSTO:  
  
-   Implementuje <xref:Extensibility.IDTExtensibility2> rozhraní. <xref:Extensibility.IDTExtensibility2> je rozhraní modelu COM, které se musí implementovat všech doplňků VSTO pro aplikace Microsoft Office. Toto rozhraní definuje metody, které aplikace volá ke komunikaci s doplňku VSTO.  
  
-   Imanagedaddin – rozhraní implementuje. Toto rozhraní je používány aplikací Office za účelem načtení doplňků VSTO. Další informace najdete v tématu [imanagedaddin – rozhraní](../vsto/imanagedaddin-interface.md).  
  
## <a name="understand-the-32-bit-and-64-bit-versions-of-the-runtime"></a>Pochopení 32bitové a 64bitové verze modulu runtime  
 Existují samostatné 64bitové a 32bitové verze Visual Studio 2010 Tools for Office runtime. Spouštění řešení v 64bitové a 32bitové edice Office se používají tyto verze modulu runtime. Následující tabulka uvádí, kterou verzi modulu runtime je požadované pro každou kombinaci systému Windows a Office.  
  
|Edice systému Windows|Edice sady Microsoft Office|Požadovaná verze modulu Visual Studio Tools for Office Runtime|  
|------------------------|---------------------------------|--------------------------------------------------------------------|  
|32bitová|32bitová|32bitová|  
|64bitových|32bitová|64bitových|  
|64bitových|64bitových|64bitových|  
  
 Při instalaci Office, požadovaná verze [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] je nainstalována spolu s Office. Například při instalaci 64bitová verze Office na 64bitovou verzi systému Windows, verze 64-bit [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] je také nainstalován. Další informace o instalaci [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] s Office, najdete v části [Visual Studio Tools for Office runtime instalace scénáře](../vsto/visual-studio-tools-for-office-runtime-installation-scenarios.md).  
  
 64bitová verze systému Office můžete také spouštět řešení pro systém Office, které byly vytvořeny pomocí šablony projektů pro systém Microsoft Office 2007 v sadě Visual Studio 2008. Neumožňuje však spouštět řešení pro Office vytvořená pomocí šablon projektů pro Microsoft Office 2003 v sadě Visual Studio 2008 ani řešení pro Office vytvořená pomocí sady Visual Studio 2005. Další informace najdete v tématu [spuštění řešení v různých verzích systému Microsoft Office](../vsto/running-solutions-in-different-versions-of-microsoft-office.md).  
  
## <a name="repair-the-visual-studio-2010-tools-for-office-runtime"></a>Opravte Visual Studio 2010 Tools for Office runtime  
 Pokud potřebujete opravit modul runtime, otevřete **programy a funkce** nebo **přidat nebo odebrat programy** v Ovládacích panelech vyberte **Microsoft Visual Studio 2010 Tools for Office Runtime**v seznamu programy a klikněte na tlačítko **odinstalovat**. Instalační program, který se spustí, umožňuje modul runtime opravit. Pokud kliknete na tlačítko **změnu**, nejsou zadána možnost pro opravu modulu runtime.  
  
## <a name="see-also"></a>Viz také:  
 [Visual Studio Tools for Office runtime instalace scénáře](../vsto/visual-studio-tools-for-office-runtime-installation-scenarios.md)   
 [Sestavení sady Visual Studio Tools for Office runtime](../vsto/assemblies-in-the-visual-studio-tools-for-office-runtime.md)   
 [Architektura řešení pro systém Office v sadě Visual Studio](../vsto/architecture-of-office-solutions-in-visual-studio.md)   
 [Architektura přizpůsobení na úrovni dokumentu](../vsto/architecture-of-document-level-customizations.md)   
 [Architektura doplňků VSTO](../vsto/architecture-of-vsto-add-ins.md)   
 [Postupy: vytváření projektů Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [Upgrade a migrace řešení Office](../vsto/upgrading-and-migrating-office-solutions.md)  
  
  