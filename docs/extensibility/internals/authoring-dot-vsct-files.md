---
title: Vytváření obsahu. Soubory Vsct | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- VSCT files, manual authoring
ms.assetid: e9f715dc-12b7-439b-bdf3-f3dc75e62f1c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 65fc62d5685ca7c81b3ebb7f524db3cdbebe72c7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31134770"
---
# <a name="authoring-vsct-files"></a>Vytváření obsahu. Vsct soubory
Tento dokument ukazuje, jak vytvořit soubor .vsct k přidání položky nabídky, panely nástrojů a další prvky uživatelského rozhraní (UI) v sadě Visual Studio integrované vývojové prostředí (IDE). Tyto kroky použijte, když přidáte prvky uživatelského rozhraní pro Visual Studio balíček (VSPackage), který ještě nemá soubor .vsct.  
  
 Pro nové projekty doporučujeme použít šablonu balíček Visual Studio, protože vygeneruje soubor .vsct, který v závislosti na požadované možnosti již požadované prvky pro příkaz nabídky, okno nástroje nebo vlastní editor. Můžete upravit soubor .vsct pro splnění požadavků vaší VSPackage. Další informace o tom, jak upravit soubor .vsct, podívejte se na příklady v [rozšíření nabídek a příkazů](../../extensibility/extending-menus-and-commands.md).  
  
## <a name="authoring-the-file"></a>Vytváření souboru  
 Vytvořit soubor .vsct v těchto fází: vytvořte strukturu pro soubory a prostředky, deklarovat prvky uživatelského rozhraní, put prvky uživatelského rozhraní v prostředí IDE a přidejte jakékoli speciální chování.  
  
### <a name="file-structure"></a>Struktura souborů  
 Základní struktura .vsct souboru je [CommandTable](../../extensibility/commandtable-element.md) kořenový element, který obsahuje [příkazy](../../extensibility/commands-element.md) elementu a [symboly](../../extensibility/symbols-element.md) elementu.  
  
##### <a name="to-create-the-file-structure"></a>Chcete-li vytvořit strukturu souborů  
  
1.  Přidejte do projektu soubor .vsct podle kroků v [postupy: vytvoření. Soubor Vsct](../../extensibility/internals/how-to-create-a-dot-vsct-file.md).  
  
2.  Přidejte požadované obory názvů `CommandTable` elementu, jak je znázorněno v následujícím příkladu.  
  
    ```xml  
    <CommandTable xmlns="http://schemas.microsoft.com/VisualStudio/2005-10-18/CommandTable"   
        xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  
    ```  
  
3.  V `CommandTable` elementu, přidejte `Commands` element pro hostování všech vlastní nabídky, panely nástrojů, příkaz skupiny a příkazy. Aby mohl načíst vaše vlastní elementy uživatelského rozhraní, `Commands` element musí mít jeho `Package` atributu nastavena na název balíčku.  
  
     Po `Commands` elementu, přidejte `Symbols` elementu, který chcete definovat identifikátory GUID pro balíček a názvy a identifikátory příkazů pro prvky vaši uživatelského rozhraní.  
  
### <a name="including-visual-studio-resources"></a>Zahrnování prostředků sady Visual Studio  
 Použití [Extern](../../extensibility/extern-element.md) element přístup k souborům, které definují příkazy sady Visual Studio a nabídky, které jsou nutné uvést vaše prvky uživatelského rozhraní v prostředí IDE. Pokud budete používat příkazy definované mimo váš balíček, použijte [UsedCommands](../../extensibility/usedcommands-element.md) element k informování Visual Studio.  
  
##### <a name="to-include-visual-studio-resources"></a>Chcete-li zahrnout zdroje sady Visual Studio  
  
1.  V horní části `CommandTable` elementu přidat `Extern` element pro každý externí soubor odkazuje, a nastavte `href` atribut název souboru. Následující soubory hlaviček pro přístup k prostředkům v sadě Visual Studio, můžete odkazovat:  
  
    -   Stdidcmd.h, definuje ID pro všechny příkazy, které jsou vystavené Visual Studio.  
  
    -   Vsshlids.h, obsahuje ID příkazu pro Visual Studio nabídky.  
  
