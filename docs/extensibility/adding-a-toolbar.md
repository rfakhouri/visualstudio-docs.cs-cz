---
title: "Přidávání panelů nástrojů | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- toolbars [Visual Studio], adding to IDE
- IDE, adding toolbars
ms.assetid: 17302c25-6f59-4e97-8c85-54f95336a07f
caps.latest.revision: "38"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: da6ea8eac18151f0efbaefb3e9f910b695630669
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="adding-a-toolbar"></a>Přidávání panelů nástrojů
Tento návod ukazuje, jak přidat panel nástrojů k prostředí Visual Studio IDE.  
  
 Panel nástrojů je vodorovné nebo svislé pruhu, který obsahuje tlačítka, které jsou vázány na příkazy. V závislosti na jeho implementace panelu nástrojů v prostředí IDE může být změnit jejich umístění, ukotveno na žádné straně hlavního okna IDE nebo se zůstat okna.  
  
 Kromě toho můžete uživatelům přidání příkazů na panel nástrojů nebo odebrání z něj pomocí **přizpůsobit** dialogové okno. Panely nástrojů v VSPackages jsou obvykle přizpůsobitelné uživatele. Zpracovává všechny přizpůsobení integrovaného vývojového prostředí a VSPackage reaguje na příkazy. VSPackage nemá vědět, kde je příkaz fyzicky nacházejí.  
  
 Další informace o nabídkách najdete v tématu [příkazy, nabídek a panelů nástrojů](../extensibility/internals/commands-menus-and-toolbars.md).  
  
## <a name="prerequisites"></a>Požadavky  
 Od sady Visual Studio 2015 se neinstalovat sadu Visual Studio SDK z webu Stažení softwaru. Je zahrnuta jako volitelná funkce v instalačním programu sady Visual Studio. VS SDK můžete také nainstalovat později. Další informace najdete v tématu [instalace sady Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="creating-an-extension-with-a-toolbar"></a>Vytvoření rozšíření pomocí panelu nástrojů  
 Vytvoření projektu VSIX s názvem `IDEToolbar`. Přidat šablonu položky příkaz nabídky s názvem **ToolbarTestCommand**. Informace o tom, jak to udělat najdete v tématu [vytvoření rozšíření pomocí příkazu v nabídce](../extensibility/creating-an-extension-with-a-menu-command.md).  
  
## <a name="creating-a-toolbar-for-the-ide"></a>Vytváření panelů nástrojů pro prostředí IDE  
  
1.  V ToolbarTestCommandPackage.vsct vyhledejte v části symboly. V elementu GuidSymbol s názvem guidToolbarTestCommandPackageCmdSet přidejte deklarace pro panel nástrojů a skupinu nástrojů, následujícím způsobem.  
  
    ```xml  
    <IDSymbol name="Toolbar" value="0x1000" />  
    <IDSymbol name="ToolbarGroup" value="0x1050" />  
  
    ```  
  
2.  V horní části příkazy vytvořte části nabídky. Přidáte Menu element do části nabídky k definování panelu nástrojů.  
  
    ```xml  
    <Menus>  
        <Menu guid="guidToolbarTestCommandPackageCmdSet" id="Toolbar"  
            type="Toolbar" >  
            <CommandFlag>DefaultDocked</CommandFlag>  
            <Strings>  
                <ButtonText>Test Toolbar</ButtonText>  
                <CommandName>Test Toolbar</CommandName>  
            </Strings>  
          </Menu>  
    </Menus>  
    ```  
  
     Panely nástrojů nemůže být vnořena jako dílčích. Proto není potřeba přiřadit nadřazenou skupinu. Navíc nemáte nastavit prioritu, protože může uživatel přesunout panely nástrojů. Obvykle počáteční umístění panelu nástrojů je definována prostřednictvím kódu programu, ale následné změny uživatelem jsou nastavené jako trvalé.  
  
3.  V [skupiny](../extensibility/groups-element.md) části existující položku skupiny, definujte [skupiny](../extensibility/group-element.md) element tak, aby obsahovala příkazy k panelu nástrojů.  
  
    ```xml  
    <Group guid="guidToolbarTestCommandPackageCmdSet" id="ToolbarGroup"  
          priority="0x0000">  
      <Parent guid="guidToolbarTestCommandPackageCmdSet" id="Toolbar"/>  
    </Group>  
    ```  
  
4.  Ujistěte se, na tlačítko se zobrazí na panelu nástrojů. V části tlačítka nahraďte nadřazený blok v tlačítka panelu nástrojů. Výsledný bloku tlačítko by měl vypadat takto:  
  
    ```xml  
    <Button guid="guidToolbarTestCommandPackageCmdSet" id="ToolbarTestCommandId" priority="0x0100" type="Button">  
        <Parent guid= "guidToolbarTestCommandPackageCmdSet" id="ToolbarGroup" />  
                <Icon guid="guidImages" id="bmpPic1" />  
        <Strings>  
            <ButtonText>Invoke ToolbarTestCommand</ButtonText>  
        </Strings>  
    </Button>  
    ```  
  
     Ve výchozím nastavení Pokud má žádné příkazy, panelu nástrojů se nezobrazí.  
  
5.  Sestavte projekt a spusťte ladění. Experimentální instanci by se zobrazit.  
  
6.  Klikněte pravým tlačítkem na panelu nabídek Visual Studio k získání seznamu panely nástrojů. Vyberte **testování nástrojů**.  
  
7.  Teď byste měli vidět panelu nástrojů jako ikony napravo od najít v ikona souborů. Když kliknete na ikonu, měli byste vidět okno se zprávou, která uvádí, že **ToolbarTestCommandPackage. Uvnitř IDEToolbar.ToolbarTestCommand.MenuItemCallback()**.  
  
## <a name="see-also"></a>Viz také  
 [Příkazy, nabídek a panelů nástrojů](../extensibility/internals/commands-menus-and-toolbars.md)