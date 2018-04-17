---
title: Přidání příkazu na panelu nástrojů Průzkumníka řešení | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- toolbars [Visual Studio], adding buttons
- buttons [Visual Studio], adding to Solution Explorer
- Solution Explorer, adding buttons
ms.assetid: f6411557-2f4b-4e9f-b02e-fce12a6ac7e9
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f6f732900ff3e73decb1dc01d5c131e26ba50669
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="adding-a-command-to-the-solution-explorer-toolbar"></a>Přidání příkazu na panelu nástrojů Průzkumník řešení
Tento návod ukazuje, jak přidat tlačítko **Průzkumníku řešení** panelu nástrojů.  
  
 Libovolnému příkazu panelu nástrojů nebo nabídky se nazývá tlačítka v sadě Visual Studio. Při kliknutí na tlačítko se spustí kód v obslužná rutina příkazu. Související příkazy jsou obvykle seskupeny dohromady tvoří jednu skupinu. Nabídek a panelů nástrojů fungují jako kontejnery pro skupiny. Priorita určuje pořadí, ve kterém se zobrazují jednotlivé příkazy ve skupině v nabídce nebo na panelu nástrojů. Můžete zabránit tlačítko se zobrazí na panelu nástrojů nebo v nabídce kontrolou jeho viditelnosti. Příkaz, který je uveden v `<VisibilityConstraints>` .vsct souboru se objeví jen v kontextu, přidružené. Viditelnost nelze použít pro skupiny.  
  
 Další informace o nabídek, příkazy nástrojů a .vsct souborů najdete v tématu [příkazy, nabídek a panelů nástrojů](../extensibility/internals/commands-menus-and-toolbars.md).  
  