2.  Pokud váš balíček volá všechny příkazy, které jsou definovány v sadě Visual Studio nebo jiné balíčky, přidejte `UsedCommands` element po `Commands` elementu. Naplnění tento element s [UsedCommand](../../extensibility/usedcommand-element.md) element u každého příkazu, který zavoláte není součástí vašeho balíčku. Nastavte `guid` a `id` atributy `UsedCommand` elementy na identifikátor GUID a ID hodnoty z příkazů pro volání. Další informace o tom, jak najít příkazy, identifikátory GUID a ID Visual Studio najdete v tématu [identifikátory GUID a ID z příkazy sady Visual Studio](../../extensibility/internals/guids-and-ids-of-visual-studio-commands.md). Volat příkazy z dalších balíčků, použijte identifikátor GUID a ID příkazu, jak jsou definovány v souboru .vsct pro tyto balíčky.  
  
### <a name="declaring-ui-elements"></a>Deklarování prvky uživatelského rozhraní  
 Deklarovat všechny nové prvky uživatelského rozhraní v `Symbols` oddílu .vsct souboru.  
  
##### <a name="to-declare-ui-elements"></a>Chcete-li deklarovat prvky uživatelského rozhraní  
  
1.  V `Symbols` elementu, přidejte tři [GuidSymbol](../../extensibility/guidsymbol-element.md) elementy. Každý `GuidSymbol` element má `name` atribut a `value` atribut. Nastavte `name` atribut, aby odrážel účel elementu. `value` Atribut trvá identifikátor GUID. (Generovat identifikátor GUID na **nástroje** nabídky, klikněte na tlačítko **vytvořit GUID**a potom vyberte **registru formátu**.)  
  
     První `GuidSymbol` element představuje váš balíček a obvykle nemá žádné podřízené objekty. Druhý `GuidSymbol` element představuje příkaz Nastavení a bude obsahovat všechny symboly, které definují nabídky, skupin a příkazy. Třetí `GuidSymbol` element představuje vaše úložiště image store a obsahuje symboly pro všechny ikony pro příkazy. Pokud máte žádné příkazy, které používají ikony, můžete vynechat třetí `GuidSymbol` elementu.  
  
2.  V `GuidSymbol` elementu, který představuje vaše sadu příkazů přidat jeden nebo víc [IDSymbol](../../extensibility/idsymbol-element.md) elementy. Každá z těchto představují nabídky, panel nástrojů, skupiny nebo příkazu, který chcete přidat do rozhraní.  
  
     Pro každou `IDSymbol` , nastavena `name` atribut název budete odkazovat na odpovídající nabídky, skupinu nebo příkazu a poté nastavte `value` element hexadecimální číslo, které budou představovat jeho id příkazu. Žádné dva `IDSymbol` prvky, které mají stejnou nadřazenou položkou může mít stejnou hodnotu.  
  
3.  Pokud některé z vašich prvků uživatelského rozhraní vyžadují ikony, přidejte `IDSymbol` element pro každou ikonu `GuidSymbol` elementu, který představuje vaše úložiště bitových kopií.  
  
### <a name="putting-ui-elements-in-the-ide"></a>Uvedení prvky uživatelského rozhraní v prostředí IDE  
 [Nabídky](../../extensibility/menus-element.md) elementu [skupiny](../../extensibility/groups-element.md) elementu a [tlačítka](../../extensibility/buttons-element.md) element obsahovat definice pro všechny nabídky, skupiny a příkazy, které jsou definovány v vašeho balíčku. Uveďte těchto nabídek, skupiny a příkazy v prostředí IDE buď pomocí [nadřazené](../../extensibility/parent-element.md) element, který je součástí definice element uživatelského rozhraní nebo pomocí [CommandPlacement](../../extensibility/commandplacement-element.md) element, který je definován jinde.  
  
 Každý `Menu`, `Group`, a `Button` element má `guid` atribut a `id` atribut. Vždy nastaven `guid` odpovídat názvu atributu `GuidSymbol` elementu, který představuje příkazu nastavit a `id` atribut název `IDSymbol` elementu, který představuje vaší nabídky, skupinu nebo příkaz `Symbols`části.  
  
##### <a name="to-define-ui-elements"></a>Chcete-li definovat prvky uživatelského rozhraní  
  
