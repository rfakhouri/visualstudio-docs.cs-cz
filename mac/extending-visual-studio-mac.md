---
title: Rozšíření sady Visual Studio pro Mac
description: Visual Studio pro Mac je funkce lze rozšířit pomocí modulů s názvem balíčků rozšíření. První část tohoto průvodce vytvoří jednoduchý Visual Studio pro balíček rozšíření Mac vložení datum a čas do dokumentu. Druhá část tohoto průvodce představuje základní informace o systému balíček rozšíření a některé z rozhraní API, která tvoří základ sady Visual Studio for Mac.
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.technology: vs-ide-sdk
ms.assetid: D5245AB0-8404-426B-B538-F49125E672B2
ms.openlocfilehash: 4ba57dde546ff6827c6d0d137e907174c0699dbb
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/07/2018
---
# <a name="extending-visual-studio-for-mac"></a>Rozšíření sady Visual Studio pro Mac

Visual Studio pro Mac se skládá ze sady modulů s názvem *balíčků rozšíření*. Rozšiřující balíčky můžete zavádět nové funkce pro Visual Studio pro Mac, například podporu pro další jazyk nebo novou šablonu projektu.

Rozšiřující balíčky sestavit z *rozšíření* body dalších balíčků rozšíření. Rozšíření body jsou zástupné symboly pro oblasti, které lze rozšířit natolik, jako jsou nabídky nebo seznam příkazů IDE. Balíček rozšíření můžete vytvořit z bodu rozšíření tak, že zaregistrujete uzlu strukturovaných dat nazývaný rozšíření, jako je například nové položky nabídky nebo nový příkaz. Každé rozšíření bod přijímá určité typy rozšíření, jako například *příkaz*, *Pad*, nebo *PSTŠablona*. Modul, který obsahuje body rozšíření je volána *doplňku hostitele*, jak ho můžete rozšířit pomocí dalších balíčků rozšíření.

Přizpůsobení sady Visual Studio pro Mac, můžete vytvořit balíček rozšíření, který sestavuje z bodů rozšíření obsažená v přidání hostitele v rámci existující knihovny v sadě Visual Studio pro Mac, které jsou popsány v následujícím diagramu:

![Architektura doplňků](media/extending-visual-studio-mac-addin1.png)

Aby mohl balíček rozšíření vytvářet ze sady Visual Studio pro Mac musí mít rozšíření, která sestavení z existující body rozšíření v sadě Visual Studio pro Mac IDE. Pokud balíček rozšíření závisí na bod rozšíření, která je definována v u hostitelů, se říká, že je tak, aby měl _závislostí_ na tento balíček rozšíření.

Výhodou tohoto modulární návrhu je, Visual Studio pro Mac je rozšiřitelný – existuje mnoho bodů rozšíření, které mohou být vytvořeny při s balíčky vlastní rozšíření. Příklady aktuální balíčků rozšíření zahrnují podporu pro C# a F #, ladicí nástroje a šablony projektů.

