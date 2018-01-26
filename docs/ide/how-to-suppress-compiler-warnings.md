---
title: "Potlačení upozornění kompilátoru v sadě Visual Studio pro projekty a balíčky NuGet | Microsoft Docs"
ms.custom: 
ms.date: 01/24/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 868e3be3dc789928fe061d236cdc7a0971d49c71
ms.sourcegitcommit: 69b898d8d825c1a2d04777abf6d03e03fefcd6da
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2018
---
# <a name="how-to-suppress-compiler-warnings"></a>Postupy: potlačení upozornění kompilátoru

Pomocí filtrování na jeden nebo více druhů upozornění kompilátoru můžete declutter protokolu sestavení. Například můžete chtít zkontrolovat jenom některé z výstupu, který se vygeneruje, když nastavíte podrobností protokolu sestavení na normální, podrobnosti nebo diagnostiky. Další informace o podrobností najdete v tématu [postupy: zobrazení, uložit a konfigurace souborů protokolu sestavení](../ide/how-to-view-save-and-configure-build-log-files.md).

## <a name="suppressing-specific-warnings-for-visual-c-or-f"></a>Potlačení upozornění specifické pro Visual C# nebo F # #

Použití **sestavení** na stránce vlastností potlačení konkrétní upozornění pro projekty C# a F #.

1. V **Průzkumníku**, zvolte projektu, ve kterém chcete potlačení upozornění.

1. Na řádku nabídek zvolte **zobrazení** > **stránky vlastností**.

1. Vyberte **sestavení** stránky.

1. V **potlačení upozornění** zadejte kódy chyb, upozornění, která chcete potlačit, oddělené středníky.

1. Znovu sestavte řešení.

## <a name="suppressing-specific-warnings-for-visual-c"></a>Potlačení upozornění specifické pro Visual C++

Použití **vlastnosti konfigurace** potlačení konkrétní upozornění pro projekty C++ na stránce vlastností.

1. V **Průzkumníku**, zvolte projekt nebo zdrojového souboru, ve kterém chcete potlačení upozornění.

1. Na řádku nabídek zvolte **zobrazení** > **stránky vlastností**.

1. Vyberte **vlastnosti konfigurace** kategorie, vyberte **C/C++** kategorie a potom zvolte **Upřesnit** stránky.

1. Proveďte jeden z následujících kroků:

    - V **zakázat konkrétní varování** zadejte kódy chyb, upozornění, která chcete potlačit, oddělených středníkem.

    - V **zakázat konkrétní varování** vyberte **upravit** zobrazíte další možnosti.

1. Vyberte **OK** tlačítko a pak znovu sestavte řešení.

## <a name="suppressing-warnings-for-visual-basic"></a>Potlačení upozornění v jazyce Visual Basic

Upozornění konkrétní kompilátoru jazyka Visual Basic můžete skrýt, a to úpravou *.vbproj* soubor projektu. Potlačit upozornění podle *kategorie*, můžete použít [stránka vlastností kompilace](../ide/reference/compile-page-project-designer-visual-basic.md). Další informace najdete v tématu [Konfigurace upozornění v jazyce Visual Basic](../ide/configuring-warnings-in-visual-basic.md).

### <a name="to-suppress-specific-warnings-for-visual-basic"></a>Chcete-li potlačit konkrétní varování jazyka Visual Basic

Tento příklad ukazuje, jak upravit *.vbproj* potlačení upozornění kompilátoru konkrétní soubor.

1. V **Průzkumníku**, zvolte projektu, ve kterém chcete potlačení upozornění.

1. Na řádku nabídek zvolte **projektu** > **uvolnit projekt**.

1. V **Průzkumníku řešení**, otevřete v klikněte pravým tlačítkem nebo v místní nabídce pro projekt a zvolte **upravit** *ProjectName* **.vbproj**.

    Soubor XML projekt se otevře v editoru kódu.