1.  Pokud definujete žádné nové nabídky, dílčích, místní nabídky nebo panely nástrojů, přidejte `Menus` elementu, který chcete `Commands` elementu. Potom pro jednotlivé nabídky, který se má vytvořit, přidat [nabídky](../../extensibility/menu-element.md) elementu, který chcete `Menus` elementu.  
  
     Nastavte `guid` a `id` atributy `Menu` element a pak nastavte `type` atributů pro druh nabídky, které chcete. Můžete také nastavit `priority` atribut k navázání relativní pozici v nabídce v nadřazené skupině.  
  
    > [!NOTE]
    >  `priority` Atribut se nevztahuje na panely nástrojů a kontextové nabídky.  
  
2.  Všechny příkazy v prostředí Visual Studio IDE musí být hostované příkaz skupin, které jsou přímo podřízené nabídek a panelů nástrojů. Pokud přidáváte nové nabídek a panelů nástrojů k prostředí IDE, tyto musí obsahovat nové skupiny příkaz. Příkaz skupiny může také přidat do existující nabídek a panelů nástrojů tak, aby vizuálně můžete seskupit příkazech.  
  
     Když přidáte nové skupiny příkaz, musíte nejdřív vytvořit `Groups` elementu a pak přidejte do ní [skupiny](../../extensibility/group-element.md) element pro každou skupinu příkaz.  
  
     Nastavte `guid` a `id` atributy jednotlivých `Group` element a pak nastavte `priority` atribut k navázání relativní pozici v nabídce nadřazené skupiny. Další informace najdete v tématu [vytváření skupin opakovaně použitelného z tlačítka](../../extensibility/creating-reusable-groups-of-buttons.md).  
  
3.  Pokud přidáváte nové příkazy k prostředí IDE, přidejte `Buttons` elementu, který chcete `Commands` elementu. Potom u každého příkazu Přidat [tlačítko](../../extensibility/button-element.md) elementu, který chcete `Buttons` elementu.  
  
    1.  Nastavte `guid` a `id` atributy jednotlivých `Button` element a pak nastavte `type` atributů pro druh tlačítko chcete. Můžete také nastavit `priority` atribut k navázání relativní pozici příkazu v nadřazené skupině.  
  
        > [!NOTE]
        >  Použití `type="button"` pro standardní příkazy a tlačítka na panely nástrojů.  
  
    2.  V `Button` elementu, přidejte [řetězce](../../extensibility/strings-element.md) elementu, který obsahuje [ButtonText](../../extensibility/buttontext-element.md) element a [CommandName](../../extensibility/commandname-element.md) elementu. `ButtonText` Element poskytuje textový popisek pro položku nabídky nebo popisek pro tlačítka panelu nástrojů. `CommandName` Element poskytuje název příkazu taky používat v příkazu.  
  
    3.  Pokud váš příkaz ikonu, vytvořte [ikonu](../../extensibility/icon-element.md) element v `Button` elementu a nastavte jeho `guid` a `id` atributy pro `Bitmap` element ikony.  
  
        > [!NOTE]
        >  Tlačítka panelu nástrojů musí mít ikony.  
  
     Další informace najdete v tématu [MenuCommands Vs. OleMenuCommands](../../extensibility/menucommands-vs-olemenucommands.md).  
  
4.  Pokud některé z příkazech vyžadují ikony, přidejte [bitmap](../../extensibility/bitmaps-element.md) elementu, který chcete `Commands` elementu. Potom pro každou ikonu Přidat [rastrový obrázek](../../extensibility/bitmap-element.md) elementu, který chcete `Bitmaps` elementu. Toto je, kde zadáte umístění prostředku rastrového obrázku. Další informace najdete v tématu [přidání ikony příkazů nabídky](../../extensibility/adding-icons-to-menu-commands.md).  
  
 Můžete spolehnout na vztahy k nadřazeným položkám struktura správně umístit většinu nabídek, skupiny a příkazy. Pro velké příkaz sad nebo když nabídky, skupinu nebo příkaz objevit na více místech, doporučujeme, že zadáte příkaz umístění.  
  
##### <a name="to-rely-on-parenting-to-place-ui-elements-in-the-ide"></a>Moct spolehnout na vztahy k nadřazeným položkám umístit prvky uživatelského rozhraní v prostředí IDE  
  
