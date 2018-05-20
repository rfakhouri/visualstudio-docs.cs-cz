---
title: Architektura doplňků VSTO
ms.custom: ''
ms.date: 02/02/2017
ms.technology: office-development
ms.prod: visual-studio-dev15
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- VSTOLoader.dll
- architecture [Office development in Visual Studio], application-level add-ins
- vstoee.dll
- application-level add-ins [Office development in Visual Studio], architecture
- add-ins [Office development in Visual Studio], architecture
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 97532cfc91fb75bdeaa1f10c2fdcdd65eaec6850
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/17/2018
---
# <a name="architecture-of-vsto-add-ins"></a>Architektura doplňků VSTO
  Doplňků VSTO vytvořené pomocí doplňku Office developer tools v sadě Visual Studio mít architektury funkce, které zdůraznil stability a zabezpečení a umožňuje jim úzce spolupracovat s Microsoft Office. Toto téma popisuje následující aspekty doplňků VSTO:  
  
-   [Pochopení doplňků VSTO](#UnderstandingAddIns)  
  
-   [Součástí doplňků VSTO](#AddinComponents)  
  
-   [Jak fungují doplňků VSTO pomocí aplikace Microsoft Office](#HowAddinsWork)  
  
 [!INCLUDE[appliesto_allapp](../vsto/includes/appliesto-allapp-md.md)]  
  
 Obecné informace o vytváření doplňků VSTO najdete v tématu [přehled vývoje řešení pro systém Office &#40;VSTO&#41; ](../vsto/office-solutions-development-overview-vsto.md) a [Začínáme s programováním doplňků VSTO](../vsto/getting-started-programming-vsto-add-ins.md).  
  
##  <a name="UnderstandingAddIns"></a> Pochopení doplňků VSTO  
 Když používáte Office developer tools v sadě Visual Studio k vytvoření doplňku VSTO, můžete vytvořit sestavení spravovaného kódu, které je načtena aplikace Microsoft Office. Po načíst sestavení doplňku VSTO může reagovat na události, které jsou vyvolány v aplikaci (například když uživatel klikne položku nabídky). Doplňku VSTO můžete také volání do modelu objektu automatizovat a rozšířit aplikace a může použít jakékoli třídy v [!INCLUDE[dnprdnshort](../sharepoint/includes/dnprdnshort-md.md)].  
  
 Sestavení komunikuje s komponentami aplikace modelu COM pomocí primární spolupracující sestavení aplikace. Další informace najdete v tématu [primární spolupracující sestavení Office](../vsto/office-primary-interop-assemblies.md) a [přehled vývoje řešení pro systém Office &#40;VSTO&#41;](../vsto/office-solutions-development-overview-vsto.md).  
  
 Pokud více doplňků VSTO jsou nainstalovány pro aplikaci, načíst je každý doplňku VSTO v doméně jinou aplikaci. To znamená, že jeden VSTO Add-in, který se chová nesprávně nemohou způsobit další doplňků VSTO selhání. Pomáhá také zajistěte, aby při ukončení aplikace všechny doplňku VSTO sestavení uvolněn z paměti. Další informace o doménách aplikací najdete v tématu [aplikační domény](/dotnet/framework/app-domains/application-domains).  
  
> [!NOTE]  
>  Doplňků VSTO vytvořené pomocí doplňku Office developer tools v sadě Visual Studio jsou určeny k použití jenom v případě, že se koncový uživatel spustí hostitele aplikace Microsoft Office. Pokud je aplikace spuštěna prostřednictvím kódu programu (například pomocí automatizace), doplňku VSTO nemusí fungovat podle očekávání.  
  
##  <a name="AddinComponents"></a> Součástí doplňků VSTO  
 Přestože je sestavení doplňku VSTO hlavní součásti, existuje několik komponent, které hraje důležitou roli v tom, jak aplikace Microsoft Office zjišťovat a načíst doplňků VSTO.  
  
### <a name="registry-entries"></a>Položky registru  
 Aplikace Microsoft Office zjistit doplňků VSTO tak, že vyhledá sada položek registru. Úplný seznam položky registru používané doplňků VSTO, najdete v části [položky registru pro doplňky VSTO](../vsto/registry-entries-for-vsto-add-ins.md).  
  
 Při sestavování řešení Visual Studio vytvoří všechny požadované položky registru na vývojovém počítači, aby mohli ladění a spouštění vaší doplňku VSTO. Další informace najdete v tématu [řešení pro systém Office sestavení](../vsto/building-office-solutions.md).  
  
 Pokud používáte ClickOnce k nasazení řešení, vytvoří instalační program automaticky vygenerovaných procesem publikování klíče registru na počítači koncového uživatele. Další informace najdete v tématu [nasazení řešení Office s použitím technologie ClickOnce](../vsto/deploying-an-office-solution-by-using-clickonce.md).  
  
### <a name="deployment-manifest-and-application-manifest"></a>Manifest nasazení a manifest aplikace  
 Doplňků VSTO používat k identifikaci a načíst nejnovější verzi doplňku VSTO sestavení manifestů aplikace a manifesty nasazení. Nasazení manifest odkazuje na aktuální manifest aplikace. Manifest aplikace odkazuje na sestavení doplňku VSTO a určuje třídu vstupní bod provést v sestavení. Další informace najdete v tématu [aplikace a nasazení manifesty v řešeních pro systém Office](../vsto/application-and-deployment-manifests-in-office-solutions.md).  
  
### <a name="visual-studio-tools-for-office-runtime"></a>Visual Studio Tools for Office Runtime  
 Pokud chcete spustit doplňků VSTO vytvořené pomocí doplňku Office developer tools v sadě Visual Studio, musí mít počítače koncového uživatele [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] nainstalována. Modul runtime zahrnuje nespravované komponenty a sadu spravovaných sestavení. Nespravované součásti načíst sestavení doplňku VSTO. Spravovaná sestavení poskytují objektový model, který používá váš kód doplňku VSTO pro automatizaci a rozšířit hostitelskou aplikaci.  
  
 Další informace najdete v tématu [Visual Studio Tools for Office runtime přehled](../vsto/visual-studio-tools-for-office-runtime-overview.md).  
  
##  <a name="HowAddinsWork"></a> Jak fungují doplňků VSTO pomocí aplikace Microsoft Office  
 Pokud uživatel spustí aplikaci Microsoft Office, aplikace použije manifest nasazení a manifest aplikace pro vyhledání a načtení nejaktuálnější verzi sestavení doplňku VSTO. Následující obrázek znázorňuje základní architektura těchto doplňků VSTO.  
  
 ![Architektura doplňku office 2007](../vsto/media/office07addin.png "architektura doplňku Office 2007")  
  
> [!NOTE]  
>  V řešení pro systém Office cílených [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)], řešení volání do modelu objektu hostitelské aplikace podle pomocí PIA – typ informace vložené v sestavení řešení, namísto volání do primární přímo. Další informace najdete v tématu [návrhu a vytvářet řešení systému Office](../vsto/designing-and-creating-office-solutions.md).  
  
### <a name="loading-process"></a>Proces načítání  
 Následující kroky dojít, když uživatel spustí aplikaci:  
  
1.  Aplikace zkontroluje registru pro položky, které identifikují doplňků VSTO vytvořené pomocí doplňku Office developer tools v sadě Visual Studio.  
  
2.  Pokud aplikace vyhledá tyto položky registru, načte, aplikace VSTOEE.dll, který načte VSTOLoader.dll. Toto nespravované knihovny DLL, které jsou součástí zavaděč pro Visual Studio 2010 Tools for Office Runtime. Další informace najdete v tématu [Visual Studio Tools for Office runtime přehled](../vsto/visual-studio-tools-for-office-runtime-overview.md).  
  
3.  *VSTOLoader.dll* načte [!INCLUDE[dnprdnshort](../sharepoint/includes/dnprdnshort-md.md)] a spustí spravovaná část [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)].  
  
4.  [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Vyhledává manifestu aktualizace a stáhne nejnovější manifestů aplikace a nasazení.  
  
5.  [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Provádí řadu kontrol zabezpečení. Další informace najdete v tématu [řešení zabezpečení Office](../vsto/securing-office-solutions.md).  
  
6.  Pokud doplňku VSTO je důvěryhodný pro spuštění [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] používá ke kontrole aktualizací sestavení – manifest nasazení a manifest aplikace. Pokud je k dispozici nová verze sestavení, modul runtime stáhne novou verzi sestavení do [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] mezipaměti na klientském počítači. Další informace najdete v tématu [nasazení řešení Office](../vsto/deploying-an-office-solution.md).  
  
7.  [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Vytvoří novou doménu aplikace, ve kterém se načíst sestavení doplňku VSTO.  
  
8.  [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Načte doplňku VSTO sestavení do domény aplikace.  
  
9. [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Volání <xref:Microsoft.Office.Tools.AddInBase.RequestComAddInAutomationService%2A> metoda vaší VSTO Add-in, pokud jste se přepsat.  
  
     Volitelně můžete přepsat tuto metodu ke zveřejnění na objekt v doplňku VSTO pro jiné řešení pro Microsoft Office. Další informace najdete v tématu [volání kódu v doplňcích VSTO z jiných řešení pro Office](../vsto/calling-code-in-vsto-add-ins-from-other-office-solutions.md).  
  
10. [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Volání <xref:Microsoft.Office.Tools.AddInBase.RequestService%2A> metoda vaší VSTO Add-in, pokud jste se přepsat.  
  
     Volitelně můžete přepsat tuto metodu za účelem vrátí objekt, který implementuje rozhraní rozšiřitelnosti rozšířit funkce aplikace Microsoft Office. Další informace najdete v tématu [funkcí přizpůsobení uživatelského rozhraní pomocí rozšiřujících rozhraní](../vsto/customizing-ui-features-by-using-extensibility-interfaces.md).  
  
    > [!NOTE]  
    >  [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Díky samostatné volání <xref:Microsoft.Office.Tools.AddInBase.RequestService%2A> metoda pro jednotlivá rozhraní rozšiřitelnosti, kterou podporuje hostitelskou aplikaci. I když první volání <xref:Microsoft.Office.Tools.AddInBase.RequestService%2A> metoda obvykle dojde před voláním `ThisAddIn_Startup` metoda, vaše doplňku VSTO neprovádějte žádné předpoklady o tom, kdy <xref:Microsoft.Office.Tools.AddInBase.RequestService%2A> volání metody nebo kolikrát bude zavolána.  
  
11. [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Volání `ThisAddIn_Startup` metoda v doplňku VSTO. Tato metoda je výchozí obslužnou rutinu <xref:Microsoft.Office.Tools.AddInBase.Startup> událostí. Další informace najdete v tématu [události v projektech Office](../vsto/events-in-office-projects.md).  
  
## <a name="see-also"></a>Viz také  
 [Architektura řešení pro systém Office v sadě Visual Studio](../vsto/architecture-of-office-solutions-in-visual-studio.md)   
 [Architektura přizpůsobení na úrovni dokumentu](../vsto/architecture-of-document-level-customizations.md)   
 [Visual Studio Tools for Office runtime – přehled](../vsto/visual-studio-tools-for-office-runtime-overview.md)   
 [Program doplňků VSTO](../vsto/programming-vsto-add-ins.md)   
 [Vývoj řešení pro systém Office](../vsto/developing-office-solutions.md)   
 [Zabezpečení řešení pro systém Office](../vsto/securing-office-solutions.md)   
 [Nasazení řešení Office](../vsto/deploying-an-office-solution.md)  
  
  