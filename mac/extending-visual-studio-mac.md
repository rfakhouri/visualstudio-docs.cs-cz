---
title: Rozšíření sady Visual Studio pro Mac
description: Visual Studio pro Mac funkce, je možné rozšířit pomocí modulů s názvem balíčky rozšíření. První část tohoto průvodce vytvoří jednoduchý Visual Studio for Mac rozšíření balíčku vložit datum a čas do dokumentu. Druhá část Tento průvodce představuje Principy systému rozšíření balíčku a některé základní rozhraní API, která tvoří základ sady Visual Studio pro Mac.
author: alanjclark
ms.author: alcl
ms.date: 05/07/2019
ms.technology: vs-ide-sdk
ms.assetid: D5245AB0-8404-426B-B538-F49125E672B2
ms.openlocfilehash: f9c14b408a7714f06ae8a96b0ecc60dfc4b8ebe7
ms.sourcegitcommit: 7fbfb2a1d43ce72545096c635df2b04496b0be71
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/09/2019
ms.locfileid: "67691650"
---
# <a name="extending-visual-studio-for-mac"></a>Rozšíření sady Visual Studio pro Mac

Visual Studio pro Mac se skládá ze sady modulů s názvem *balíčky rozšíření*. Balíčky rozšíření můžete použít pro zavedení nových funkcí do sady Visual Studio pro Mac, jako třeba podporu pro další jazyk nebo nové šablony projektu.

Balíčky rozšíření sestavení z *rozšíření* body jiné balíčky rozšíření. Rozšiřovací body jsou zástupné symboly pro oblasti, které lze rozšířit natolik, jako je například nabídka nebo seznam příkazů prostředí IDE. Balíček rozšíření můžete vytvořit z rozšiřovacím bodem registrace uzlu strukturovaných dat, kterým se říká rozšíření, jako je například novou položku nabídky nebo nový příkaz. Každý rozšiřovací bod přijímá určité typy rozšíření například *příkaz*, *panel*, nebo *PSTŠablona*. Modul, který obsahuje Rozšiřovací body je volána *hostitele doplňku*, jak je možné rozšířit pomocí jiné balíčky rozšíření.

Přizpůsobení sady Visual Studio pro Mac, můžete vytvořit balíček rozšíření, který vytváří z Rozšiřovací body, které jsou obsaženy v hostiteli doplňku v rámci existující knihovny v sadě Visual Studio pro Mac, jak je znázorněno v následujícím diagramu:

![Architektura doplňků](media/extending-visual-studio-mac-addin1.png)

Pořadí rozšíření balíčku k sestavení ze sady Visual Studio pro Mac musí mít rozšíření, která sestavení z předem existujících Rozšiřovací body v sadě Visual Studio pro Mac integrovaného vývojového prostředí. Když balíček rozšíření závisí na rozšiřovacím bodem definované v hostiteli, který doplněk, to se říká, že mají _závislost_ na tento balíček rozšíření.

Výhodou této modulárního návrhu je, že Visual Studio for Mac je možné rozšířit – existuje mnoho Rozšiřovací body, které můžou být postavené na pomocí rozšíření vlastních balíčků. Příklady aktuální balíčky rozšíření zahrnují podporu pro C# a F#ladicího programu nástroje a šablony projektů.

