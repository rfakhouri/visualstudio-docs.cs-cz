---
title: "Vytváření opakovaně použitelných skupin tlačítek | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- button groups, creating in VSPackages
- VSPackages, creating reusable button groups
- buttons, creating reusable groups
ms.assetid: 0c561617-fb86-476d-8bd1-c6e5e7464c65
caps.latest.revision: "44"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 4be8e84c6040f3b4d57082cd39920aec2196e9f7
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="creating-reusable-groups-of-buttons"></a>Vytváření opakovaně použitelných skupin tlačítek
Skupina příkazu je kolekce příkazy, které se vždy zobrazují společně v nabídce nebo na panelu nástrojů. Všechny skupiny pro příkaz znovu lze přiřazením do jiné nadřazené nabídek v části CommandPlacements .vsct souboru.  
  
 Příkaz skupiny obvykle obsahují tlačítka, ale může také obsahovat další nabídky nebo pole se seznamem.  
  
### <a name="to-create-a-reusable-group-of-buttons"></a>Chcete-li vytvořit opakovaně použitelný skupina tlačítek  
  
1.  Vytvoření projektu VSIX s názvem `ReusableButtons`. Další informace najdete v tématu [vytvoření rozšíření pomocí příkazu v nabídce](../extensibility/creating-an-extension-with-a-menu-command.md).  
  
2.  Když na projekt se otevře, přidejte šablonu a vlastní příkaz položka s názvem **ReusableCommand**. V **Průzkumníku řešení**, klikněte pravým tlačítkem na uzel projektu a vyberte **přidat / novou položku**. V **přidat novou položku** dialogové okno, přejděte na **Visual C# nebo rozšíření** a vyberte **vlastní příkaz**. V **název** pole v dolní části okna, změňte název souboru příkaz **ReusableCommand.cs**.  
  
3.  V souboru .vsct přejděte k části symboly a najít GuidSymbol elementu, který obsahuje skupiny a příkazy pro projekt. Musí mít název guidReusableCommandPackageCmdSet.  
  
4.  Přidáte IDSymbol pro každé tlačítko, které přidáte do skupiny, jako v následujícím příkladu.  
  
    ```xml  
    <GuidSymbol name="guidReusableCommandPackageCmdSet" value="{7f383b2a-c6b9-4c1d-b4b8-a26dc5b60ca1}">  
        <IDSymbol name="MyMenuGroup" value="0x1020" />  
        <IDSymbol name="ReusableCommandId" value="0x0100" />  
        <IDSymbol name="SecondReusableCommandId" value="0x0200" />  
    </GuidSymbol>  
    ```  
  
     Ve výchozím nastavení, šablony položky příkaz vytvoří skupinu s názvem **MyGroup** a tlačítko, které má název, který jste zadali, spolu s IDSymbol záznam pro každý.  
  
5.  V části skupiny vytvořte skupinového elementu, který má stejný identifikátor GUID a ID atributy jako ty, které jsou uvedeny v části symboly. Můžete také použít stávající skupinu nebo použít položku, která zajišťuje šabloně příkaz jako v následujícím příkladu. Této skupiny se zobrazí na **nástroje** nabídky  
  
    ```xml  
    <Groups>  
        <Group guid="guidReusableCommandPackageCmdSet" id="MyMenuGroup" priority="0x0600">  
              <Parent guid="guidSHLMainMenu" id="IDM_VS_MENU_TOOLS"/>  
        </Group>  
    </Groups>  
    ```  
  
### <a name="to-create-a-group-of-buttons-for-reuse"></a>Vytvoření skupiny tlačítek pro opakované použití  
  
