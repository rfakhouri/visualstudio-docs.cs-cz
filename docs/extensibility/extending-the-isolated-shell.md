---
redirect_url: shell/extending-the-isolated-shell
title: "Rozšíření izolované prostředí | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Visual Studio shell, isolated mode
ms.assetid: 9a641d8f-211e-4486-a1b1-4a89fafe7ee8
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: fffa21e0351b6516920700d8dde0ba8b43243a9a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="extending-the-isolated-shell"></a>Rozšíření izolované prostředí
Prostředí sady Visual Studio izolované můžete rozšířit přidáním VSPackage, součást Managed Extensibility Framework (MEF) nebo obecné VSIX projektu do aplikace izolované prostředí.  
  
> [!NOTE]
>  Následující kroky předpokládají, že jste vytvořili základní izolované prostředí aplikace pomocí šablony projektu Visual Studio Shell izolované. Další informace o této šablony projektu najdete v tématu [návod: vytvoření základní aplikace izolované prostředí](../extensibility/walkthrough-creating-a-basic-isolated-shell-application.md).  
  
## <a name="locations-for-the-visual-studio-package-project-template"></a>Umístění pro šablony sady Visual Studio balíčku projektu  
 Šablona projektu balíček Visual Studio najdete ve třech různých umístěních v **nový projekt** dialogové okno:  
  
1.  V části **jazyka Visual Basic**, **rozšiřitelnost**. Je výchozí jazyk projektu jazyka Visual Basic.  
  
2.  V části **Visual C#**, **rozšiřitelnost**. Je výchozí jazyk projektu C#.  
  
3.  V části **jiné typy projektů**, **rozšiřitelnost**. Výchozí jazyk projektu je C++.  
  
## <a name="adding-a-vspackage"></a>Přidání VSPackage  
 VSPackage můžete přidat do vaší aplikace izolované prostředí. Následující kroky ukazují, jak vytvořit takový, který přidá příkazy nabídky.  
  
#### <a name="to-add-a-new-vspackage"></a>Chcete-li přidat nový VSPackage  
  
1.  Přidejte balíček Visual Studio projektu s názvem `MenuCommandsPackage`.  
  
2.  Na **základní informace VSPackage** stránce průvodce, nastavte **název společnosti** k `Fabrikam` a **VSPackage název** k `FabrikamMenuCommands`. Vyberte **Další** tlačítko.  
  
3.  Na další stránce vyberte **příkaz nabídky** a potom zvolte **Další**.  
  
4.  Na další stránce, nastavte **název příkazu** k `Fabrikam Command` a **ID příkazu** k `cmdidFabrikamCommand`a potom zvolte **Další**.  
  
5.  Na **vyberte možnosti testování projektu** stránky, zrušte zaškrtnutí možnosti testování a potom vyberte **Dokončit** tlačítko.  
  
6.  V projektu ShellExtensionsVSIX otevřete soubor source.extension.vsixmanifest.  
  
     **Prostředky** oddíl by měl obsahovat položku pro VSShellStub.AboutBoxPackage projektu.  
  
7.  Vyberte **nový** tlačítko.  
  
8.  V **přidat nový prostředek** okno v **typ** seznamu, vyberte **Microsoft.VisualStudio.VsPackage**.  
  
9. V **zdroj** seznamu, ujistěte se, že **na projekt v aktuálním řešení** je vybrána. V **projektu** pole se seznamem, vyberte **MenuCommandsPackage**.  
  
10. Soubor uložte a zavřete.  
  
11. Znovu sestavte řešení a spuštění ladění izolované prostředí.  
  
12. Na řádku nabídek zvolte **nástroje** nabídky, pak **Fabrikam příkaz**.  
  
     By se zobrazit okno se zprávou.  
  
13. Zastavte ladění aplikace.  
  
## <a name="adding-a-mef-component-part"></a>Přidání součást MEF  
 Následující kroky ukazují, jak přidat součást MEF do aplikace izolované prostředí.  
  
#### <a name="to-add-a-mef-component"></a>Přidat součást MEF  
  
1.  V **přidat nový projekt** dialogovém **Visual C#**, **rozšiřitelnost**, použijte **okraj editoru** šablony přidat projekt. Pojmenujte ji `ShellEditorMargin`.  
  
2.  V projektu ShellExtensionsVSIX otevřete soubor Source.extension.vsixmanifest v zobrazení návrhu zobrazení kódu.  
  
3.  V `Asset` zvolte **přidat obsahu**.  
  
4.  V **přidat nový prostředek** okno v **typ** seznamu, vyberte **Microsoft.VisualStudio.MefComponent**.  
  
5.  V **zdroj** seznamu, ujistěte se, že **na projekt v aktuálním řešení** je vybrána. V **projektu** pole se seznamem, vyberte **ShellEditorMargin**.  
  
6.  Soubor uložte a zavřete.  
  
7.  Znovu sestavte řešení a spuštění ladění izolované prostředí.  
  
8.  Otevřete textový soubor.  
  
     Zelená okraj, který obsahuje slova "Hello, world!" má být zobrazena v dolní části okna textového souboru.  
  
9. Zastavte ladění aplikace.  
  
## <a name="adding-a-generic-vsix-project"></a>Přidání projektu obecné VSIX  
  
#### <a name="to-add-a-generic-vsix-project"></a>Chcete-li přidat obecné projektu VSIX  
  
1.  V **přidat nový projekt** dialogovém **Visual C#**, **rozšiřitelnost**, použijte **VSIXProject** šablony přidat projekt. Pojmenujte ji `EmptyVSIX`.  
  
2.  V projektu ShellExtensionsVSIX otevřete soubor Source.extensions.vsixmanifest v zobrazení návrhu zobrazení kódu.  
  
3.  V `Assets` zvolte **nový**.  
  
4.  V **přidat nový prostředek** okno v **typ** vyberte obsahu, který chcete přidat.  
  
5.  V **zdroj**, ujistěte se, že **na projekt v aktuálním řešení** je vybraná možnost. V seznamu vyberte název projektu VSIX.  
  
6.  Soubor uložte a zavřete.  
  
7.  Pokud tento projekt obsahuje zkompilovaný kód, je nutné upravit projekt tak, aby sestavení je zahrnutá ve výstupu.  
  
    1.  Uvolnit projekt VSIX a otevřete soubor projektu.  
  
    2.  V prvním `<PropertyGroup>` blokovat, změňte hodnotu `<CopyBuildOutputToOutputDirectory>` k `true`.  
  
    3.  Uložte a projekt znovu načíst.  
  
8.  Sestavení a spuštění řešení.  
  
## <a name="see-also"></a>Viz také  
 [Návod: Vytvoření základní aplikace izolovaného prostředí](../extensibility/walkthrough-creating-a-basic-isolated-shell-application.md)