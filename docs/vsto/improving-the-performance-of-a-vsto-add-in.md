---
title: "Zvýšení výkonu doplňku VSTO | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
ms.assetid: 03ef25c2-6308-4737-a655-74bbbb472dc2
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: bafc82f247f067f1f836730ec1f676f2f9559915
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="improving-the-performance-of-a-vsto-add-in"></a>Zvýšení výkonu doplňku VSTO
  Můžete uživatelům poskytovat lepší pomocí optimalizace doplňků VSTO vytvořených pro Office aplikace tak, aby rychle začít, vypnout, otevřete položky a provádět další úlohy. Pokud vaše doplňku VSTO pro Outlook, můžete také snížit pravděpodobnost, že vaše doplňku VSTO bude zakázána z důvodu snížený výkon. Může zvýšit výkon vaší doplňku VSTO implementací následujících strategií:  
  
-   [Načtení doplňků VSTO na vyžádání](#Load).  
  
-   [Publikovat řešení pro systém Office pomocí Instalační služby systému Windows](#Publish).  
  
-   [Nepoužívat pásu karet reflexe](#Bypass).  
  
-   [V samostatné prováděcí vlákno provádět nákladné operace](#Perform).  
  
 Další informace o tom, jak optimalizovat doplňku VSTO pro Outlook najdete v tématu [výkonu kritéria pro zachování doplňků VSTO povoleno](http://go.microsoft.com/fwlink/?LinkID=266503).  
  
##  <a name="Load"></a>Zatížení doplňků VSTO na vyžádání  
 Můžete nakonfigurovat Add-in VSTO načíst jenom v následujících případech:  
  
-   Při prvním uživatel spustí aplikaci, která po instalaci doplňku VSTO.  
  
-   Při prvním uživatel pracuje s doplňku VSTO po spuštění aplikace následné kdykoli.  
  
 Například vaše doplňku VSTO může naplnění na listu s daty když uživatel vybere vlastní tlačítko, které je označeno **načíst Moje Data**. Aplikace musí načíst vaše doplňku VSTO alespoň jednou, aby **načíst Moje Data** tlačítko můžete zobrazit na pásu karet. Ale doplňku VSTO nenačte znovu když uživatel spustí aplikaci, při příštím. Doplňku VSTO načte, když uživatel pouze vybere **načíst Moje Data** tlačítko.  
  
#### <a name="to-configure-a-clickonce-solution-to-load-vsto-add-ins-on-demand"></a>Ke konfiguraci řešení ClickOnce načíst doplňků VSTO na vyžádání  
  
1.  V **Průzkumníku**, vyberte uzel projektu.  
  
2.  Na řádku nabídek zvolte **zobrazení**, **stránky vlastností**.  
  
3.  Na **publikovat** , zvolte **možnosti** tlačítko.  
  
4.  V **možnosti publikování** dialogovém okně vyberte **nastavení Office** položka seznamu, vyberte **zatížení na vyžádání** možnost a potom vyberte **OK**tlačítko.  
  
#### <a name="to-configure-a-windows-installer-solution-to-load-vsto-add-ins-on-demand"></a>Ke konfiguraci řešení Instalační služby systému Windows pro načtení doplňků VSTO na vyžádání  
  
1.  V registru, nastavte `LoadBehavior` položku *kořenové*\Software\Microsoft\Office\\*ApplicationName*\Addins\\*ID Add-in*klíče na **0x10**.  
  
     Další informace najdete v tématu [položky registru pro doplňky VSTO](../vsto/registry-entries-for-vsto-add-ins.md).  
  
#### <a name="to-configure-a-solution-to-load-vsto-add-ins-on-demand-while-you-debug-the-solution"></a>Ke konfiguraci řešení při načítání doplňků VSTO na vyžádání ladění řešení  
  
1.  Vytvořit skript, který nastaví `LoadBehavior` položku *kořenové*\Software\Microsoft\Office\\*ApplicationName*\Addins\\*ID Add-in* klíče na **0x10**.  
  
     Následující kód ukazuje příklad tohoto skriptu.  
  
    ```  
    [HKEY_CURRENT_USER\Software\Microsoft\Office\Excel\Addins\MyAddIn]  
    "Description"="MyAddIn"  
    "FriendlyName"="MyAddIn"  
    "LoadBehavior"=dword:00000010  
    "Manifest"="c:\\Temp\\MyAddIn\\bin\\Debug\\MyAddIn.vsto|vstolocal"  
  
    ```  
  
2.  Vytvoření události po sestavení, která aktualizuje registr pomocí skriptu.  
  
     Následující kód ukazuje příklad příkaz řetězce, který může přidat do události po sestavení.  
  
    ```  
    regedit /s "$(SolutionDir)$(SolutionName).reg"  
  
    ```  
  
     Informace o tom, jak vytvořit události po sestavení v projektu C# najdete v tématu [postupy: určení událostí sestavení &#40; C &#35; &#41; ](/visualstudio/ide/how-to-specify-build-events-csharp).  
  
     Informace o tom, jak vytvořit události po sestavení v projektu jazyka Visual Basic najdete v tématu [postupy: určení událostí sestavení &#40; Visual Basic &#41; ](/visualstudio/ide/how-to-specify-build-events-visual-basic).  
  
##  <a name="Publish"></a>Publikovat řešení pro systém Office pomocí Instalační služby systému Windows  
 Pokud publikujete řešení pomocí Instalační služby systému Windows, Visual Studio 2010 Tools for Office Runtime obchází následující kroky, až se načte doplňku VSTO.  
  
-   Ověření manifestu schématu.  
  
-   Automatické zjišťování aktualizací.  
  
-   Ověření digitálních podpisů manifesty nasazení.  
  
    > [!NOTE]  
    >  Tento přístup není nutné v případě nasazení vaší doplňku VSTO do zabezpečeného umístění na počítačích uživatelů.  
  
 Další informace najdete v tématu [nasazení řešení Office pomocí Instalační služba systému Windows](../vsto/deploying-an-office-solution-by-using-windows-installer.md).  
  
##  <a name="Bypass"></a>Reflexe nepoužívat pásu karet  
 Pokud vytvoříte řešení pomocí [!INCLUDE[vs_dev11_long](../sharepoint/includes/vs-dev11-long-md.md)], ujistěte se, že uživatelé nainstalovali nejnovější verzi sady Visual Studio 2010 Tools for Office Runtime při nasazení řešení. Starší verze tohoto modulu runtime projeví sestavení řešení najít vlastních nastavení pásu karet. Tento proces může způsobit doplňku VSTO načíst pomaleji.  
  
 Jako alternativu můžete zabránit v libovolné verzi sady Visual Studio 2010 Tools for Office Runtime pomocí reflexe k identifikaci vlastních nastavení pásu karet. Chcete-li provést tuto strategii, přepište `CreateRibbonExtensibility` metoda a objekty explicitně návratový pásu karet. Pokud vaše doplňku VSTO neobsahuje žádné vlastních nastavení pásu karet, vrátí `null` uvnitř metody.  
  
 Následující příklad vrátí objekt pásu karet na základě hodnoty pole.  
  
 [!code-vb[Trin_Ribbon_Choose_Ribbon#1](../vsto/codesnippet/VisualBasic/trin_ribbon_choose_ribbon_4/ThisWorkbook.vb#1)]
 [!code-csharp[Trin_Ribbon_Choose_Ribbon#1](../vsto/codesnippet/CSharp/trin_ribbon_choose_ribbon_4/ThisWorkbook.cs#1)]  
  
##  <a name="Perform"></a>V samostatné prováděcí vlákno provádět nákladné operace  
 Vezměte v úvahu provádění časově náročné úkoly (například dlouhotrvající úlohy, připojení databáze nebo jiné typy volání sítě) v samostatných vlákna. Další informace najdete v tématu [dělení na vlákna podporu Office](../vsto/threading-support-in-office.md).  
  
> [!NOTE]  
>  Všechny kód, který volá do modelu objektu Office musí být spuštěn v hlavní vlákno.  
  
## <a name="see-also"></a>Viz také  
 [Doplňky na vyžádání načítání VSTO](http://blogs.msdn.com/b/andreww/archive/2008/07/14/demand-loading-vsto-add-ins.aspx)   
 [Zpoždění načtení modulu CLR v doplňcích Office](http://blogs.msdn.com/b/andreww/archive/2008/04/19/delay-loading-the-clr-in-office-add-ins.aspx)   
 [Výkon VSTO: Načítání zpoždění a (Stephen Peters)](http://blogs.msdn.com/b/vsto/archive/2010/01/07/vsto-performance-delay-loading-and-you.aspx)   
 [Vylepšení výkonu připravuje se na aktualizaci Service Pack okolo vás (Stephen Peters)](http://blogs.msdn.com/b/vsto/archive/2010/11/30/performance-improvements-coming-soon-to-a-service-pack-near-you-stephen-peters.aspx)   
 [Výkon VSTO: Pásu karet reflexe (Stephen Peters)](http://blogs.msdn.com/b/vsto/archive/2010/06/03/vsto-performance-ribbon-reflection.aspx)  
  
  