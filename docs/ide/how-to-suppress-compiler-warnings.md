---
title: "Postupy: potlačení upozornění kompilátoru | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 31827b17-f933-413d-b28a-b19f903b64ca
caps.latest.revision: "5"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: d97695cae08352ea213ba02008ab99bef7f61c47
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-suppress-compiler-warnings"></a>Postupy: Potlačení upozornění kompilátoru
Zadáním jednoho nebo více druhů upozornění kompilátoru, že nechcete, aby mohla obsahovat můžete declutter protokolu sestavení. Například můžete použít tento postup, chcete-li zkontrolovat některé, ale ne všechny informace, které se automaticky vygeneruje při nastavení podrobností protokolu sestavení na normální, podrobnosti nebo diagnostiky. Další informace o podrobností najdete v tématu [postupy: zobrazení, ukládání a konfigurace souborů protokolu sestavení](../ide/how-to-view-save-and-configure-build-log-files.md).  
  
### <a name="to-suppress-specific-warnings-for-visual-c-or-f"></a>Chcete-li potlačit konkrétní varování pro Visual C# nebo F # #
  
1.  V **Průzkumníku**, zvolte projektu, ve kterém chcete potlačení upozornění.  
  
2.  Na řádku nabídek zvolte **zobrazení**, **stránky vlastností**.  
  
3.  Vyberte **sestavení** stránky.  
  
4.  V **potlačení upozornění** pole, zadejte kódy chyb, upozornění, která chcete potlačit, oddělené středníky a pak znovu sestavte řešení.  
  
### <a name="to-suppress-specific-warnings-for-visual-c"></a>Chcete-li potlačit konkrétní varování pro Visual C++  
  
1.  V **Průzkumníku**, zvolte projekt nebo zdrojového souboru, ve kterém chcete potlačení upozornění.  
  
2.  Na řádku nabídek zvolte **zobrazení**, **stránky vlastností**.  
  
3.  Vyberte **vlastnosti konfigurace** kategorie, vyberte **C/C++** kategorie a potom zvolte **Upřesnit** stránky.  
  
4.  Proveďte jeden z následujících kroků:  
  
    -   V **zakázat konkrétní varování** zadejte kódy chyb, upozornění, která chcete potlačit, oddělených středníkem.  
  
    -   V **zakázat konkrétní varování** vyberte **upravit** zobrazíte další možnosti.  
  
5.  Vyberte **OK** tlačítko a pak znovu sestavte řešení.  
  
## <a name="suppressing-warnings-for-visual-basic"></a>Potlačení upozornění v jazyce Visual Basic  
 Upozornění konkrétní kompilátoru jazyka Visual Basic můžete skrýt, a to úpravou souboru .vbproj pro projekt. Můžete také [stránka kompilovat, Návrhář projektu](../ide/reference/compile-page-project-designer-visual-basic.md) k potlačení upozornění podle kategorie. Další informace najdete v tématu [Konfigurace upozornění v jazyce Visual Basic](../ide/configuring-warnings-in-visual-basic.md).  
  
#### <a name="to-suppress-specific-warnings-for-visual-basic"></a>Chcete-li potlačit konkrétní varování jazyka Visual Basic  
  
1.  V **Průzkumníku**, zvolte projektu, ve kterém chcete potlačení upozornění.  
  
2.  Na řádku nabídek zvolte **projektu**, **uvolnit projekt**.  
  
3.  V **Průzkumníku řešení**, otevřete místní nabídky projektu a zvolte **upravit***ProjectName***.vbproj**.  
  
     Soubor projektu je otevřen v editoru kódu.  
  
4.  Vyhledejte `<NoWarn></NoWarn>` element v konfiguraci sestavení, se kterou vytváříte.  
  
     Následující příklad ukazuje `<NoWarn></NoWarn>` element tučným písmem pro konfiguraci ladění sestavení na x86 platformy:  
  
    ```  
    <PropertyGroup Condition=" '$(Configuration)|$(Platform)' == 'Debug|x86' ">  
        <PlatformTarget>x86</PlatformTarget>  
        <DebugSymbols>true</DebugSymbols>  
        <DebugType>full</DebugType>  
        <Optimize>false</Optimize>  
        <OutputPath>bin\Debug\</OutputPath>  
        <DefineDebug>true</DefineDebug>  
        <DefineTrace>true</DefineTrace>  
        <ErrorReport>prompt</ErrorReport>  
        <NoWarn></NoWarn>  
        <WarningLevel>1</WarningLevel>  
      </PropertyGroup>  
    ```  
  
5.  Přidejte jedno nebo více čísel upozornění jako hodnotu `<NoWarn>` elementu. Pokud zadáte více čísel upozornění, oddělte je čárkou, jak ukazuje následující příklad.  
  
    ```  
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
  
6.  Uložte změny do souboru .vbproj.  
  
7.  Na řádku nabídek zvolte **projektu**, **znovu načíst projekt**.  
  
8.  Na řádku nabídek zvolte **sestavení**, **znovu sestavit řešení**.  
  
     **Výstup** okno přestane zobrazovat upozornění, která jste zadali.  
  
 Další informace najdete v tématu [/nowarn](/dotnet/visual-basic/reference/command-line-compiler/nowarn).  
  
## <a name="see-also"></a>Viz také  
 [Návod: Vytvoření aplikace](../ide/walkthrough-building-an-application.md)   
 [Postupy: zobrazení, uložit a konfigurace souborů protokolu sestavení](../ide/how-to-view-save-and-configure-build-log-files.md)   
 [Kompilace a sestavení](../ide/compiling-and-building-in-visual-studio.md)