> [!NOTE]
>  Určuje způsob zobrazení nabídek a příkazů vaší VSPackages pomocí souborů XML příkaz tabulky (.vsct) místo soubory konfigurace (.ctc) tabulky příkazů. Další informace najdete v tématu [tabulky příkaz Visual Studio (. Soubory Vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md).  
  
## <a name="prerequisites"></a>Požadavky  
 Od sady Visual Studio 2015 se neinstalovat sadu Visual Studio SDK z webu Stažení softwaru. Je zahrnuta jako volitelná funkce v instalačním programu sady Visual Studio. VS SDK můžete také nainstalovat později. Další informace najdete v tématu [instalace sady Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="creating-an-extension-with-a-menu-command"></a>Vytvoření rozšíření pomocí příkazu nabídky  
 Vytvoření projektu VSIX s názvem `SolutionToolbar`. Přidat šablonu položky příkaz nabídky s názvem **ToolbarButton**. Informace o tom, jak to udělat najdete v tématu [vytvoření rozšíření pomocí příkazu v nabídce](../extensibility/creating-an-extension-with-a-menu-command.md).  
  
## <a name="adding-a-button-to-the-solution-explorer-toolbar"></a>Přidání tlačítka na panelu nástrojů Průzkumník řešení  
 Tato část průvodce ukazuje, jak přidat tlačítko **Průzkumníku řešení** panelu nástrojů. Při kliknutí na tlačítko Spustit je kód v metodě zpětného volání.  
  
1.  V souboru ToolbarButtonPackage.vsct, přejděte na `<Symbols>` oddílu. `<GuidSymbol>` Uzel obsahuje skupiny nabídek a příkaz, který byl vygenerován balíčku šablony. Přidat `<IDSymbol>` element pro tento uzel deklarovat skupině, která bude obsahovat příkazu.  
  
    ```xml  
    <IDSymbol name="SolutionToolbarGroup" value="0x0190"/>  
    ```  
  
2.  V `<Groups>` části existující položku skupiny, zadejte novou skupinu, kterou je deklarován v předchozím kroku.  
  
    ```xml  
    <Group guid="guidToolbarButtonPackageCmdSet"  
           id="SolutionToolbarGroup" priority="0xF000">  
            <Parent guid="guidSHLMainMenu" id="IDM_VS_TOOL_PROJWIN"/>  
          </Group>  
    ```  
  
     Nastavení nadřazené pár GUID:ID na `guidSHLMainMenu` a `IDM_VS_TOOL_PROJWIN` vloží této skupiny **Průzkumníku řešení** nástrojů a nastavení hodnoty s vysokou prioritou vloží ho po další příkaz skupiny.  
  
3.  V `<Buttons>` změňte ID nadřazeného generované `<Button>` položky tak, aby odrážela skupiny, který jste zadali v předchozím kroku. Upravenou `<Button>` element by měla vypadat takto:  
  
    ```xml  
    <Button guid="guidToolbarButtonPackageCmdSet" id="ToolbarButtonId" priority="0x0100" type="Button">  
        <Parent guid="guidToolbarButtonPackageCmdSet" id="SolutionToolbarGroup" />  
        <Icon guid="guidImages" id="bmpPicStrikethrough" />  
        <Strings>  
            <ButtonText>Invoke ToolbarButton</ButtonText>  
        </Strings>  
    </Button>  
    ```  
  
4.  Sestavte projekt a spusťte ladění. Zobrazí se experimentální instanci.  
  
     **Průzkumníku řešení** panelu nástrojů pro napravo od tlačítka existující zobrazeno tlačítko Nový příkaz. Ikona tlačítko je přeškrtnutí.  
  
5.  Klikněte na tlačítko Nový.  
  
     Dialogové okno zprávy **ToolbarButtonPackage uvnitř SolutionToolbar.ToolbarButton.MenuItemCallback()** má být zobrazen.  
  
## <a name="controlling-the-visibility-of-a-button"></a>Ovládání viditelnosti tlačítka  
 Tato část průvodce ukazuje, jak řídit zobrazení tlačítka na panelu nástrojů. Nastavením kontextu na jeden nebo více projektů `<VisibilityConstraints>` části souboru SolutionToolbar.vsct omezíte tlačítko zobrazí, jenom když na projekt nebo projekty jsou otevřené.  
  
#### <a name="to-display-a-button-when-one-or-more-projects-are-open"></a>K zobrazení tlačítka, když jeden nebo více projektů jsou otevřené  
  
1.  V `<Buttons>` části ToolbarButtonPackage.vsct, přidat dvěma příznaky příkazu ke stávající `<Button>` element, mezi `<Strings>` a `<Icons>` značky.  
  
    ```xml  
    <CommandFlag>DefaultInvisible</CommandFlag>  
    <CommandFlag>DynamicVisibility</CommandFlag>  
    ```  
  
     `DefaultInvisible` a `DynamicVisibility` příznaky musí být nastaven tak této položky v `<VisibilityConstraints>` části se projeví.  
  
2.  Vytvoření `<VisibilityConstraints>` oddíl, který má dva `<VisibilityItem>` položky. Uveďte novou část právě po zavření `</Commands>` značky.  
  
    ```xml  
    <VisibilityConstraints>  
        <VisibilityItem guid="guidToolbarButtonPackageCmdSet"  
              id="ToolbarButtonId"  
              context="UICONTEXT_SolutionHasSingleProject" />  
        <VisibilityItem guid="guidToolbarButtonPackageCmdSet"  
              id="ToolbarButtonId"  
              context="UICONTEXT_SolutionHasMultipleProjects" />  
    </VisibilityConstraints>  
    ```  
  
     Každá položka viditelnost představuje pod kterým se zobrazí tlačítko zadanou podmínku. Pokud chcete nainstalovat více podmínek, musíte vytvořit několik záznamů pro stejný tlačítko.  
  
3.  Sestavte projekt a spusťte ladění. Zobrazí se experimentální instanci.  
  
     **Průzkumníku řešení** panelu nástrojů na tlačítko přeškrtnutí neobsahuje.  
  
4.  Otevřete řešení obsahující projekt.  
  
     Tlačítko přeškrtnutí se zobrazí na panelu nástrojů napravo od existující tlačítek.  
  
5.  Na **soubor** nabídky, klikněte na tlačítko **zavřít řešení**. Tlačítko dané zařízení zmizí z panelu nástrojů.  
  
 Viditelnost tlačítko řídí [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] dokud VSPackage je načtena. Po načtení VSPackage viditelnost tlačítko řídí VSPackage.  Další informace najdete v tématu [MenuCommands Vs. OleMenuCommands](../extensibility/menucommands-vs-olemenucommands.md).  
  
## <a name="see-also"></a>Viz také  
 [Příkazy, nabídky a panely nástrojů](../extensibility/internals/commands-menus-and-toolbars.md)