1.  Příkaz nebo nabídky můžete uvést ve skupině pomocí skupiny jako nadřazený objekt v definici příkazu nebo nabídky nebo vložením příkazu nebo nabídky ve skupině pomocí části CommandPlacements.  
  
     V části tlačítka definovat tlačítko, které má vaše skupinu jako svůj nadřazený uzel, nebo použijte tlačítko poskytovaná šablonou balíček, jak je znázorněno v následujícím příkladu.  
  
    ```xml  
    <Button guid="guidReusableCommandPackageCmdSet" id="ReusableCommandId" priority="0x0100" type="Button">  
        <Parent guid="guidReusableCommandPackageCmdSet" id="MyMenuGroup" />  
        <Icon guid="guidImages" id="bmpPic1" />  
        <Strings>  
            <ButtonText>Invoke ReusableCommand</ButtonText>  
        </Strings>  
    </Button>  
    ```  
  
2.  Pokud tlačítko objevit ve více než jedné skupiny, vytvořte záznam pro něj v části CommandPlacements musí být umístěny po části příkazy. Nastavit atributy GUID a ID elementu CommandPlacement shodují s těmi, které chcete umístit tlačítka a potom nastavte GUID a ID objektů svého nadřízeného elementu na ty, cílové skupiny, jak je znázorněno v následujícím příkladu.  
  
    ```xml  
    <CommandPlacements>  
        <CommandPlacement guid="guidReusableCommandPackageCmdSet" id="SecondReusableCommandId" priority="0x105">  
          <Parent guid="guidReusableCommandPackageCmdSet" id="MyMenuGroup" />  
        </CommandPlacement>  
    </CommandPlacements>  
    ```  
  
    > [!NOTE]
    >  Hodnota pole Priorita určuje pozici příkazu v nové skupině příkaz. V CommandPlacement element přepíšou nastavení v definici položky nastavit priority. Příkazy, které mají nižší hodnoty priority se zobrazují před příkazy, které mají vyšší hodnoty priority. Priorita duplicitní hodnoty jsou povolené, ale relativní pozici příkazy, které mají stejnou prioritu nemůže zaručit, protože pořadí, v jakém **devenv/Setup** příkaz vytvoří konečnou rozhraní z registru mohou být nekonzistentní.  
  
### <a name="to-put-a-reusable-group-of-buttons-on-a-menu"></a>V nabídce uvést opakovaně použitelné skupina tlačítek  
  
1.  Vytvořit položku ve `CommandPlacements` oddílu. Nastavte GUID a ID `CommandPlacement` element na ty, skupiny a nastavte nadřazený identifikátor GUID a ID na těch, které v cílovém umístění.  
  
     V části CommandPlacements musí být umístěny bezprostředně za části příkazy:  
  
    ```xml  
    <CommandTable>  
    ...  
      <Commands>... </Commands>  
      <CommandPlacements>... </CommandPlacements>  
    ...   
    </CommandTable>  
    ```  
  
     Skupina příkazu lze vložit více než jeden nabídky. V nabídce nadřazené může být ten, který jste vytvořili, ten, který poskytl [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] (jako popsaný v tématu ShellCmdDef.vsct nebo SharedCmdDef.vsct), nebo jednu, která je definována v jiné VSPackage. Počet vrstev vztahy k nadřazeným položkám neomezená tak dlouho, dokud nabídce nadřazený server připojený k [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nebo místní nabídky, který se zobrazí při VSPackage.  
  
     Následující příklad vloží skupině **Průzkumníku řešení** napravo od ostatních tlačítek panelu nástrojů.  
  
    ```xml  
    <CommandPlacements>  
        <CommandPlacement guid="guidReusableCommandPackageCmdSet" id="MyMenuGroup" priority="0xF00">  
          <Parent guid="guidSHLMainMenu" id="IDM_VS_TOOL_PROJWIN"/>  
        </CommandPlacement>  
    </CommandPlacements>  
    ```  
  
    ```xml  
    <CommandPlacements>  
      <CommandPlacement guid="guidButtonGroupCmdSet" id="MyMenuGroup"   
          priority="0x605">  
        <Parent guid="guidSHLMainMenu" id="IDM_VS_MENU_TOOLS" />  
      </CommandPlacement>  
    </CommandPlacements>  
  
    ```