---
title: Přidání nabídky do řádku nabídek sady Visual Studio | Dokumentace Microsoftu
ms.date: 3/16/2019
ms.topic: conceptual
helpviewer_keywords:
- menus, creating top level
- top-level menus
ms.assetid: 58fc1a31-2aeb-441c-8e48-c7d5cbcfe501
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a28e7f69ed8e9a76e11d8892ee677435f75c99b2
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66349793"
---
# <a name="add-a-menu-to-the-visual-studio-menu-bar"></a>Přidání nabídky na řádku nabídek sady Visual Studio

Tento návod ukazuje, jak přidat do nabídky na řádku nabídek sady Visual Studio integrované vývojové prostředí (IDE). Panel nabídek integrovaného vývojového prostředí obsahuje kategorií nabídek, jako **souboru**, **upravit**, **zobrazení**, **okno**, a **pomáhají** .

Před přidáním nové nabídky na řádku nabídek sady Visual Studio, zvažte, jestli vaše příkazy by měl být umístěn v rámci existující nabídky. Další informace o umístění příkazu najdete v tématu [nabídek a příkazů pro sadu Visual Studio](../extensibility/ux-guidelines/menus-and-commands-for-visual-studio.md).

Nabídky jsou deklarovány v *.vsct* souboru projektu. Další informace o nabídkách a *.vsct* soubory, naleznete v tématu [příkazy, nabídky a panely nástrojů](../extensibility/internals/commands-menus-and-toolbars.md).

V tomto návodu, můžete vytvořit nabídky s názvem **TestMenu** , která obsahuje jeden příkaz.

> [!NOTE]
> Ve VS 2019 nabídek nejvyšší úrovně přispěla rozšíření jsou umístěné v části **rozšíření** nabídky.

## <a name="prerequisites"></a>Požadavky

Spouští se v sadě Visual Studio 2015, nenainstalujete sadu Visual Studio SDK ze služby Stažení softwaru. Je zahrnut jako volitelná funkce v instalačním programu sady Visual Studio. VS SDK můžete také nainstalovat později. Další informace najdete v tématu [instalace sady Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).

## <a name="create-a-vsix-project-that-has-a-custom-command-item-template"></a>Vytvořte projekt VSIX, který obsahuje šablonu položky vlastní příkaz.

1. Vytvořte projekt VSIX s názvem `TopLevelMenu`. Šablona projektu VSIX v můžete najít **nový projekt** dialogové okno tak, že "vsix".  Další informace najdete v tématu [vytváření rozšíření pomocí příkazu nabídky](../extensibility/creating-an-extension-with-a-menu-command.md).

2. Po otevření projektu přidat vlastní příkaz šablonu položky s názvem **TestCommand**. V **Průzkumníka řešení**, klikněte pravým tlačítkem na uzel projektu a vyberte **přidat** >  **nová položka**. V **přidat novou položku** dialogové okno, přejděte na **Visual C# / rozšíření** a vyberte **vlastního příkazu**. V **název** pole v dolní části okna, změňte název souboru příkazu *TestCommand.cs*.

## <a name="create-a-menu-on-the-ide-menu-bar"></a>Vytvořit nabídku v panelu nabídek integrovaného vývojového prostředí

::: moniker range="vs-2017"

1. V **Průzkumníka řešení**, otevřete *TestCommandPackage.vsct*.

    Na konci souboru, je \<symboly > uzel, který obsahuje několik \<guidsymbol – > uzlů. V uzlech s názvem guidTestCommandPackageCmdSet přidejte nový symbol následujícím způsobem:

   ```xml
   <IDSymbol name="TopLevelMenu" value="0x1021"/>
   ```

2. Vytvořte prázdnou \<nabídky > uzlu \<příkazy > uzlu, těsně před \<skupiny >. V \<nabídky > uzel, přidejte \<nabídky > uzlu, následujícím způsobem:

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

    `guid` a `id` hodnoty nabídky určují sadu příkazů a konkrétní nabídky v sadu příkazů.

    `guid` a `id` nadřazených hodnot umístění v nabídce v části řádku nabídek sady Visual Studio, který obsahuje nástroje a Add-ins nabídky.

    Hodnota `CommandName` řetězec Určuje, že by se zobrazit text v položce nabídky.