> [!NOTE]
> **Poznámka:**: Pokud máte projekt Maker doplněk, který byl vytvořen ještě před Add-in Maker 1.2, budete muset migrovat projektu, jak je uvedeno v krocích [zde](https://mhut.ch/addinmaker/1.2).

<!---The [Walkthrough](~/extending-visual-studio-mac-walkthrough.md) topic explains how to build an extension package that uses a *Command* to insert the date and time into an open text document.--->

V této části vypadá na různých soubory generované Maker Add-in a příkaz rozšíření dat vyžaduje.

## <a name="attribute-files"></a>Atribut soubory

Rozšiřující balíčky ukládat metadata o jejich název, verzi, závislosti a další informace v jazyce C# atributy. Maker Add-in vytvoří dva soubory, `AddinInfo.cs` a `AssemblyInfo.cs` tyto informace uspořádat a uložit. Rozšiřující balíčky musí mít jedinečné ID. a obor názvů zadaný v jejich *doplněk atribut*:

```
[assembly:Addin (
   "DateInserter",
   Namespace = "DateInserter",
   Version = "1.0"
)]
```

Rozšiřující balíčky také na rozšiřující balíčky, které vlastní rozšíření body, které se připojte deklarovat závislosti. Automaticky se odkazuje v čase vytvoření buildu.

Kromě toho další odkazy jde přidat prostřednictvím uzlu odkazu Add-in v panelu pro řešení pro projekt, jako jsou znázorněny na následujícím obrázku:

![Vložit snímek datum](media/extending-visual-studio-mac-addin13.png)

Mají také jejich odpovídajících `assembly:AddinDependency ` atributy přidané na čas sestavení. Jakmile jsou deklarace metadata a závislosti na místě, můžete se zaměřit na základní stavební kameny pro balíček rozšíření.

## <a name="extensions-and-extension-points"></a>Rozšíření a rozšíření body

Bod rozšíření je zástupný symbol, který určuje strukturu dat (typ), zatímco rozšíření definuje data, která vyhovuje pro struktury určeného bod konkrétní rozšíření. Rozšíření odkazuje určují, jaký typ rozšíření, se může přijmout v jeho deklaraci. Rozšíření jsou deklarováno s použitím názvy typů nebo rozšíření cesty. Najdete v článku [odkaz na rozšíření bodu](http://monoaddins.codeplex.com/wikipage?title=Extension%20Points&referringTitle=Description%20of%20Add-ins%20and%20Add-in%20Roots) pro podrobnější vysvětlení o tom, jak vytvořit bod rozšíření, které potřebujete.

Architektura bodu rozšíření nebo rozšíření udržuje vývoj sady Visual Studio pro Mac rychlé a modulární. 

<!--Since there are a large number of extension types, this article focuses on the ones used in the extension package that was built in the [Walkthrough](~/extending-visual-studio-mac-walkthrough.md).-->

### <a name="command-extensions"></a>Příkaz rozšíření

<!--[Walkthrough](~/extending-visual-studio-mac-walkthrough.md) uses a Command Extension - an extension that points to methods that are called every time it is executed. -->

Příkaz rozšíření jsou rozšíření, které odkazují na metody, které se nazývají pokaždé, když se spustí.

Přidávání položek do rozšíření příkaz jsou definovány `/MonoDevelop/Ide/Commands` bodu rozšíření. Jsme definovali naše rozšíření v `Manifest.addin.xml` následujícím kódem:

 ```
<Extension path="/MonoDevelop/Ide/Commands/Edit">
  <command id="DateInserter.DateInserterCommands.InsertDate"
            _label="Insert Date"
            _description="Insert the current date"
            defaulthandler="DateInserter.InsertDateHandler" />
</Extension>
```

Rozšíření uzlu obsahuje cestu atribut, který určuje rozšíření bod, který ho je zapojení do, v takovém případě `/MonoDevelop/Ide/Commands/Edit`. Kromě toho funguje jako nadřazený uzel k příkazu. Příkaz uzel má následující atributy:

*   **ID** -Určuje identifikátor pro tento příkaz. Identifikátory příkazů musí být deklarována jako členové výčtu a slouží k připojení k CommandItems příkazy.
*   **_label** – text, který se zobrazí v nabídkách.
*   **_description** – text, který má být zobrazen jako popisek pro tlačítka panelu nástrojů.
*   **defaultHandler** – Určuje `CommandHandler` třídu, která pohání příkaz

<!--To invoke the command from the Edit Menu, the walkthrough creates a CommandItem extension that plugs into the `/MonoDevelop/Ide/MainMenu/Edit` extension point:-->

CommandItem rozšíření, která po zapojení do `/MonoDevelop/Ide/MainMenu/Edit` rozšíření bod je znázorněn v následujícím fragmentu kódu:

```
<Extension path="/MonoDevelop/Ide/MainMenu/Edit">
  <commanditem id="DateInserter.DateInserterCommands.InsertDate" />
</Extension>
```

CommandItem umístí příkaz zadaný v jeho atribut id do nabídky. Tento CommandItem je rozšíření `/MonoDevelop/Ide/MainMenu/Edit` rozšíření bod, který umožňuje popisek příkazu se zobrazí v **nabídce Úpravy**. Všimněte si, že **id** ve CommandItem odpovídá id uzlu příkaz `InsertDate`. Pokud byste chtěli odebrat CommandItem, **vložit datum** možnost zmizí z nabídky upravit.

### <a name="command-handlers"></a>Obslužné rutiny příkazů

`InsertDateHandler` Je rozšířením `CommandHandler` třídy. Přepíše dvě metody, `Update` a `Run`. `Update` Je dotazován metoda vždy, když je příkaz zobrazí v nabídce nebo proveden prostřednictvím vazeb klíče. Změnou objekt informace můžete zakázat příkaz nebo jejím, naplnit pole příkazy a další. To `Update` metoda zakáže příkaz, pokud nemůže najít aktivní *dokumentu* s *TextEditor* k vložení textu do:

```
protected override void Update (CommandInfo info)
{
    info.Enabled = IdeApp.Workbench.ActiveDocument?.Editor != null;
}
```

Potřebujete přepsat `Update` metoda, pokud máte speciální logiku pro povolení nebo skrytí příkaz. `Run` Metoda provede vždy, když uživatel spustí příkaz, který v tomto případě nastane, když uživatel vybere příkazu v nabídce Upravit. Tato metoda vloží datum a čas pomocí kurzoru v textovém editoru:

```
protected override void Run ()
{
  var editor = IdeApp.Workbench.ActiveDocument.Editor;
  var date = DateTime.Now.ToString ();
  editor.InsertAtCaret (date);
}
```

Typ příkazu deklarovat jako člena výčtu v rámci `DateInserterCommands`:

```
public enum DateInserterCommands
{
  InsertDate,
}
```

Sváže společně příkaz i jeho CommandItem – CommandItem tento příkaz volá, když je vybraný CommandItem **nabídce Úpravy**.

## <a name="ide-apis"></a>Rozhraní API IDE

<!--The extension package detailed in the [Walkthrough](~/extending-visual-studio-mac-walkthrough.md) deals with the Text Editor in Visual Studio for Mac, but this is only one of many possible areas for customization. -->

Informace o rozsahu oblasti, které jsou k dispozici pro vývoj najdete v tématu [odkaz na rozšíření stromu](http://monodevelop.com/Developers/Articles/Extension_Tree_Reference) a [přehled rozhraní API](http://monodevelop.com/Developers/Articles/API_Overview). Při vytváření balíčků pokročilé rozšíření, se také podívat na [vývojáře články](http://monodevelop.com/Developers/Articles). Dole je částečný seznam oblastí pro přizpůsobení:

*   Dotyková zařízení
*   Schémata vazeb klíče
*   Zásady
*   Formátování kódu
*   Formáty souborů projektu
*   Předvolby panelů
*   Možnosti panelů
*   Protokoly ladicí program
*   Ladicí program vizualizérech
*   Rozložení pracovního prostoru
*   Uzly stromu pad řešení
*   Okraje editoru zdroje
*   Moduly testů jednotek
*   Generátory kódu
*   Fragmenty kódu
*   Cílové rozhraní
*   Cílový modul runtime
*   VC back EndY
*   Refaktoring
*   Spuštění obslužné rutiny
*   zvýraznění syntaxe

## <a name="additional-information"></a>Další informace

> [!NOTE]
Pracujeme na vylepšení scénáře rozšíření pro Visual Studio for Mac. Pokud vytváříte rozšíření a další nápovědu nebo informace nebo chcete poskytnout zpětnou vazbu, vyplňte [Visual Studio pro vytváření obsahu rozšíření Mac](https://aka.ms/vsmac-extensions-survey) formuláře.