1. Vyhledejte `<NoWarn>` element pro konfiguraci sestavení můžete sestavujete s a přidat jeden nebo více upozornění čísla jako hodnotu `<NoWarn>` elementu. Pokud zadáte více čísel upozornění, oddělte je čárkou.

     Následující příklad ukazuje `<NoWarn>` element pro *ladění* konfigurace na x86 sestavení platformy s dvěma upozornění kompilátoru potlačeno:

    ```xml
    <PropertyGroup Condition=" '$(Configuration)|$(Platform)' == 'Debug|x86' ">
        <PlatformTarget>x86</PlatformTarget>
        <DebugSymbols>true</DebugSymbols>
        <DebugType>full</DebugType>
        <Optimize>false</Optimize>
        <OutputPath>bin\Debug\</OutputPath>
        <DefineDebug>true</DefineDebug>
        <DefineTrace>true</DefineTrace>
        <ErrorReport>prompt</ErrorReport>
        <NoWarn>40059,42024</NoWarn>
        <WarningLevel>1</WarningLevel>
      </PropertyGroup>
    ```

   > [!NOTE]
   > .NET core projekty neobsahují sestavení konfigurace vlastností skupiny ve výchozím nastavení. Potlačit upozornění v projektu .NET Core, přidejte do souboru ručně sestavení konfigurační oddíl. Příklad:
   >
   > ```xml
   > <Project Sdk="Microsoft.NET.Sdk">
   >   <PropertyGroup>
   >     <OutputType>Exe</OutputType>
   >     <TargetFramework>netcoreapp2.0</TargetFramework>
   >     <RootNamespace>VBDotNetCore_1</RootNamespace>
   >   </PropertyGroup>
   >   <PropertyGroup Condition=" '$(Configuration)|$(Platform)' == 'Debug|AnyCPU' ">
   >     <NoWarn>42016,41999,42017</NoWarn>
   >   </PropertyGroup>
   > </Project>
   > ```

1. Uložit změny *.vbproj* souboru.

1. Na řádku nabídek zvolte **projektu** > **znovu načíst projekt**.

1. Na řádku nabídek zvolte **sestavení** > **znovu sestavit řešení**.

    **Výstup** okno přestane zobrazovat upozornění, která jste zadali.

Další informace najdete v tématu [/nowarn) – možnost kompilátoru](/dotnet/visual-basic/reference/command-line-compiler/nowarn) pro Visual Basic – kompilátor příkazového řádku.

## <a name="suppressing-warnings-for-nuget-packages"></a>Potlačení upozornění pro balíčky NuGet

V některých případech můžete chtít potlačení upozornění kompilátoru NuGet pro jeden balíček NuGet, ne pro celý projekt. Upozornění slouží účelu, takže nechcete potlačit na úrovni projektu. Například jedna NuGet upozornění, zjistíte, balíček nemusí být plně kompatibilní s projektem. Pokud můžete potlačit na úrovni projektu a později přidat další balíčky NuGet, by nikdy vědět, pokud vyrábí kompatibility upozornění.

### <a name="to-suppress-a-specific-warning-for-a-single-nuget-package"></a>Zvláštní upozornění pro jeden balíček NuGet potlačit

1. V **Průzkumníku**, vyberte balíček NuGet, který chcete potlačení upozornění kompilátoru pro.

   ![Balíček NuGet v Průzkumníku řešení](media/nuget-package-with-warning.png)

1. V nabídce klikněte pravým tlačítkem nebo kontextu vyberte **vlastnosti**.

1. V **NoWarn** pole vlastností balíčku, zadejte číslo upozornění, která chcete potlačit pro tento balíček. Pokud chcete více než jeden upozornění potlačit, použijte k oddělení čísel upozornění čárkou.

   ![Vlastnosti balíčku NuGet](media/nuget-properties-nowarn.png)

   Upozornění na dané zařízení zmizí z **Průzkumníku řešení** a **seznam chyb**.

## <a name="see-also"></a>Viz také

[Návod: Sestavení aplikace](../ide/walkthrough-building-an-application.md)  
[Postupy: Zobrazování, ukládání a konfigurace souborů protokolu sestavení](../ide/how-to-view-save-and-configure-build-log-files.md)  
[Kompilace a sestavení](../ide/compiling-and-building-in-visual-studio.md)