1.  Pro typické vztahy k nadřazeným položkám, vytvořte `Parent` element v každé `Menu`, `Group`, a `Command` element, který je definován v vašeho balíčku.  
  
     Cílem `Parent` element je nabídky nebo skupiny, která bude obsahovat v nabídce, skupinu nebo příkaz.  
  
    1.  Nastavte `guid` atribut název `GuidSymbol` element, který definuje sadu příkazů. Pokud cílový element není součástí vašeho balíčku, použijte identifikátor guid pro tuto sadu příkazů, jak jsou definovány v odpovídající soubor .vsct.  
  
    2.  Nastavte `id` atribut tak, aby odpovídala `id` atribut target nabídky nebo skupiny. Pro seznam nabídky a skupiny, které jsou zveřejněné Visual Studio, najdete v části [identifikátory GUID a ID nástroje Visual Studio nabídek](../../extensibility/internals/guids-and-ids-of-visual-studio-menus.md) nebo [identifikátory GUID a ID nástroje Visual Studio panelů nástrojů](../../extensibility/internals/guids-and-ids-of-visual-studio-toolbars.md).  
  
 Pokud máte velký počet prvků uživatelského rozhraní pro umístění v prostředí IDE, nebo pokud máte prvků, které se mají zobrazit na více místech, definovat jejich umísťováním v [CommandPlacements](../../extensibility/commandplacements-element.md) elementu, jak je znázorněno v následujícím postupu.  
  
##### <a name="to-use-command-placement-to-place-ui-elements-in-the-ide"></a>Použít příkaz umístění umístit prvky uživatelského rozhraní v prostředí IDE  
  
1.  Po `Commands` elementu, přidejte `CommandPlacements` elementu.  
  
2.  V `CommandPlacements` elementu, přidejte `CommandPlacement` element pro každou nabídky, skupiny nebo příkaz umístit.  
  
     Každý `CommandPlacement` element nebo `Parent` element umístí jeden nabídky, skupinu nebo příkaz na jednom místě IDE. Element uživatelského rozhraní může mít pouze jednu nadřazenou položku, ale může mít několik umísťováním příkaz. Umístit prvku uživatelského rozhraní na více místech, přidejte `CommandPlacement` element pro každé umístění.  
  
3.  Nastavte `guid` a `id` atributy jednotlivých `CommandPlacement` element pro hostování nabídky nebo skupiny, stejně, jako by pro `Parent` elementu. Můžete také nastavit `priority` atribut k navázání relativní umístění prvku uživatelského rozhraní.  
  
 Je možné kombinovat umístění pomocí vztahy k nadřazeným položkám a příkaz umístění. Pro velké příkaz sady, ale doporučujeme používat pouze příkaz umístění.  
  
### <a name="adding-specialized-behaviors"></a>Přidání specializované chování  
 Můžete použít [CommandFlag](../../extensibility/command-flag-element.md) elementy chcete změnit chování nabídek a příkazů, například, chcete-li změnit jejich vzhled a viditelnost. Může ovlivnit také když příkaz je viditelná pomocí [VisibilityConstraints](../../extensibility/visibilityconstraints-element.md), nebo přidejte klávesové zkratky pomocí [klíčových vazeb](../../extensibility/keybindings-element.md). Určité typy nabídek a příkazů již specializovaný chování součástí.  
  
##### <a name="to-add-specialized-behaviors"></a>Chcete-li přidat specializované chování  
  
1.  Chcete-li prvku uživatelského rozhraní viditelná pouze v určitých uživatelského rozhraní kontextů, například při načtení řešení, použijte omezení viditelnosti.  
  
    1.  Po `Commands` elementu, přidejte `VisibilityConstraints` elementu.  
  
    2.  Pro každou položku uživatelského rozhraní k omezení přidat [VisibilityItem](../../extensibility/visibilityitem-element.md) element.  
  
    3.  Pro každou `VisibilityItem` , nastavena `guid` a `id` atributy nabídky, skupiny, nebo příkaz a potom nastavte `context` atribut kontext uživatelského rozhraní, který chcete, jak jsou definovány v <xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids80> – třída. Další informace najdete v tématu [VisibilityItem Element](../../extensibility/visibilityitem-element.md).  
  
2.  Pokud chcete nastavit viditelnost nebo dostupnosti položky uživatelského rozhraní v kódu, použijte jeden nebo více následující příznaky příkazu:  
  
    -   DefaultDisabled  
  
    -   DefaultInvisible  
  
    -   DynamicItemStart  
  
    -   DynamicVisibility  
  
    -   NoShowOnMenuController  
  
    -   NotInTBList  
  
     Další informace najdete v tématu [Element Command příznak](../../extensibility/command-flag-element.md).  
  
