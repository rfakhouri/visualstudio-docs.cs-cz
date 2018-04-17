---
title: Vytvoření vazby klávesové zkratky položky nabídky | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- keyboard command
- keyboards
- command key
- keyboard shortcuts
- menu items
ms.assetid: 19f483b6-4d3e-424e-9d68-dc129c788e47
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: db02cf763ee4bf171d862129c88687accab00cc4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="binding-keyboard-shortcuts-to-menu-items"></a>Vazba klávesové zkratky pro položky nabídky
K vytvoření vazby příkazu nabídky vlastní klávesové zkratky, stačí přidáte položku do .vsct souboru pro balíček. Toto téma vysvětluje, jak k mapování klávesové zkratky vlastní tlačítko, položku nabídky nebo příkazu panelu nástrojů a jak použít mapování klávesnice v editoru výchozí nebo omezit na vlastní editor.  
  
 Klávesové zkratky přiřadit stávající položek nabídky v sadě Visual Studio, najdete v části [identifikuje a přizpůsobení klávesových zkratek](../ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio.md).  
  
## <a name="choosing-a-key-combination"></a>Výběr kombinaci kláves  
 Mnoho klávesové zkratky se již používá v sadě Visual Studio. Stejné zástupce by neměl přiřadit k více než jednoho příkazu, protože je obtížné zjistit duplicitní vazby a může také způsobit nepředvídatelné výsledky. Proto je vhodné ověřit dostupnost zástupce, před přiřazením ho.  
  
#### <a name="to-verify-the-availability-of-a-keyboard-shortcut"></a>Chcete-li ověřit dostupnost klávesové zkratky  
  
1.  V **Nástroje / možnosti / prostředí** vyberte **klávesnice**.  
  
2.  Ujistěte se, že **použití nového zástupce v** je nastaven na **globální**.  
  
3.  V **klávesovou zkratku** zadejte klávesové zkratky, které chcete použít.  
  
     Pokud zástupce se už používá v sadě Visual Studio **Shorcut aktuálně používané** poli se zobrazí příkaz, který aktuálně volá zástupce.  
  
4.  Zkoušejte různé kombinace kláves, dokud zjistíte, ten, který není namapovaná.  
  
    > [!NOTE]
    >  Klávesové zkratky, které používají ALT mohou otevřete nabídku a ne přímo provedení příkazu. Proto **Shorcut aktuálně používané** může být pole prázdné, když zadáte zástupce, který zahrnuje ALT. Můžete ověřit, že zástupce není otevřete nabídku podle zavření **možnosti** dialogové okno a potom stisknutím kláves.  
  
 Následující postup předpokládá, že máte existující VSPackage pomocí příkazu v nabídce. Pokud potřebujete pomoc učinit, podívejte se na [vytvoření rozšíření pomocí příkazu v nabídce](../extensibility/creating-an-extension-with-a-menu-command.md).  
  
#### <a name="to-assign-a-keyboard-shortcut-to-a-command"></a>Příkaz přiřadit klávesové zkratky  
  
1.  Otevřete soubor .vsct pro svůj balíček.  
  
2.  Vytvořte prázdnou `<KeyBindings>` části po `<Commands>` Pokud již není přítomen.  
  
    > [!WARNING]
    >  Další informace o vazeb klíče najdete v tématu [Keybinding](../extensibility/keybinding-element.md).  
  
     V `<KeyBindings>` , vytvořte `<KeyBinding>` položku.  
  
     Nastavte `guid` a `id` atributy těm, které chcete vyvolání příkazu.  
  
     Nastavte `mod1` atribut **řízení**, **Alt**, nebo **Shift**.  
  
     V části klíčových vazeb by měl vypadat přibližně takto:  
  
    ```xml  
    <KeyBindings>  
        <KeyBinding guid="<name of command set>" id="<name of command id>"  
            editor="guidVSStd97" key1="1" mod1="CONTROL"/>  
    </KeyBindings>  
  
    ```  
  
 Pokud klávesové zkratky vyžaduje více než dva klíče, nastavte `mod2` a `key2` atributy.  
  
 Ve většině případů **Shift** by se neměla používat bez druhý modifikátor, protože je již stisknutí způsobí, že většina alfanumerické klíče na typ symbolu nebo velké písmeno.  
  
 Klíč virtuální kódy umožňují přístup k speciální klávesy, které nemají znak spojené s nimi, například funkční klávesy a **BACKSPACE** klíč. Další informace najdete v tématu [virtuální klíč kódy](http://go.microsoft.com/fwlink/?LinkID=105932).  
  
 Chcete-li příkaz k dispozici v sadě Visual Studio editor, nastavte `editor` atribut `guidVSStd97`.  
  
 Chcete-li příkaz k dispozici pouze v vlastní editor, nastavte `editor` atribut název vlastního editoru, který byl vygenerován [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] balíček šablonu při vytváření VSPackage obsahuje vlastní editor. Hodnota názvu, hledejte v `<Symbols>` část `<GuidSymbol>` uzlu jejichž `name` atribut končí na "`editorfactory`." Toto je název vlastního editoru.  
  
## <a name="example"></a>Příklad  
 Tento příklad vytvoří vazbu klávesovou zkratku CTRL + ALT + C příkaz s názvem `cmdidMyCommand` v balíčku s názvem `MyPackage`.  
  
```  
<CommandTable>  
. . .  
<Commands>  
. . .  
</Commands>  
<KeyBindings>  
  <KeyBinding guid="guidMyPackageCmdSet" id="cmdidMyCommand"   
      key1="C" mod1="CONTROL" mod2="ALT" editor="guidVSStd97" />  
</KeyBindings>  
. . .  
</CommandTable>  
```  
  
## <a name="example"></a>Příklad  
 Tento příklad vytvoří vazbu klávesovou zkratku CTL + B příkaz s názvem `cmdidBold` v projektu s názvem `TestEditor`. Příkaz je k dispozici pouze v editoru vlastní a není v jiných editory.  
  
```xml  
<KeyBinding guid="guidVSStd97" id="cmdidBold" editor="guidTestEditorEditorFactory" key1="B" mod1="Control" />  
```  
  
## <a name="see-also"></a>Viz také  
 [Rozšiřování nabídek a příkazů](../extensibility/extending-menus-and-commands.md)