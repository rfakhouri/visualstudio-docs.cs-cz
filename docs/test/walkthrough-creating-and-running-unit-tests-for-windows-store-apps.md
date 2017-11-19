---
title: "Návod: Vytváření a spouštění testování částí pro aplikace UWP | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- unit tests, creating
- unit tests
- unit tests, UWP apps
- unit tests, running
ms.assetid: dd3e8a6a-b366-433e-a409-b9a9b89da89a
caps.latest.revision: "21"
ms.author: douge
manager: douge
ms.openlocfilehash: 32cab11dd909fc8b60134ebff0d5f37c0b14dcd6
ms.sourcegitcommit: c0422a3d594ea5ae8fc03f1aee684b04f417522e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/02/2017
---
# <a name="walkthrough-creating-and-running-unit-tests-for-uwp-apps"></a>Návod: Vytváření a spouštění testování částí pro aplikace UWP
Visual Studio zahrnuje podporu pro testování částí spravované [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] aplikace a obsahuje šablony knihoven testů jednotek pro Visual C#, Visual Basic a Visual C++.  
  
> [!TIP]
>  Další informace o vývoji [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] aplikace, najdete v části [Začínáme s aplikací UWP](http://go.microsoft.com/fwlink/?LinkID=241410).  
  
 Visual Studio poskytuje testování funkce následujících částí:  
  
-   [Vytváření projektů testování částí](#CreateAndRunUnitTestWin8Tailored_Create)  
  
-   [Upravte Manifest pro projektu testování částí](#CreateAndRunUnitTestWin8Tailored_Manifest)  
  
-   [Programování testu jednotek](#CreateAndRunUnitTestWin8Tailored_Code)  
  
-   [Spouštění testování částí](#CreateAndRunUnitTestWin8Tailored_Run)  
  
 Následující postupy popisují postup vytvoření, spuštění a ladění testování částí pro spravovaný Windows 8 [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] aplikace.  
  
## <a name="prerequisites"></a>Požadavky  
 Visual Studio  
  
##  <a name="CreateAndRunUnitTestWin8Tailored_Create"></a>Vytváření projektů testování částí  
  
#### <a name="to-create-a-unit-test-project-for-a-uwp-app"></a>Vytvoření projektu testů jednotek pro aplikace UWP  
  
1.  Z **soubor** nabídce zvolte **nový projekt**.  
  
     Zobrazí se dialogové okno Nový projekt.  
  
2.  V části šablony, vyberte programovací jazyk, který chcete vytvořit testování částí v a pak zvolte přidruženého [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] knihovny test jednotky. Například vyberte **Visual C#** , zvolte **univerzální pro Windows**a potom zvolte **knihovny Test jednotky (Universal Windows)**.  
  
    > [!NOTE]
    >  Visual Studio obsahuje šablony knihoven testů jednotek pro Visual C#, Visual Basic a Visual C++.  
  
3.  (Volitelné) V **název** textovému poli, zadejte název, kterou chcete použít pro [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)]projektu testování částí.  
  
4.  (Volitelné) Změňte cestu, kde chcete vytvořit projekt tak, že ho v **umístění** textovému poli, nebo výběrem položky **Procházet** tlačítko.  
  
5.  (Volitelné) V **řešení** název textového pole, zadejte tento název, kterou chcete použít pro vaše řešení.  
  
6.  Ponechte **vytvořit adresář pro řešení** možnost vybrána a vyberte **OK** tlačítko.  
  
     ![Přizpůsobit knihovny Test jednotky](../test/media/unit_test_win8_1.png "Unit_Test_Win8_1")  
  
     Průzkumník řešení je naplněna s nové [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)]projektu testování částí a editoru kódu zobrazí výchozí testu jednotek s názvem UnitTest1.  
  
     ![Nový projekt test šité na míru jednotky](../test/media/unit_test_win8_unittestexplorer_newprojectcreated.png "Unit_Test_Win8_UnitTestExplorer_NewProjectCreated")  
  
##  <a name="CreateAndRunUnitTestWin8Tailored_Manifest"></a>Upravte Manifest pro projektu testování částí  
 Může být nutné upravit manifest pro projektu testů jednotek k poskytování požadované možnosti a spusťte aplikaci.  
  
#### <a name="to-edit-the-unit-test-projects-uwp-application-manifest-file"></a>Chcete-li upravit souboru manifestu aplikace UWP projektu testování částí  
  
1.  V Průzkumníku řešení v novém [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] projektu testů jednotek, klikněte pravým tlačítkem na soubor Package.appxmanifest a zvolte **otevřete**.  
  
     Návrhář manifestu zobrazí pro úpravy.  
  
2.  V Návrháři Manifest zvolte **možnosti** kartě.  
  
3.  V seznamu v části **možnosti**, vyberte možnosti, je nutné, vaše testování částí a kód to tak, aby měl testování. Vyberte například **Internet** zaškrtávací políčko, pokud jednotkové testování vyžaduje a kód je testování musí mít možnost přístupu k Internetu.  
  
    > [!NOTE]
    >  Možnosti vyberete by zahrnovat pouze možnosti, které jsou nezbytné, aby [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] testů jednotek, aby správně fungoval. Možnosti nikdy nemusí zahrnovat funkce, které nejsou součástí [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] aplikace se otestovány a obecně by měl být podmnožinou možnosti zadané pro [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)]aplikace v rámci testu.  
  
     Další informace o návrháře manifestu najdete v tématu [nakonfigurovat balíček aplikace pro Windows 8.1 pomocí návrháře manifestu](http://msdn.microsoft.com/Library/24c58b7f-9c6d-41c3-b385-c1e8497d5b2d).  
  
     ![Manifest Test jednotky](../test/media/unit_test_win8_.png "Unit_Test_Win8_")  
  
##  <a name="CreateAndRunUnitTestWin8Tailored_Code"></a>Programování testu jednotek  
  
#### <a name="to-code-the-unit-test-for-a-uwp-app"></a>K programování testu jednotek pro aplikace UWP  
  
1.  V editoru kódu upravit testování částí a přidat vyhodnotí a logiku potřebnou pro svůj test.  
  
     Další informace najdete v tématu v [používání tříd Assert](http://go.microsoft.com/fwlink/?LinkID=224991) v knihovně MSDN.  
  
##  <a name="CreateAndRunUnitTestWin8Tailored_Run"></a>Spouštění testování částí  
  
#### <a name="to-build-the-solution-and-run-the-unit-test-using-test-explorer"></a>Sestavení řešení a spuštění testování částí pomocí Průzkumníka testů  
  
1.  Na **Test** nabídce zvolte **Windows**a potom zvolte **Průzkumníka testů**.  
  
     Testování Explorer zobrazí bez svůj test se uvedené.  
  
2.  Z **sestavení** nabídce zvolte **sestavit řešení**.  
  
     Test jednotky je nyní obsažena.  
  
    > [!NOTE]
    >  Musíte sestavit řešení Chcete-li aktualizovat seznam testů jednotek v Průzkumníka testů.  
  
    > [!WARNING]
    >  Visual Studio známý problém: než začnete vytvářet k testovacímu projektu, musíte otevřít Průzkumníka testů.  
  
3.  V Průzkumníku otestovat zvolte testování částí, které jste vytvořili.  
  
    > [!TIP]
    >  Průzkumníka testů obsahuje odkaz na zdrojový kód do **zdroj:**.  
  
4.  Zvolte **spustit všechny**.  
  
     ![Průzkumníka testů jednotek & č. 45; spuštění testování částí](../test/media/unit_test_win8_unittestexplorer_contextmenurun.png "Unit_Test_Win8_UnitTestExplorer_ContextMenuRun")  
  
    > [!TIP]
    >  Vyberte jeden nebo více testů částí uvedených v Průzkumníku, klikněte pravým tlačítkem a zvolte **spuštění testů vybrané**.  
    >   
    >  Kromě toho můžete **ladění vybrané testy**, **otevřete testovací**a použít **vlastnosti** možnost.  
    >   
    >  ![Průzkumníka testů jednotek & č. 45; UNI testovací kontextovou nabídku](../test/media/unit_test_win8_unittestexplorer_contextmenu.png "Unit_Test_Win8_UnitTestExplorer_ContextMenu")  
  
     Jednotka test spustí. Po dokončení testování Explorer zobrazí stav testu, uplynulý čas a obsahuje odkaz na zdroj.  
  
     ![Průzkumníka testů jednotek & č. 45; Test byl dokončen](../test/media/unit_test_win8_unittestexplorer_done.png "Unit_Test_Win8_UnitTestExplorer_Done")  
  
## <a name="external-resources"></a>Externí zdroje  
  
### <a name="videos"></a>Videa  
 [Channel 9: Testování aplikace UWP vyvíjené v XAML částí](http://go.microsoft.com/fwlink/?LinkId=226285)  
  
### <a name="forums"></a>Diskuzní fóra  
 [Testování částí sady Visual Studio](http://go.microsoft.com/fwlink/?LinkId=224477)  
  
### <a name="msdn-library"></a>Knihovna MSDN  
 [Knihovna MSDN – vytváření a spouštění testování částí pro existujícího kódu (Visual Studio 2010)](http://go.microsoft.com/fwlink/?LinkID=223683)  
  
## <a name="see-also"></a>Viz také  
 [Testování aplikací pro UPW pomocí sady Visual Studio](../test/testing-store-apps-with-visual-studio.md)   
 [Vytvoření a testování aplikací UWP pomocí Team Foundation Build](http://msdn.microsoft.com/Library/d0ca17bb-deae-4f3d-a18d-1a99bebceaa9)
