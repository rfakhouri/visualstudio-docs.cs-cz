---
title: Přidání nabídky na panelu nabídek Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- menus, creating top level
- top-level menus
ms.assetid: 58fc1a31-2aeb-441c-8e48-c7d5cbcfe501
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 3a391da85c38176d79a1c77ce8836ce510e8d27e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="adding-a-menu-to-the-visual-studio-menu-bar"></a>Přidání nabídky na panelu nabídek Visual Studio
Tento návod ukazuje, jak přidat nabídku na panelu nabídek integrované vývojové prostředí (IDE) sady Visual Studio. Panel nabídek IDE obsahuje nabídky kategorie, jako **soubor**, **upravit**, **zobrazení**, **okno**, a **pomoci** .  
  
 Před přidáním nové nabídky do nabídek v sadě Visual Studio, zvažte, zda má být umístěn příkazech v rámci existující nabídky. Další informace o příkazu umístění najdete v tématu [nabídek a příkazů pro sadu Visual Studio](../extensibility/ux-guidelines/menus-and-commands-for-visual-studio.md).  
  
 Nabídky jsou deklarované v souboru .vsct projektu. Další informace o nabídky a .vsct souborů najdete v tématu [příkazy, nabídek a panelů nástrojů](../extensibility/internals/commands-menus-and-toolbars.md).  
  
 Provedením tohoto návodu, můžete vytvořit nabídky s názvem **TestMenu** obsahující jeden příkaz.  
  
## <a name="prerequisites"></a>Požadavky  
 Od sady Visual Studio 2015 se neinstalovat sadu Visual Studio SDK z webu Stažení softwaru. Je zahrnuta jako volitelná funkce v instalačním programu sady Visual Studio. VS SDK můžete také nainstalovat později. Další informace najdete v tématu [instalace sady Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="creating-a-vsix-project-that-has-a-custom-command-item-template"></a>Vytvoření projektu VSIX, který má příkaz vlastní šablony položek  
  
1.  Vytvoření projektu VSIX s názvem `TopLevelMenu`. Můžete najít v šabloně projektů VSIX **nový projekt** dialogové okno pod **Visual C#** / **rozšiřitelnost**.  Další informace najdete v tématu [vytvoření rozšíření pomocí příkazu v nabídce](../extensibility/creating-an-extension-with-a-menu-command.md).  
  
2.  Když na projekt se otevře, přidejte šablonu a vlastní příkaz položka s názvem **TestCommand**. V **Průzkumníku řešení**, klikněte pravým tlačítkem na uzel projektu a vyberte **přidat / novou položku**. V **přidat novou položku** dialogové okno, přejděte na **Visual C# nebo rozšíření** a vyberte **vlastní příkaz**. V **název** pole v dolní části okna, změňte název souboru příkaz **TestCommand.cs**.  
  
## <a name="creating-a-menu-on-the-ide-menu-bar"></a>Vytvoření nabídky v řádku nabídek IDE  
  
#### <a name="to-create-a-menu"></a>Vytvoření nabídky  
  
1.  V **Průzkumníku**, otevřete TestCommandPackage.vsct.  
  
     Na konci souboru, je \<symboly > uzlu, který obsahuje několik \<GuidSymbol > uzly. V uzlu s názvem guidTestCommandPackageCmdSet přidejte nový symbol následujícím způsobem:  
  
    ```xml  
    <IDSymbol name="TopLevelMenu" value="0x1021"/>  
    ```  
  
2.  Vytvořte prázdnou \<nabídky > uzlu \<příkazy > uzlu, těsně před \<skupiny >. V \<nabídky > uzlu, přidejte \<nabídky > uzlu, následujícím způsobem:  
  
    ```xml  
    <Menus>  
          <Menu guid="guidTestCommandPackageCmdSet" id="TopLevelMenu" priority="0x700" type="Menu">  
            <Parent guid="guidSHLMainMenu"  
                    id="IDG_VS_MM_TOOLSADDINS" />  
            <Strings>  
              <ButtonText>TestMenu</ButtonText>  
              <CommandName>TestMenu</CommandName>  
            </Strings>  
        </Menu>  
    </Menus>  
    ```  
  
     `guid` a `id` hodnoty v nabídce určují sadu příkazů nástroje a konkrétní nabídky v sadu příkazů.  
  
     `guid` a `id` hodnoty nadřazeného prvku pozice v nabídce v části panelu nabídek Visual Studio, který obsahuje nástroje a doplňky nabídky.  
  
     Hodnota `CommandName` řetězec Určuje, že by se zobrazit text v položku nabídky.  
  
3.  V \<skupiny > vyhledejte \<skupiny > a změňte \<nadřazené > element tak, aby odkazovaly do nabídky, kterou jsme právě přidali:  
  
    ```csharp  
    <Groups>  
          <Group guid="guidTestCommandPackageCmdSet" id="MyMenuGroup" priority="0x0600">  
            <Parent guid="guidTestCommandPackageCmdSet" id="TopLevelMenu"/>  
          </Group>  
        </Groups>  
    ```  
  
     Díky tomu skupiny součástí nové nabídky.  
  
4.  Najít `Buttons` části. Všimněte si, že [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] vygenerovala balíčku šablony `Button` element, který má nadřazený nastavena na `MyMenuGroup`. V důsledku toho se tento příkaz zobrazí na vaší nabídky.  
  
## <a name="building-and-testing-the-extension"></a>Vytváření a testování rozšíření  
  
1.  Sestavte projekt a spusťte ladění. Instance experimentální instance by se zobrazit.  
  
2.  Panel nabídek v experimentální instanci by měl obsahovat **TestMenu** nabídky.  
  
3.  Na **TestMenu** nabídky, klikněte na tlačítko **vyvolání příkazu testovací**.  
  
     Okno se zprávou by měl zobrazit a zobrazí se zpráva "TestCommand balíček uvnitř TopLevelMenu.TestCommand.MenuItemCallback()". To znamená, že nový příkaz funguje.  
  
## <a name="see-also"></a>Viz také  
 [Příkazy, nabídky a panely nástrojů](../extensibility/internals/commands-menus-and-toolbars.md)