> [!NOTE]
> Pokud máte projekt doplňku tvůrce, který byl vytvořen ještě před doplněk Tvůrce 1.2, budete muset migrovat projekt, jak je uvedeno v krocích [tady](https://mhut.ch/addinmaker/1.2).

<!---The [Walkthrough](~/extending-visual-studio-mac-walkthrough.md) topic explains how to build an extension package that uses a *Command* to insert the date and time into an open text document.--->

Této části se probírají různé soubory generované záznamem pro tvůrce Add-in a vyžaduje data rozšíření příkazu.

## <a name="attribute-files"></a>Atribut soubory

Balíčky rozšíření ukládají metadata o jejich název, verzi, závislosti a další informace v jazyce C# atributy. Doplněk tvůrce vytvoří dva soubory `AddinInfo.cs` a `AssemblyInfo.cs` můžete ukládat a uspořádávat tyto informace. Balíčky rozšíření musí mít jedinečné ID a obor názvů určený ve svých  *`Addin` atribut*:

```csharp
[assembly:Addin (
   "DateInserter",
   Namespace = "DateInserter",
   Version = "1.0"
)]
```

Balíčky rozšíření musí deklarovat také závislosti na balíčky rozšíření, které vlastní rozšíření body, které jsou pružný, které jsou automaticky odkazována v okamžiku sestavení.

Kromě toho další odkazy jde přidat prostřednictvím doplňku referenční uzel v oblasti řešení pro projekt, jako jsou znázorněny na následujícím obrázku:

![Vložit datum – snímek obrazovky](media/extending-visual-studio-mac-addin13.png)

Mají také odpovídající `assembly:AddinDependency` atributy přidané na čas sestavení. Jakmile deklarace metadata a závislosti jsou na místě, můžete se soustředit na základní stavební bloky balíček rozšíření.

## <a name="extensions-and-extension-points"></a>Rozšíření a Rozšiřovací body

Rozšiřovacím bodem je zástupný symbol, který definuje strukturu dat (typ), zatímco rozšíření definuje data, která odpovídá struktuře určené konkrétní rozšiřovací bod. Rozšiřovací body určit, jaký typ rozšíření se může přijmout v jeho deklaraci. Rozšíření jsou deklarovány pomocí názvy typů nebo rozšíření cesty. Najdete v článku [rozšiřovací bod odkaz](https://github.com/mono/mono-addins/wiki/Extension-Points) najdete podrobnější vysvětlení o tom, jak vytvořit rozšiřovací bod, který potřebujete.

Architektura rozšíření/rozšíření bodu udržuje vývoje sady Visual Studio pro Mac rychlou modulární.

<!--Since there are a large number of extension types, this article focuses on the ones used in the extension package that was built in the [Walkthrough](~/extending-visual-studio-mac-walkthrough.md).-->

### <a name="command-extensions"></a>Příkaz rozšíření

<!--[Walkthrough](~/extending-visual-studio-mac-walkthrough.md) uses a Command Extension - an extension that points to methods that are called every time it is executed. -->

Příkaz rozšíření jsou přípony, které odkazují na metody, které jsou volány pokaždé, když je proveden.

Příkaz rozšíření, které jsou definovány pomocí přidání položek `/MonoDevelop/Ide/Commands` rozšiřovací bod. Jsme definovali naše rozšíření v `Manifest.addin.xml` následujícím kódem:

 ```xml
<Extension path="/MonoDevelop/Ide/Commands/Edit">
  <command id="DateInserter.DateInserterCommands.InsertDate"
            _label="Insert Date"
            _description="Insert the current date"
            defaulthandler="DateInserter.InsertDateHandler" />
</Extension>
```

Uzel výrazu obsahuje atribut cesty, která určuje rozšiřovací bod, který ho se připojit k, v tomto případě `/MonoDevelop/Ide/Commands/Edit`. Kromě toho funguje jako nadřazený uzel k příkazu. Příkaz uzel má následující atributy:

* `id` : Určuje identifikátor pro tento příkaz. Identifikátory příkazů musí být deklarována jako členy výčtu a slouží k připojení k CommandItems příkazy.
* `_label` -Text zobrazený v nabídkách.
* `_description` – Text, který se zobrazí jako popisek pro tlačítka panelu nástrojů.
* `defaultHandler` : Určuje, že `CommandHandler` třída, která je základem příkazu

<!--To invoke the command from the Edit Menu, the walkthrough creates a CommandItem extension that plugs into the `/MonoDevelop/Ide/MainMenu/Edit` extension point:-->

CommandItem rozšíření, které zpřístupní `/MonoDevelop/Ide/MainMenu/Edit` rozšiřovací bod je znázorněn v následujícím fragmentu kódu:

```xml
<Extension path="/MonoDevelop/Ide/MainMenu/Edit">
  <commanditem id="DateInserter.DateInserterCommands.InsertDate" />
</Extension>
```

CommandItem umístí příkaz zadaný v jeho `id` atribut do nabídky. Rozšíření této CommandItem `/MonoDevelop/Ide/MainMenu/Edit` rozšiřovacího bodu, což zajišťuje popisek příkazu se zobrazí v **nabídky Úpravy**. Všimněte si, že ID v CommandItem odpovídá ID uzlu příkaz `InsertDate`. Pokud odeberete CommandItem, **vložit datum** možnost zmizí z nabídky Úpravy.

### <a name="command-handlers"></a>Obslužné rutiny příkazů

`InsertDateHandler` Je rozšířením `CommandHandler` třídy. Dvě metody, přepíše `Update` a `Run`. `Update` Metoda dotazuje se vždy, když je příkaz zobrazí v nabídce nebo provést pomocí klávesové zkratky. Změnou informace o objektu, můžete zakázat příkaz nebo je nastavit jako neviditelné, naplnit pole příkazy a další. To `Update` metoda zakáže příkazu, pokud nemůže najít aktivní *dokumentu* s *TextEditor* vložit text do:

```csharp
protected override void Update (CommandInfo info)
{
    info.Enabled = IdeApp.Workbench.ActiveDocument?.Editor != null;
}
```

Chcete přepsat `Update` metodu, pokud máte zvláštní logiku pro povolení nebo skrytí příkazu. `Run` Metoda spustí vždy, když uživatel spustí příkaz, který v tomto případě nastane, když uživatel vybere příkaz z nabídky Úpravy. Tato metoda vloží data a času blikající kurzor v textovém editoru:

```csharp
protected override void Run ()
{
  var editor = IdeApp.Workbench.ActiveDocument.Editor;
  var date = DateTime.Now.ToString ();
  editor.InsertAtCaret (date);
}
```

Typ příkazu deklarovat jako člen výčtového typu v rámci `DateInserterCommands`:

```csharp
public enum DateInserterCommands
{
  InsertDate,
}
```

Příkaz i jeho CommandItem jsou nyní spojených dohromady – CommandItem volá příkaz při výběru CommandItem z **nabídky Úpravy**.

## <a name="ide-apis"></a>Integrované vývojové prostředí rozhraní API

<!--The extension package detailed in the [Walkthrough](~/extending-visual-studio-mac-walkthrough.md) deals with the Text Editor in Visual Studio for Mac, but this is only one of many possible areas for customization. -->

Informace o rozsahu oblastí, které jsou k dispozici pro vývoj najdete v článku [odkaz na rozšíření stromu](http://monodevelop.com/Developers/Articles/Extension_Tree_Reference) a [přehled rozhraní API](http://monodevelop.com/Developers/Articles/API_Overview). Při vytváření pokročilých rozšíření balíčků, také odkazovat na [článků Vývojář](http://monodevelop.com/Developers/Articles). Následuje částečný seznam oblastí pro přizpůsobení:

* Ladicí systém
* Schémata vazeb klíče
* Zásady
* Formátování kódu
* Formáty souborů projektu
* Předvolby panelů
* Možnosti panelů
* Protokoly ladicího programu
* Vizualizérů ladění
* Rozložení pracovního prostoru
* Uzly stromu panel řešení
* Okraje editoru zdroje
* Moduly testu jednotek
* Generátory kódu
* Fragmenty kódu
* Cílové architektury
* Cílový modul runtime
* VC back EndY
* Refaktoring
* Spuštění obslužné rutiny
* Zvýrazňování syntaxe

## <a name="extending-the-new-editor"></a>Rozšíření nového editoru

Visual Studio pro Mac [zavádí nové nativní Cocoa textového editoru uživatelského rozhraní](https://aka.ms/vs/mac/editor/learn-more) postavené na stejné editor vrstvy ze sady Visual Studio na Windows.

Jednou z mnoha výhod sdílení editor mezi Visual Studio a Visual Studio for Mac je, že kód zaměřený editor sady Visual Studio, mohou být přizpůsobeny pro spuštění v sadě Visual Studio pro Mac.

> [!NOTE]
> Nový editor podporuje jenom C# soubory v tuto chvíli. Ostatní jazyky a formátů souborů se otevře v editoru starší verze. Starší verze editor implementovat ale některé z editoru sady Visual Studio rozhraní API je popsáno níže.

### <a name="visual-studio-editor-overview"></a>Přehled editoru sady Visual Studio

![Architektura editoru sady Visual Studio](media/vs-editor-architecture.png)

Před na podrobnosti o rozšíření specifické pro Visual Studio pro Mac, je dobré znát další informace o sdílených samotný editor. Níže je několik prostředků, které může prohloubit tyto znalosti:

* [Rozhraní Managed Extensibility Framework](https://docs.microsoft.com/dotnet/framework/mef/index)
* [MEF v editoru](https://docs.microsoft.com/visualstudio/extensibility/managed-extensibility-framework-in-the-editor)
* [Práce v editoru](https://docs.microsoft.com/visualstudio/extensibility/inside-the-editor)
* [Rozšiřovací body služeb jazyka a editoru](https://docs.microsoft.com/visualstudio/extensibility/language-service-and-editor-extension-points)
* [Video Úvod do architektury editoru](https://www.youtube.com/watch?v=PkYVztKjO9A)

Pomocí těchto prostředků v dolním jsou primární koncepty, které potřebujete znát [ `ITextBuffer` ](https://docs.microsoft.com/dotnet/api/microsoft.visualstudio.text.itextbuffer) a [ `ITextView` ](https://docs.microsoft.com/dotnet/api/microsoft.visualstudio.text.editor.itextview):

* `ITextBuffer` Je reprezentací v paměti text, který můžete v průběhu času měnit. `CurrentSnapshot` Vlastnost `ITextBuffer` vrátí *neměnné* reprezentace aktuální obsah vyrovnávací paměti, instance `ITextSnapshot`. Po provedení úprav ve vyrovnávací paměti, vlastnost CurrentSnapshot se aktualizuje na nejnovější verzi. Analyzátory, můžete si prohlédnout snímek text v libovolném vlákně a jeho obsah je zaručeno, že nikdy nezmění.

* `ITextView` Je reprezentace uživatelského rozhraní jak `ITextBuffer` se vykreslí na obrazovce v ovládacím prvku editoru. Obsahuje odkaz na jeho textové vyrovnávací paměti, stejně jako `Caret`, `Selection`a další koncepty související s Uživatelským rozhraním.

Pro danou [ `MonoDevelop.Ide.Gui.Document` ](http://source.monodevelop.com/#MonoDevelop.Ide/MonoDevelop.Ide.Gui/Document.cs,4e960d4735f089b5), můžete načíst související základní `ITextBuffer` a `ITextView` prostřednictvím `Document.GetContent<ITextBuffer>()` a `Document.GetContent<ITextView>()` v uvedeném pořadí.

## <a name="additional-information"></a>Další informace

> [!NOTE]
> Aktuálně pracujeme na vylepšení scénáře rozšíření pro Visual Studio pro Mac. Pokud vytváříte rozšíření a potřebujete další pomoc nebo informace nebo chcete poskytnout zpětnou vazbu, vyplňte prosím [sady Visual Studio pro Mac rozšíření vytváření](https://aka.ms/vsmac-extensions-survey) formuláře.

## <a name="see-also"></a>Viz také:

- [Vývoj rozšíření sady Visual Studio (ve Windows)](/visualstudio/extensibility/starting-to-develop-visual-studio-extensions)