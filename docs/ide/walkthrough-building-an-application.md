---
title: "Návod: Vytváření aplikace | Microsoft Docs"
ms.custom: 
ms.date: 09/25/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 485c8445f24dbd0aaec501649885df50d173347a
ms.sourcegitcommit: d6327b978661c0a745bf4b59f32d8171607803a3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/01/2018
---
# <a name="walkthrough-building-an-application"></a>Postupy: Sestavení aplikace

Provedením tohoto návodu budete seznámení s několik možností, které můžete nakonfigurovat při vytváření aplikací pomocí sady Visual Studio. Budete vytvářet vlastní konfiguraci sestavení, skrýt některé zprávy upozornění a zvýšit sestavení výstupní informace pro ukázkovou aplikaci.

## <a name="install-the-sample-application"></a>Instalace ukázkové aplikace

Stažení [Úvod do vytváření grafického subsystému WPF aplikací](https://code.msdn.microsoft.com/Introduction-to-Building-b8d16419) ukázka. Vyberte buď C# nebo Visual Basic. Po stažení je soubor .zip, rozbalte ho a otevřete **ExpenseItIntro.sln** souboru pomocí sady Visual Studio.

## <a name="create-a-custom-build-configuration"></a>Vytvořit vlastní konfiguraci sestavení

Když vytvoříte řešení, konfigurace debug a release sestavení a jejich výchozí platformy cíle jsou definovány pro řešení automaticky. Potom můžete přizpůsobit tyto konfigurace nebo vytvořit vlastní. Konfigurace sestavení zadejte typ sestavení. Platformy sestavení zadejte operační systém, který aplikace cílí pro danou konfiguraci. Další informace najdete v tématu [Principy konfigurací sestavení](../ide/understanding-build-configurations.md), [Principy platforem sestavení](../ide/understanding-build-platforms.md), a [postupy: nastavení ladění a konfigurace verze](../debugger/how-to-set-debug-and-release-configurations.md).

Můžete změnit nebo vytvořit platformy nastavení a konfigurace pomocí **nástroje Configuration Manager** dialogové okno. V tomto postupu vytvoříte konfigurace sestavení pro testování.

### <a name="to-create-a-build-configuration"></a>Pro vytvoření konfigurace sestavení

1. Otevřete **nástroje Configuration Manager** dialogové okno.

   ![Vytvoření nabídky nástroje Configuration Manager příkaz](../ide/media/buildwalk_configurationmanagerdialogbox.png "BuildWalk_ConfigurationManagerDialogBox")  

1. V **aktivní konfigurace řešení** vyberte  **\<nový... \>**.

1. V **novou konfiguraci řešení** dialogové okno, název novou konfiguraci `Test`, Kopírovat nastavení z existující konfiguraci ladění a potom zvolte **OK** tlačítko.

   ![Nové řešení dialogové okno Konfigurace](../ide/media/buildwalk_newsolutionconfigdlgbox.png "BuildWalk_NewSolutionConfigDlgBox")  

1. V **platforma Active řešení** vyberte  **\<nový... \>**.

1. V **nová platforma řešení** dialogovém okně vyberte **x64**a není Kopírovat nastavení z x86 platformy.

   ![Řešení platformy dialogové okno Nový](../ide/media/buildwalk_newsolutionplatform.png "BuildWalk_NewSolutionPlatform")  

1. Vyberte **OK** tlačítko.

   Konfigurace aktivního řešení se změnil na Test s platformou aktivním řešení nastavena na x64.

   ![Configuration Manager s testovací konfigurace](../ide/media/buildwalk_configmanagertestconfig.png "BuildWalk_ConfigManagerTestconfig")  

1. Zvolte **Zavřít**.

Můžete rychle ověřte nebo změňte konfiguraci active řešení pomocí **konfigurace řešení** na seznamu **standardní** panelu nástrojů.
  
![Možnost konfigurace řešení standardním panelu nástrojů](../ide/media/buildwalk_standardtoolbarsolutioncongfig.png "BuildWalk_StandardToolbarSolutionCongfig")  
  
## <a name="build-the-application"></a>Sestavení aplikace

Dále budete sestavte řešení s konfigurací vlastního sestavení.
  
### <a name="to-build-the-solution"></a>K sestavení řešení
  
-   Na řádku nabídek zvolte **sestavení** > **sestavit řešení**.
  
    **Výstup** okně se zobrazí výsledky sestavení. Sestavení bylo úspěšné.
  
## <a name="hide-compiler-warnings"></a>Skrýt upozornění kompilátoru

Dále budete zavedeme některé kód, který způsobí, že má být vygenerován kompilátorem upozornění.

1. Otevřete v projektu jazyka C# **ExpenseReportPage.xaml.cs** souboru. V **ExpenseReportPage** metoda, přidejte následující kód: `int i;`.

    NEBO

    Otevřete v projektu jazyka Visual Basic **ExpenseReportPage.xaml.vb** souboru. V konstruktoru vlastní **veřejné Sub New...** , přidejte následující kód: `Dim i`.

1. Sestavte řešení.

**Výstup** okně se zobrazí výsledky sestavení. Sestavení bylo úspěšné, ale byly vygenerovány upozornění:

![Výstup – okno jazyka Visual Basic](../ide/media/buildwalk_vbbuildoutputwnd.png "BuildWalk_VBBuildOutputWnd")

![Výstup – okno Visual C &#35; ] (../ide/media/buildwalk_csharpbuildoutputwnd.png "BuildWalk_CsharpBuildOutputWnd")

Můžete dočasně skrýt některé zprávy upozornění během sestavení místo kliknul zbytečných souborů až výstupu sestavení.

### <a name="to-hide-a-specific-c-warning"></a>Chcete-li skrýt konkrétní upozornění C#

1. V **Průzkumníku**, vyberte uzel nejvyšší úrovně projektu.

1. Na řádku nabídek zvolte **zobrazení**, **stránky vlastností**.
  
     **Návrhář projektu** otevře.

1. Vyberte **sestavení** stránky a pak na **potlačení upozornění** zadejte číslo upozornění **0168**.
  
     ![Vytvoření stránky, Návrhář projektu](../ide/media/buildwalk_csharpsupresswarnings.png "BuildWalk_CsharpSupressWarnings")  
  
     Další informace najdete v tématu [stránka sestavení, Návrhář projektu (C#)](../ide/reference/build-page-project-designer-csharp.md).

1. Sestavte řešení.
  
     **Výstup** okně zobrazí pouze souhrnné informace o sestavení.
  
     ![Output Window, Visual C&#35; Build Warnings](../ide/media/buildwalk_visualcsharpbuildwarnings.png "BuildWalk_VisualCsharpBuildWarnings")  
  
### <a name="to-suppress-all-visual-basic-build-warnings"></a>Chcete-li potlačit všech upozornění sestavení jazyka Visual Basic

1. V **Průzkumníku**, vyberte uzel nejvyšší úrovně projektu.

1. Na řádku nabídek zvolte **zobrazení**, **stránky vlastností**.
  
     **Návrhář projektu** otevře.

1. Na **zkompilovat** vyberte **zakázat všech upozornění** zaškrtávací políčko.
  
     ![Stránka kompilovat, Návrhář projektu](../ide/media/buildwalk_vbsupresswarnings.png "BuildWalk_VBSupressWarnings")  
  
     Další informace najdete v tématu [Konfigurace upozornění v jazyce Visual Basic](../ide/configuring-warnings-in-visual-basic.md).

1. Sestavte řešení.
  
 **Výstup** okně zobrazí pouze souhrnné informace o sestavení.
  
 ![Okno výstup, Visual Basic sestavení upozornění](../ide/media/buildwalk_visualbasicbuildwarnings.png "BuildWalk_VisualBasicBuildWarnings")  
  
 Další informace najdete v tématu [postupy: potlačení upozornění kompilátoru](../ide/how-to-suppress-compiler-warnings.md).
  
## <a name="display-additional-build-details-in-the-output-window"></a>Zobrazení podrobností o další sestavení v okně výstupu

Kolik informace o procesu sestavení se zobrazí v, můžete změnit **výstup** okno. Sestavení podrobností je obvykle nastavené na minimální, to znamená, že **výstup** okně zobrazí pouze souhrn procesu sestavení spolu s vysokou prioritou nějakým chybám. Další informace o sestavení můžete zobrazit pomocí [dialogové okno Možnosti, projekty a řešení, sestavení a spuštění](../ide/reference/options-dialog-box-projects-and-solutions-build-and-run.md).
  
> [!IMPORTANT]
>  Zobrazíte další informace, sestavení bude trvat delší dobu.
  
### <a name="to-change-the-amount-of-information-in-the-output-window"></a>Chcete-li změnit množství informací v okně výstupu

1. Otevřete **možnosti** dialogové okno.
  
     ![Možnosti příkazu v nabídce Nástroje pro](../ide/media/exploreide-toolsoptionsmenu.png "ExploreIDE ToolsOptionsmenu")  

1. Vyberte **projekty a řešení** kategorie a potom zvolte **sestavit a spustit** stránky.

1. V **výstup sestavení projektu MSBuild podrobností** vyberte **normální**a potom zvolte **OK** tlačítko.

1. Na řádku nabídek zvolte **sestavení**, **Vyčistit řešení**.

1. Sestavte řešení a poté zkontrolujte informace v **výstup** okno.
  
     Informace o sestavení zahrnuje při spuštění sestavení (umístěný na začátku) a pořadí, ve které byly zpracovány soubory. Tyto informace zahrnují také syntaxi skutečné kompilátoru Visual Studio spustí během sestavení.
  
     Například v C# sestavení [/nowarn](/dotnet/visual-basic/reference/command-line-compiler/nowarn) možnost uvádí kód upozornění 1762, který jste zadali dříve v tomto tématu, společně s tři další upozornění.
  
     V sestavení jazyka Visual Basic [/nowarn](/dotnet/visual-basic/reference/command-line-compiler/nowarn) neobsahuje konkrétní varování, pokud chcete vyloučit, takže se žádná upozornění.
  
    > [!TIP]
    > Můžete hledat obsah **výstup** okna, je-li je zobrazit **najít** dialogové okno Vybrat klávesy Ctrl + F.

Další informace najdete v tématu [postupy: zobrazení, ukládání a konfigurace souborů protokolu sestavení](../ide/how-to-view-save-and-configure-build-log-files.md).
  
## <a name="create-a-release-build"></a>Vytváření sestavení pro vydání

Verzi ukázkové aplikace, která je optimalizovaná pro přesouvání je možné vytvořit. Pro sestavení pro vydání budete zadejte, zda spustitelný soubor před sestavení je spuštěna zkopírován do sdílené síťové složky.

Další informace najdete v tématu [postupy: Změna výstupního adresáře sestavení](../ide/how-to-change-the-build-output-directory.md) a [sestavování a čištění projektů a řešení v sadě Visual Studio](../ide/building-and-cleaning-projects-and-solutions-in-visual-studio.md).

### <a name="to-specify-a-release-build-for-visual-basic"></a>Chcete-li určit sestavení pro vydání jazyka Visual Basic

1. Otevřete **Návrhář projektu**.
  
     ![Nabídka Zobrazit příkaz – stránky vlastností](../ide/media/buildwalk_viewpropertypages.png "BuildWalk_ViewPropertyPages")  

1. Vyberte **zkompilovat** stránky.

1. V **konfigurace** vyberte **verze**.

1. V **platformy** vyberte **x86**.

1. V **sestavení výstupní cesta** zadejte síťovou cestu.

     Například můžete zadat \\\myserver\builds.

    > [!IMPORTANT]
    > Okno se zprávou se může zobrazit upozornění, že sdílené síťové složce, který jste zadali, nemusí být důvěryhodném umístění. Pokud důvěřujete umístění, které jste zadali, vyberte **OK** tlačítka v okně zprávy.

1. Sestavení aplikace.

     ![Sestavit řešení – příkaz v nabídce sestavení](../ide/media/exploreide-buildsolution.png "ExploreIDE BuildSolution")  

### <a name="to-specify-a-release-build-for-c"></a>Chcete-li určit sestavení pro vydání pro jazyk C# #

1. Otevřete **Návrhář projektu**.
  
     ![Nabídka Zobrazit příkaz – stránky vlastností](../ide/media/buildwalk_viewpropertypages.png "BuildWalk_ViewPropertyPages")  

1. Vyberte **sestavení** stránky.

1. V **konfigurace** vyberte **verze**.

1. V **platformy** vyberte **x86**.

1. V **výstupní cesta** zadejte síťovou cestu.
  
     Například můžete zadat \\\myserver\builds.
  
    > [!IMPORTANT]
    > Okno se zprávou se může zobrazit upozornění, že sdílené síťové složce, který jste zadali, nemusí být důvěryhodném umístění. Pokud důvěřujete umístění, které jste zadali, vyberte **OK** tlačítka v okně zprávy.

1. Na **standardním panelu nástrojů**, nastavte konfiguraci řešení **verze** a řešení platformy jako **x86**.

1. Sestavení aplikace.

     ![Sestavit řešení – příkaz v nabídce sestavení](../ide/media/exploreide-buildsolution.png "ExploreIDE BuildSolution")  

   Spustitelný soubor zkopírován do cesty sítě, který jste zadali. Jeho cesta by byla \\\myserver\builds\\*FileName*.exe.

Blahopřejeme: jste úspěšně dokončit tento postup.
  
## <a name="see-also"></a>Viz také

[Návod: Sestavení projektu (C++)](/cpp/ide/walkthrough-building-a-project-cpp)  
[Předkompilace Přehled projektu ASP.NET – webové aplikace](http://msdn.microsoft.com/b940abbd-178d-4570-b441-52914fa7b887)  
[Návod: Použití nástroje MSBuild](../msbuild/walkthrough-using-msbuild.md)