3.  Ke změně jak element se zobrazí, nebo se dynamicky mění její vzhled, použijte jednu nebo více následující příznaky příkazu:  
  
    -   AlwaysCreate  
  
    -   CommandWellOnly  
  
    -   DefaultDocked  
  
    -   DontCache  
  
    -   DynamicItemStart  
  
    -   FixMenuController  
  
    -   IconAndText  
  
    -   PICT  
  
    -   StretchHorizontally  
  
    -   TextMenuUseButton  
  
    -   TextChanges  
  
    -   Typu TextOnly  
  
     Další informace najdete v tématu [Element Command příznak](../../extensibility/command-flag-element.md).  
  
4.  Ke změně, jak element odpovědí, pokud obdrží příkazy, použijte jednu nebo více následující příznaky příkazu:  
  
    -   AllowParams  
  
    -   CaseSensitive  
  
    -   CommandWellOnly  
  
    -   Funkce Filtrování kláves  
  
    -   NoAutoComplete  
  
    -   NoButtonCustomize  
  
    -   NoKeyCustomize  
  
    -   NoToolbarClose  
  
    -   PostExec  
  
    -   RouteToDocs  
  
    -   TextIsAnchorCommand  
  
     Další informace najdete v tématu [Element Command příznak](../../extensibility/command-flag-element.md).  
  
5.  Závislé nabídky klávesové zkratky připojit k nabídce nebo položku v nabídce, přidejte znak ampersand ('a ') v `ButtonText` nabídka nebo položka nabídky elementu. Znak, který následuje ampersand je active klávesovou zkratku, když je otevřený v nabídce nadřazené.  
  
6.  Chcete-li připojení k příkazu nabídky nezávislé klávesové zkratky, použijte [klíčových vazeb](../../extensibility/keybindings-element.md). Další informace najdete v tématu [KeyBinding Element](../../extensibility/keybinding-element.md).  
  
7.  O lokalizaci text nabídky, použijte `LocCanonicalName` elementu. Další informace najdete v tématu [řetězce Element](../../extensibility/strings-element.md).  
  
 Některé typy nabídky a tlačítko zahrnovat specializovaná chování. Následující tabulka popisuje některé speciální nabídky a typy tlačítko. Pro ostatní typy podívejte `types` atribut popisy v [Menu Element](../../extensibility/menu-element.md), [Button Element](../../extensibility/button-element.md), a [Element pole se seznamem](../../extensibility/combo-element.md).  
  
 Pole se seznamem  
 Pole se seznamem je rozevíracího seznamu, který lze použít na panelu nástrojů. Chcete-li přidat pole se seznamem do uživatelského rozhraní, vytvořte [kláves](../../extensibility/combos-element.md) element v `Commands` elementu. Pak přidejte do `Combos` elementu `Combo` element pro každé pole se seznamem přidat. `Combo` elementy mají stejné atributy a podřízené položky jako `Button` elementy a také mít `DefaultWidth` a `idCommandList` atributy. `DefaultWidth` Atribut Nastaví šířku v pixelech a `idCommandList` atribut body ID příkazu, který se používá k vyplnění pole se seznamem. Další informace najdete v tématu `Combo` element dokumentaci.  
  
 MenuController  
 Řadič nabídky je tlačítko, které má šipka vedle sebe. Klikněte na šipku otevřete seznam. Chcete-li přidat řadič nabídky do uživatelského rozhraní, vytvořte `Menu` elementu a sadu jeho `type` atribut **MenuController** nebo **MenuControllerLatched**, v závislosti na chování, které chcete. K naplnění řadič nabídky, nastavte ji jako nadřazený prvek `Group` elementu. Řadičem nabídky se zobrazí všechny podřízené objekty dané skupiny v rozevíracím seznamu.  
  
## <a name="see-also"></a>Viz také  
 [Rozšíření nabídek a příkazů](../../extensibility/extending-menus-and-commands.md)   
 [Visual Studio příkaz tabulky (. Soubory Vsct)](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)   
 [XML schéma VSCT – referenční informace](../../extensibility/vsct-xml-schema-reference.md)