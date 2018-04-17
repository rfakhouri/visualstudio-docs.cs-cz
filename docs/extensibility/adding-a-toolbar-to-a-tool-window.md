---
title: Přidávání panelů nástrojů do okno nástroje | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- tool windows, adding toolbars
- toolbars [Visual Studio], adding to tool windows
ms.assetid: 172f64b3-87f8-4292-9c1c-65bffa2b0970
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 47ff5f69ff559ea1c08d0ae9bdd7192a257c844e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="adding-a-toolbar-to-a-tool-window"></a>Přidávání panelů nástrojů do okno nástroje
Tento návod ukazuje, jak přidat panel nástrojů pro okno nástroje.  
  
 Panel nástrojů je vodorovné nebo svislé pruhu, který obsahuje tlačítka vázána na příkazy. Délka nástrojů v okně nástroje je vždy stejný jako šířky nebo výšky panel nástrojů, v závislosti na tom, kde je ukotvena panelu nástrojů.  
  
 Na rozdíl od panely nástrojů v prostředí IDE panelu nástrojů v okně nástroje musí být ukotvena a nelze přesunout nebo přizpůsobit. Pokud VSPackage je napsán v umanaged kódu, lze ukotvit panelu nástrojů na libovolný okraj.  
  
 Další informace o tom, jak přidat panel nástrojů najdete v tématu [přidávání panelů nástrojů](../extensibility/adding-a-toolbar.md).  
  
## <a name="prerequisites"></a>Požadavky  
 Od sady Visual Studio 2015 se neinstalovat sadu Visual Studio SDK z webu Stažení softwaru. Je zahrnuta jako volitelná funkce v instalačním programu sady Visual Studio. VS SDK můžete také nainstalovat později. Další informace najdete v tématu [instalace sady Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="creating-a-toolbar-for-a-tool-window"></a>Vytváření panelů nástrojů pro okno nástroje  
  
1.  Vytvoření projektu VSIX s názvem `TWToolbar` má oba příkazu nabídky s názvem **TWTestCommand** a v okně nástroje s názvem **TestToolWindow**. Další informace najdete v tématu [vytvoření rozšíření pomocí příkazu v nabídce](../extensibility/creating-an-extension-with-a-menu-command.md) a [vytváření rozšíření s okno nástroje](../extensibility/creating-an-extension-with-a-tool-window.md). Je nutné přidat šablony položky příkaz před přidáním šablona okno nástroje.  
  
2.  V TWTestCommandPackage.vsct vyhledejte v části symboly. V uzlu GuidSymbol s názvem guidTWTestCommandPackageCmdSet deklarujte panelu nástrojů a skupinu nástrojů, následujícím způsobem.  
  
    ```xml  
    <IDSymbol name="TWToolbar" value="0x1000" />  
    <IDSymbol name="TWToolbarGroup" value="0x1050" />  
    ```  
  
3.  V horní části `Commands` , vytvořte `Menus` části. Přidat `Menu` elementu, který chcete definovat panelu nástrojů.  
  
    ```xml  
    <Menus>  
        <Menu guid="guidTWTestCommandPackageCmdSet" id="TWToolbar" type="ToolWindowToolbar">  
            <CommandFlag>DefaultDocked</CommandFlag>  
            <Strings>  
                <ButtonText>Test Toolbar</ButtonText>  
                <CommandName>Test Toolbar</CommandName>  
            </Strings>  
        </Menu>  
    </Menus>  
    ```  
  
     Panely nástrojů nemůže být vnořena jako dílčích. Proto není potřeba přiřadit nadřazený. Navíc nemáte nastavit prioritu, protože může uživatel přesunout panely nástrojů. Obvykle počáteční umístění panelu nástrojů je definována prostřednictvím kódu programu, ale následné změny uživatelem jsou nastavené jako trvalé.  
  
4.  V části skupiny definujte skupinu tak, aby obsahovala příkazy k panelu nástrojů.  
  
    ```xml  
  
    <Group guid="guidTWTestCommandPackageCmdSet" id="TWToolbarGroup" priority="0x0000">  
        <Parent guid="guidTWTestCommandPackageCmdSet" id="TWToolbar" />  
    </Group>  
    ```  
  
5.  V části tlačítka změňte nadřazený existujícího elementu tlačítko panelu nástrojů skupiny tak, aby se zobrazí panelu nástrojů.  
  
    ```xml  
    <Button guid="guidTWTestCommandPackageCmdSet" id="TWTestCommandId" priority="0x0100" type="Button">  
        <Parent guid="guidTWTestCommandPackageCmdSet" id="TWToolbarGroup" />  
        <Icon guid="guidImages" id="bmpPic1" />  
        <Strings>  
            <ButtonText>Invoke TWTestCommand</ButtonText>  
        </Strings>  
    </Button>  
    ```  
  
     Ve výchozím nastavení Pokud má žádné příkazy, panelu nástrojů se nezobrazí.  
  
     Vzhledem k tomu, že nový panel nástrojů není automaticky přidat do okno nástroje, musí explicitně přidat panelu nástrojů. Tento postup je popsán v následujícím oddíle.  
  
## <a name="adding-the-toolbar-to-the-tool-window"></a>Přidání panelu nástrojů na panel nástrojů  
  
1.  V TWTestCommandPackageGuids.cs přidejte následující řádky.  
  
    ```csharp  
    public const string guidTWTestCommandPackageCmdSet = "00000000-0000-0000-0000-0000";  // get the GUID from the .vsct file  
    public const int TWToolbar = 0x1000;  
    ```  
  
2.  V TestToolWindow.cs přidejte následující příkaz using.  
  
    ```csharp  
    using System.ComponentModel.Design;  
    ```  
  
3.  V konstruktoru TestToolWindow přidejte následující řádek.  
  
    ```csharp  
    this.ToolBar = new CommandID(new Guid(TWTestCommandPackageGuids.guidTWTestCommandPackageCmdSet), TWTestCommandPackageGuids.TWToolbar);  
    ```  
  
## <a name="testing-the-toolbar-in-the-tool-window"></a>Testování panelu nástrojů v okně nástroje  
  
1.  Sestavte projekt a spusťte ladění. Visual Studio, které by se měla objevit experimentální instanci.  
  
2.  Na **zobrazení nebo ostatní okna** nabídky, klikněte na tlačítko **okno Test nástrojů** zobrazíte panel nástrojů.  
  
     Měli byste vidět, že panelu nástrojů (vypadá jako výchozí ikonu) v horní pravé okno nástroje právě pod ním.  
  
3.  Na panelu nástrojů klikněte na ikonu k zobrazení zprávy **TWTestCommandPackage uvnitř TWToolbar.TWTestCommand.MenuItemCallback()**.  
  
## <a name="see-also"></a>Viz také  
 [Přidání panelu nástrojů](../extensibility/adding-a-toolbar.md)