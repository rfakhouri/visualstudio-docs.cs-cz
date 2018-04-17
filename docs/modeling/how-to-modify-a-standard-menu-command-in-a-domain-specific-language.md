---
title: 'Postupy: úprava příkazu standardní nabídky v jazyce specifické pro doménu | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- .vsct files, adding commands to a domain-specific language
- Domain-Specific Language, adding custom commands
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 19d555f770802044b88e6a446932596176baa9fb
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-modify-a-standard-menu-command-in-a-domain-specific-language"></a>Postupy: Úprava příkazu standardní nabídky v jazyce specifickém pro doménu
Můžete změnit chování některé standardní příkazy, které jsou definovány automaticky ve vašem DSL. Například může změnit **Vyjmout** tak, aby se vyloučí citlivé informace. K tomuto účelu přepsání metody v příkazu set – třída. Tyto třídy jsou definovány v souboru CommandSet.cs v projektu DslPackage a jsou odvozené z <xref:Microsoft.VisualStudio.Modeling.Shell.CommandSet>.  
  
 V souhrnu upravit příkaz:  
  
1.  [Zjistit, jaké příkazy, můžete upravit](#what).  
  
2.  [Vytvořit deklaraci částečné třídy sady příslušný příkaz](#extend).  
  
3.  [Přepsání metody ProcessOnStatus a ProcessOnMenu](#override) pro příkaz.  
  
 Toto téma vysvětluje tento postup.  
  
> [!NOTE]
>  Pokud chcete vytvořit vlastní příkazy nabídky, přečtěte si téma [postupy: přidání příkazu do místní nabídky](../modeling/how-to-add-a-command-to-the-shortcut-menu.md).  
  
##  <a name="what"></a> Jaké příkazy můžete upravit?  
  
#### <a name="to-discover-what-commands-you-can-modify"></a>Pokud chcete zjistit, co jste příkazy můžete upravit  
  
1.  V `DslPackage` projekt, otevřete `GeneratedCode\CommandSet.cs`. Tento soubor C# můžete najít v Průzkumníku řešení jako dceřiným `CommandSet.tt`.  
  
2.  Najít třídy v tomto souboru, jejichž názvy končí "`CommandSet`", například `Language1CommandSet` a `Language1ClipboardCommandSet`.  
  
3.  Každý příkaz set – třída, zadejte "`override`" následované mezerou. IntelliSense zobrazí seznam metod, které můžete přepsat. Každý příkaz má pár metody, jejichž názvy začínají "`ProcessOnStatus`"a"`ProcessOnMenu`".  
  
4.  Všimněte si, kterou příkazu nastavit třídy obsahuje příkaz, který chcete upravit.  
  
5.  Zavřete soubor bez uložení úprav.  
  
    > [!NOTE]
    >  Obvykle byste neměli upravovat soubory, které byly vytvořeny. Veškeré úpravy budou ztraceny při příštím spuštění se generují soubory.  
  
##  <a name="extend"></a> Rozšíření příslušný příkaz set – třída  
 Vytvořte nový soubor, který obsahuje deklaraci částečné třídy příkazu set.  
  
#### <a name="to-extend-the-command-set-class"></a>Rozšíření třídy sady příkazů  
  
1.  V Průzkumníku řešení v projektu DslPackage otevřete složku GeneratedCode a podívejte se do části CommandSet.tt a otevřete jeho generovaný soubor CommandSet.cs. Všimněte si, obor názvů a název první třídy, která je definována existuje. Například může zobrazit:  
  
     `namespace Company.Language1`  
  
     `{ ...  internal partial class Language1CommandSet : ...`  
  
2.  V **DslPackage**, vytvořte složku s názvem **vlastní kód**. V této složce vytvořte soubor novou třídu s názvem `CommandSet.cs`.  
  
3.  V novém souboru zápisu částečné deklarace, který má stejný obor názvů a název jako generovaný třídu. Příklad:  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.ComponentModel.Design;  
    namespace Company.Language1 /* Make sure this is correct */  
    { internal partial class Language1CommandSet { ...  
    ```  
  
     **Poznámka:** Pokud šablona souboru třídy jste použili k vytvoření nového souboru, je nutné opravit obor názvů a název třídy.  
  
##  <a name="override"></a> Přepsání metody příkaz  
 Většina příkazů mít dvě související metody: jako metodu s názvem `ProcessOnStatus`... Určuje, zda příkaz by měla být viditelné a povolené. Ho je volána, když kliknutí pravým tlačítkem na obrázku a by měla provést rychle a beze změn. `ProcessOnMenu`... je volána, když uživatel klikne na příkaz a proveďte funkce příkazu. Můžete chtít přepsat jedno nebo obě tyto metody.  
  
### <a name="to-change-when-the-command-appears-on-a-menu"></a>Chcete-li změnit, pokud příkaz je zobrazen v nabídce  
 Přepsání ProcessOnStatus... metoda. Tato metoda by měla nastavit viditelný a povolené vlastnosti jeho parametru nabídka – příkaz. Příkaz obvykle vypadá v této. CurrentSelection určit, zda se vztahuje na vybrané elementy příkaz a může taky podívejte se na jejich vlastnosti k určení, zda příkaz lze použít v jeho aktuálním stavu.  
  
 Jako vodítko je třeba určit vlastnost Visible ve přizpůsobitelné prvky jsou vybrány. Vlastnost povoleno, která určuje, zda příkaz zobrazí jako černá nebo šedá v nabídce, by měl závisí na aktuální stav výběru.  
  
 Následující příklad zakáže odstranit položky nabídky, když uživatel vybral více než jeden tvar.  
  
> [!NOTE]
>  Tato metoda nemá vliv, zda je k dispozici prostřednictvím stisknutí klávesy příkaz. Například zakázat položky nabídky odstranit nezabrání příkaz volaná klíč odstranit.  
  
```  
/// <summary>  
/// Called when user right-clicks on the diagram or clicks the Edit menu.  
/// </summary>  
/// <param name="command">Set Visible and Enabled properties.</param>  
protected override void ProcessOnStatusDeleteCommand (MenuCommand command)  
{  
  // Default settings from the base method.  
  base.ProcessOnStatusDeleteCommand(command);  
  if (this.CurrentSelection.Count > 1)  
  {  
    // If user has selected more than one item, Delete is greyed out.  
    command.Enabled = false;  
  }  
}  
```  
  
 Je dobrým zvykem nejprve volat základní metodu, jak nakládat s případy a nastavení, pomocí kterých nejste obavy.  
  
 Metoda ProcessOnStatus nesmí vytvořit, odstranit nebo aktualizovat elementů v úložišti.  
  
### <a name="to-change-the-behavior-of-the-command"></a>Chcete-li změnit chování příkazu  
 Přepsání ProcessOnMenu... metoda. Následující příklad, nemůže uživatel odstranění více než jeden element současně, i pomocí klíče odstranit.  
  
```  
/// <summary>  
/// Called when user presses Delete key   
/// or clicks the Delete command on a menu.  
/// </summary>  
protected override void ProcessOnMenuDeleteCommand()  
{  
  // Allow users to delete only one thing at a time.  
  if (this.CurrentSelection.Count <= 1)  
  {  
    base.ProcessOnMenuDeleteCommand();  
  }  
}  
```  
  
 Pokud váš kód provede změny do úložiště, jako je například vytvoření, odstranění nebo aktualizaci elementy nebo odkazy, musíte tak učinit v transakci. Další informace najdete v tématu [postup vytvoření a aktualizace elementů modelu](../modeling/how-to-modify-a-standard-menu-command-in-a-domain-specific-language.md).  
  
### <a name="writing-the-code-of-the-methods"></a>Psaní kódu z metod  
 Následující fragmenty jsou často užitečné v rámci těchto metod:  
  
-   `this.CurrentSelection`. Obrazec, který uživatel klepli pravým tlačítkem myši je vždy součástí tohoto seznamu tvarů a konektory. Pokud uživatel klikne na prázdnou část diagramu, diagramu je pouze členem seznamu.  
  
-   `this.IsDiagramSelected()` - `true` Pokud uživatel klikne na prázdnou část diagramu.  
  
-   `this.IsCurrentDiagramEmpty()`  
  
-   `this.IsSingleSelection()` -uživatel nevybrali více obrazců  
  
-   `this.SingleSelection` -tvar nebo diagram, který klepli pravým tlačítkem myši uživatele  
  
-   `shape.ModelElement as MyLanguageElement` -element modelu reprezentována obrazce.  
  
 Další informace o tom, jak přejít z elementu a o tom, jak vytvořit objekty a propojení najdete v tématu [navigace a aktualizace modelu v programovém kódu](../modeling/navigating-and-updating-a-model-in-program-code.md).  
  
## <a name="see-also"></a>Viz také  
 <xref:System.ComponentModel.Design.MenuCommand>   
 [Psaní kódu sestavit si jazyka domény](../modeling/writing-code-to-customise-a-domain-specific-language.md)   
 [Postupy: přidání příkazu do místní nabídky](../modeling/how-to-add-a-command-to-the-shortcut-menu.md)   
 [Jak přidat VSPackages prvky uživatelského rozhraní](../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [Visual Studio příkaz tabulky (. Soubory Vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)   
 [Referenční dokumentace schématu VSCT XML](../extensibility/vsct-xml-schema-reference.md)   
 [VMSDK – ukázka okruhů. Přizpůsobení rozsáhlé DSL](http://code.msdn.microsoft.com/Visualization-Modeling-SDK-763778e8)   
 [Ukázkový kód: okruh diagramy](http://code.msdn.microsoft.com/Visualization-Modeling-SDK-763778e8)