3. V \<skupiny > vyhledejte \<skupiny > a změnit \<nadřazené > element tak, aby odkazoval do nabídky jsme právě přidali:

   ```csharp
   <Groups>
         <Group guid="guidTestCommandPackageCmdSet" id="MyMenuGroup" priority="0x0600">
           <Parent guid="guidTestCommandPackageCmdSet" id="TopLevelMenu"/>
         </Group>
       </Groups>
   ```

    Díky tomu je součástí skupiny v nové nabídce.

::: moniker-end

::: moniker range=">=vs-2019"

1. V **Průzkumníka řešení**, otevřete *TopLevelMenuPackage.vsct*.

    Na konci souboru, je \<symboly > uzel, který obsahuje několik \<guidsymbol – > uzlů. V uzlech s názvem guidTopLevelMenuPackageCmdSet přidejte nový symbol následujícím způsobem:

   ```xml
   <IDSymbol name="TopLevelMenu" value="0x1021"/>
   ```

2. Vytvořte prázdnou \<nabídky > uzlu \<příkazy > uzlu, těsně před \<skupiny >. V \<nabídky > uzel, přidejte \<nabídky > uzlu, následujícím způsobem:

   ```xml
   <Menus>
         <Menu guid="guidTopLevelMenuPackageCmdSet" id="TopLevelMenu" priority="0x700" type="Menu">
           <Parent guid="guidSHLMainMenu"
                   id="IDG_VS_MM_TOOLSADDINS" />
           <Strings>
             <ButtonText>TestMenu</ButtonText>
             <CommandName>TestMenu</CommandName>
           </Strings>
       </Menu>
   </Menus>
   ```

    `guid` a `id` hodnoty nabídky určují sadu příkazů a konkrétní nabídky v sadu příkazů.

    `guid` a `id` nadřazených hodnot umístění v nabídce v části řádku nabídek sady Visual Studio, který obsahuje nástroje a Add-ins nabídky.

    Hodnota `CommandName` řetězec Určuje, že by se zobrazit text v položce nabídky.

3. V \<skupiny > vyhledejte \<skupiny > a změnit \<nadřazené > element tak, aby odkazoval do nabídky jsme právě přidali:

   ```csharp
   <Groups>
         <Group guid="guidTopLevelMenuPackageCmdSet" id="MyMenuGroup" priority="0x0600">
           <Parent guid="guidTopLevelMenuPackageCmdSet" id="TopLevelMenu"/>
         </Group>
       </Groups>
   ```

    Díky tomu je součástí skupiny v nové nabídce.

::: moniker-end

4. Najít `Buttons` oddílu. Všimněte si, že [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] generoval balíček šablony `Button` element, který má nadřazený nastavena na `MyMenuGroup`. Tento příkaz v důsledku toho se zobrazí v nabídce.

## <a name="build-and-test-the-extension"></a>Vytváření a testování rozšíření

1. Sestavte projekt a spusťte ladění. Instancí experimentální instanci aplikace by se zobrazit.

::: moniker range="vs-2017"

2. By měl obsahovat nabídek v experimentální instanci **TestMenu** nabídky.

::: moniker-end

::: moniker range=">=vs-2019"

2. **Rozšíření** by měl obsahovat nabídky v experimentální instanci **TestMenu** nabídky.

::: moniker-end

3. Na **TestMenu** nabídky, klikněte na tlačítko **vyvolat příkaz Test**.

     Okno se zprávou by měla objevit a zobrazit zprávu "TestCommand balíček uvnitř TopLevelMenu.TestCommand.MenuItemCallback()".

## <a name="see-also"></a>Viz také:

- [Příkazy, nabídky a panely nástrojů](../extensibility/internals/commands-menus-and-toolbars.md)