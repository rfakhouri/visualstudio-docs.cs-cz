---
title: Vytváření a konfigurace členů typů (návrhář tříd)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- vs.classdetails.method
- vs.classdetails.property
- vs.classdetails.parameter
- vs.classdetails.event
- vs.classdetails.field
helpviewer_keywords:
- Class Designer [Visual Studio], member creation
- type members, modifying in Class Designer
- parameters [ASP.NET Web Services], adding to methods
- type members, configuring
- type members
- members
- type members, creating
- members, creating
- Class Designer [Visual Studio], type members
- read-only information, displaying
- members, configuring
- methods [Visual Studio], adding parameters
- Class Details window
- Class Details window, member creation
ms.assetid: 42af8738-3738-4ca7-82ff-edf573a68f96
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0b5e60da7ea3058f192ad59dcc57a493115a751b
ms.sourcegitcommit: 4c0db930d9d5d8b857d3baf2530ae89823799612
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/10/2018
---
# <a name="create-and-configure-type-members-in-class-designer"></a>Vytvořit a nakonfigurovat členy typu v Návrháři tříd

Můžete přidat diagram tito členové pro typy třídy a konfigurace členů v **podrobností třídy** okno:

|**Typ**|**Členů, které může obsahovat**|
|--------------|--------------------------------|
|Třída|metoda, vlastnost (pro C# a Visual Basic), pole, událost (pro C# a Visual Basic), konstruktor (metoda), konstruktor (metoda), konstanta|
|Výčet|člen|
|Rozhraní|metoda, vlastnost, událost (pro C# a Visual Basic)|
|Abstraktní třída|metoda, vlastnost (pro C# a Visual Basic), pole, událost (pro C# a Visual Basic), konstruktor (metoda), konstruktor (metoda), konstanta|
|Struktura (struktura v jazyce C#)|metoda, vlastnost (pro C# a Visual Basic), pole, událost (pro C# a Visual Basic), konstruktor (metoda), konstanta|
|Delegát|parametr|
|Modul (pouze VB)|metoda, vlastnost, pole, událost, konstruktor, konstanta|

> [!NOTE]
> Když přístupové objekty get a set nepotřebují další logiku, můžete deklaraci vlastnosti zestručnit pomocí automaticky implementovaných vlastností (pouze jazyk C#). Zobrazit se úplné podpis, **diagramu tříd** nabídce zvolte **změnit členy formát** > **zobrazení úplné podpis**. Další informace o automaticky implementované vlastnosti najdete v tématu [Auto-Implemented vlastnosti](/dotnet/csharp/programming-guide/classes-and-structs/auto-implemented-properties).

## <a name="common-tasks"></a>Běžné úlohy

|Úloha|Podpora obsahu|
|----------|------------------------|
|**Začínáme:** předtím, než vytvoříte a nakonfigurujete členy typu, je nutné otevřít **podrobností třídy** okno.|- [Otevřete okno podrobností třídy](creating-and-configuring-type-members.md#open-the-class-details-window)<br />- [Poznámky pro použití podrobnosti – třída](creating-and-configuring-type-members.md#class-details-usage-notes)<br />- [Zobrazení jen pro čtení informací](creating-and-configuring-type-members.md#display-of-read-only-information)<br />- [Klávesnice a myši zkratky v okně diagramu tříd a podrobností třídy](keyboard-and-mouse-shortcuts-in-the-class-diagram-and-class-details-window.md)|
|**Vytvořit a upravit členy typu:** můžete vytvořit nové členy, upravit členy a přidat parametry do metody pomocí **podrobností třídy** okno.|- [Vytváření členů](creating-and-configuring-type-members.md#create-members)<br />- [Upravit členy typu](creating-and-configuring-type-members.md#modify-type-members)<br />- [Přidání parametrů do metody](creating-and-configuring-type-members.md#add-parameters-to-methods)|

## <a name="open-the-class-details-window"></a>Otevřete okno podrobností třídy

Ve výchozím nastavení **podrobností třídy** okno se zobrazí automaticky při otevření nové diagramu tříd. V tématu [postupy: Přidání diagramů tříd do projektů](how-to-add-class-diagrams-to-projects.md)). Můžete také otevřít **podrobností třídy** okno následujícími způsoby:

- Klikněte pravým tlačítkem na libovolné třídy v diagramu zobrazíte z kontextové nabídky a potom vyberte **podrobností třídy**.

- Vyberte **zobrazení** > **ostatní okna** > **podrobností třídy** z řádku nabídek.

## <a name="create-members"></a>Vytváření členů

Člen můžete vytvořit pomocí libovolného z následujících nástrojů:

- **Návrhář tříd**

- **Třídy podrobnosti** nástrojů okna

- **Třídy podrobnosti** okna

> [!NOTE]
> Pomocí postupů v tomto oddíle můžete také vytvořit konstruktory a destruktory. Nezapomínejte, že konstruktory a destruktory jsou zvláštní druhy metody a jako takový se objeví v **metody** prostředí obrazců diagramu tříd a v **metody** části  **Třídy podrobnosti** okno mřížky.

> [!NOTE]
> Parametr je jediná entita, kterou můžete přidat k delegátu. Všimněte si, že postup právo, vytvořit člena pomocí **podrobností třídy** nástrojů okna ' není platný pro tuto akci.

### <a name="create-a-member-using-class-designer"></a>Vytvoření člena s použitím návrháře – třída

1.  Klikněte pravým tlačítkem na typ, do které chcete přidat člena, přejděte na **přidat**a pak vyberte typ člena, který chcete přidat.

     Vytvoří se nový podpis člena a přidá se k typu. Ho je zadána výchozí název, který můžete změnit v **návrhář tříd**, **podrobností třídy** okno, nebo **vlastnosti** okno.

2.  Volitelně můžete určit další detaily členu, například jeho typ.

### <a name="create-a-member-using-the-class-details-window-toolbar"></a>Vytvoření členem pomocí panelu nástrojů v okně podrobností třídy

1.  Na ploše diagramu vyberte typ, ke kterému chcete přidat člen.

     Získá typ fokus a její obsah se zobrazí v **podrobností třídy** okno.

2.  V **podrobností třídy** nástrojů v okně klikněte na ikonu horní a vyberte **nový \<člen >** z rozevíracího seznamu.

     Posune kurzor **název** pole řádek pro typ člena, který chcete přidat. Například pokud jste klikli na **novou vlastnost**, kurzor se přesune na nový řádek v **vlastnosti** části **podrobností třídy** okno.

3.  Zadejte název členu, který chcete vytvořit, a stiskněte klávesu Enter (nebo jinak přesuňte fokus, například stisknutím klávesy Tab).

     Vytvoří se nový podpis člena a přidá se k typu. Člen nyní existuje v kódu a zobrazí se v **návrhář tříd**, **podrobností třídy** okno a v okně Vlastnosti.

4.  Volitelně můžete určit další detaily členu, například jeho typ.

### <a name="create-a-member-using-the-class-details-window"></a>Vytvoření členem pomocí okno podrobností třídy

1.  Na ploše diagramu vyberte typ, ke kterému chcete přidat člen.

     Získá typ fokus a její obsah se zobrazí v **podrobností třídy** okno.

2.  V **podrobností třídy** okno, v oddílu, který obsahuje typ člena, který chcete přidat, klikněte na tlačítko  **\<přidat člena >**. Například pokud chcete přidat pole, klikněte na možnost  **\<přidat pole >**.

3.  Zadejte název členu, který chcete vytvořit, a stiskněte klávesu Enter.

     Vytvoří se nový podpis člena a přidá se k typu. Člen nyní existuje v kódu a zobrazí se v **návrhář tříd**, **podrobností třídy** okno a v okně Vlastnosti.

4.  Volitelně můžete určit další detaily členu, například jeho typ.

     **Poznámka:** klávesové zkratky můžete také použít k vytvoření členy. Další informace najdete v tématu [klávesové zkratky a zkratky myši v okně diagramu tříd a podrobností třídy](keyboard-and-mouse-shortcuts-in-the-class-diagram-and-class-details-window.md).

## <a name="modify-type-members"></a>Upravit členy typu

V Návrháři tříd můžete upravit členy typů, které se zobrazí v diagramu. Můžete upravit členy libovolného typu, které se zobrazí v diagramu třídy a nejsou jen pro čtení. Upravit členy typu pomocí úpravy v místě na návrhovou plochu, vlastnosti – okno a **podrobností třídy** okno.

Všechny členy zobrazené v **podrobností třídy** okno představují členy typy v diagramu tříd. Existují čtyři typy členů: metody, vlastnosti, pole a události.

Všechny řádky členů jsou zobrazeny pod nadpisy, které je seskupují podle druhu. Například všechny vlastnosti se zobrazí v části **vlastnosti**, který jako uzel v mřížce, možné sbalit nebo rozbalit.

Každý řádek členu zobrazuje následující prvky:

- **Ikona člena**

     Každý druh členu znázorňuje jeho vlastní ikona. Bod myší na ikonu člen zobrazíte podpis člena. Kliknutím na ikonu členu nebo na prázdné znaky vlevo od ikony členu vyberete řádek.

- **Název členu**

     **Název** sloupce v řádku člen zobrazí název člena. Tento název se zobrazí také v **název** vlastnost v okně Vlastnosti. Tuto buňku můžete použít ke změně názvu jakéhokoli členu, který má oprávnění pro čtení i zápis.

     Pokud **název** sloupec je příliš úzké, chcete-li zobrazit celý název odkazující myši na název člena zobrazí celý název.

- **Typ člena**

     **MemberType** buňky používá technologii IntelliSense, které lze vybrat ze seznamu všechny typy, které jsou dostupné v aktuálním projektu nebo odkazované projekty.

- **Člen modifikátor**

     Změňte buď modifikátor viditelnosti člena `Public` (`public`), `Private` (`private`), `Friend` (`internal`) `Protected` (`protected`), `Protected``Friend` (`protected``internal`), nebo `Default`.

- **\<Přidání člena >**

     Poslední řádek v **podrobností třídy** okno obsahuje text  **\<přidat člena >** v **název** buňky. Pokud na tuto buňku klikněte, můžete vytvořit nový člen. Další informace najdete v tématu [vytvořit členy](creating-and-configuring-type-members.md#create-members).

- **Vlastnosti člena v okně vlastností**

     **Podrobností třídy** zobrazují podmnožinu vlastnosti člena, které se zobrazují v okně Vlastnosti. Změna vlastnosti na jednom místě aktualizuje hodnotu vlastnosti globálně. Aktualizuje se i zobrazení hodnoty členu v jiném umístění.

- **Shrnutí**

     **Souhrnné** buňky zpřístupní souhrnné informace o člen. Klikněte na tlačítko se třemi tečkami v **Souhrn** buňky do umožňuje zobrazit nebo upravit informace o **Souhrn**, **návratového typu**, a **poznámky** pro člena .

- **Skrýt**

     Když **skrýt** je zaškrtnuté políčko, člen není zobrazen v typu.

### <a name="to-modify-a-type-member"></a>Změna členu typu

1.  Pomocí Návrháře tříd vyberte typ.

2.  Pokud **podrobností třídy** okno se nezobrazí, klikněte na tlačítko **podrobností třídy** okno tlačítka na panelu nástrojů návrhář tříd.

3.  Upravte hodnoty v polích **podrobností třídy** okno mřížky. Po každé úpravě stiskněte klávesu ENTER nebo jinak přesuňte fokus z upravovaného pole, například stisknutím klávesy TAB. Úpravy se v kódu projeví okamžitě.

    > [!NOTE]
    > Pokud chcete změnit pouze název členu, můžete to provést úpravou na místě.

## <a name="add-parameters-to-methods"></a>Přidání parametrů do metody

Přidání parametrů do metod pomocí **podrobností třídy** okno. Parametry lze konfigurovat jako povinné, či volitelné. Poskytnutí hodnotu **volitelné výchozí** přikazuje parametru návrháře pro generování kódu jako volitelný parametr.

Řádky parametru obsahují následující položky:

- **Jméno**

     **Název** sloupce v řádku parametr zobrazí název parametru. Tento název se zobrazí také v **název** vlastnost v okně Vlastnosti. Tuto buňku můžete použít ke změně názvu jakéhokoli parametru, který má oprávnění pro čtení i zápis.

     Název parametru odkazující na název parametru zobrazí, pokud **název** sloupec je příliš úzké, chcete-li zobrazit celý název.

- **Typ**

     **Typ parametru** buňky používá technologii IntelliSense, která umožňuje vybrat ze seznamu všechny typy, které jsou dostupné v aktuálním projektu nebo odkazované projekty.

- **Modifikátor**

     **Modifikátor** buňky v řádku parametr přijme a zobrazí new – modifikátor parametru. Pokud chcete zadat nové – modifikátor parametrů, použijte rozevírací seznam a vyberte z **žádné**, **ref**, **out**, nebo **parametry** v C# a **ByVal**, **ByRef**, nebo **ParamArray** v jazyce VB.

- **Shrnutí**

     **Souhrn** buňky v řádku parametr umožňuje zadávání komentářů kódu, které se zobrazují v IntelliSense při zadávání parametru do editoru kódu.

- **\<Přidejte parametr >**

     Poslední řádek parametr člena obsahuje text **<add parameter>** v **název** buňky. Kliknutím na tuto buňku vytvoříte nový parametr. Další informace najdete v tématu [přidání parametru k metodě](creating-and-configuring-type-members.md#add-parameters-to-methods).

**Vlastnosti** stejný parametr vlastností zobrazených v okně se zobrazí **podrobností třídy** okno: **název**, **typu**,  **Modifikátor**, **Souhrn**, a taky **volitelné výchozí** vlastnost. Změnou vlastnosti na jednom místě aktualizujete hodnotu vlastnosti globálně, včetně zobrazení hodnoty v jiném umístění.

> [!NOTE]
> Pro přidání parametru s delegátem, najdete v části [vytvořit členy](creating-and-configuring-type-members.md#create-members).

> [!NOTE]
> Ačkoli je destruktor metoda, nemůže mít parametry.

### <a name="to-add-a-parameter-to-a-method"></a>Přidání parametru do metody

1.  Na ploše diagramu klikněte na typ obsahující metodu, ke které chcete přidat parametr.

     Získá typ fokus a zobrazit jeho obsah v **podrobností třídy** okno.

2.  V **podrobností třídy** okně rozbalte řádek metody, do které chcete přidat parametr.

     Se zobrazí řádek zobrazují odsazené parametr, obsahující jenom pár kulaté závorky a slova  **\<přidat parametr >.**

3.  Klikněte na tlačítko  **\<přidat parametr >**, zadejte název nového parametru a stiskněte klávesu **Enter**.

     Metoda a kód metody je přidán nový parametr. Zobrazí se v **podrobností třídy** okno a v okně Vlastnosti.

4.  Volitelně můžete určit další detaily parametru, například jeho typ.

### <a name="to-add-an-optional-parameter-to-a-method"></a>Přidání volitelného parametru do metody

1.  Na ploše diagramu klikněte na typ obsahující metodu, ke které chcete přidat volitelný parametr.

     Získá typ fokus a zobrazit jeho obsah v **podrobností třídy** okno.

2.  V **podrobností třídy** okně rozbalte řádek metody, do které chcete přidat volitelný parametr.

     Se zobrazí řádek zobrazují odsazené parametr, obsahující jenom pár kulaté závorky a slova  **\<přidat parametr >.**

3.  Klikněte na tlačítko  **\<přidat parametr >**, zadejte název nového parametru a stiskněte klávesu **Enter**.

     Metoda a kód metody je přidán nový parametr. Zobrazí se v **podrobností třídy** okno a v okně Vlastnosti.

4.  V okně vlastností zadejte hodnotu **volitelné výchozí** vlastnost. Nastavením vlastnosti Volitelné výchozí nastavíte daný parametr na volitelný.

    > [!NOTE]
    > Volitelné parametry musí být posledními parametry v seznamu parametrů.

## <a name="class-details-usage-notes"></a>Poznámky pro použití podrobnosti – třída

Poznámka: následující tipy pro použití **podrobností třídy** okno.

### <a name="editable-and-non-editable-cells"></a>Editovatelné a needitovatelné buňky

Všechny buňky v **podrobností třídy** okno se upravovat s několika výjimkami:

- Celý typ je jen pro čtení, když, například se nachází v odkazované sestavení. Když vyberete tvaru v Návrháři tříd **podrobností třídy** okně se zobrazí podrobnosti ve stavu jen pro čtení.

- V případě indexerů je název jen pro čtení a zbytek (typ, modifikátor, shrnutí) je editovatelný.

- Obecné typy všechny mít parametry jen pro čtení **podrobností třídy** okno. Chcete-li změnit obecný parametr, upravte jeho zdrojový kód.

- Název parametru typu, který je definován na obecném typu, je jen pro čtení.

- Když je rozděleno (nelze analyzovat), typ kódu **podrobností třídy** okně se zobrazí typ obsahu jen pro čtení.

### <a name="the-class-details-window-and-source-code"></a>Podrobnosti třídy okno a zdrojový kód

- Zdrojový kód můžete zobrazit kliknutím pravým tlačítkem na obrazce v **podrobností třídy** okno (nebo návrhář tříd) a potom kliknutím na zobrazení kódu. Otevře se soubor zdrojového kódu a zobrazení se posune na vybraný prvek.

- Změna zdrojového kódu se okamžitě projeví v zobrazení podpis informací v Návrháři tříd a **podrobností třídy** okno. Pokud **podrobností třídy** zavření okna v době, nové informace jsou viditelné při příštím otevření.

- Když je rozděleno (nelze analyzovat), typ kódu **podrobností třídy** okně se zobrazí typ obsahu jen pro čtení.

### <a name="clipboard-functionality-in-the-class-details-window"></a>Funkce schránky v okně podrobností třídy

Můžete kopírovat nebo vyjmout pole nebo řádky z **podrobností třídy** okno a vložit do jiného typu. Řádek můžete vyjmout, pouze pokud je jen pro čtení. Když vložíte řádek, **podrobností třídy** okno přiřadí nový název (odvozený od názvu zkopírovaného řádku) aby nedošlo ke konfliktu.

## <a name="display-of-read-only-information"></a>Zobrazení jen pro čtení informací

Návrhář tříd a **podrobností třídy** okno může zobrazit typy (a členové typy) pro následující:

- projekt, který obsahuje diagram třídy

- projekt odkazovaný z projektu, který obsahuje diagram třídy

- sestavení odkazované z projektu, který obsahuje diagram třídy

V posledních dvou případech je odkazovaná entita (typ nebo člen) v diagramu tříd, který ji reprezentuje, jen pro čtení.

Celý projekt nebo jeho části, například jednotlivé soubory, mohou být jen pro čtení. Většina běžných případů, ve kterých projekt nebo jeden z jeho souborů, je jen pro čtení, jsou takové, kdy se projekt nachází v rámci správy zdrojového kódu (a není rezervován), existuje v externím sestavení nebo když operační systém považuje soubory za soubory jen pro čtení.

**Řízení zdrojového kódu**

Protože diagramu tříd je uložený jako soubor v projektu, budete muset rezervovat projektu a uložte změny provedené v Návrháři tříd nebo **podrobností třídy** okno.

**Projekty jen pro čtení**

Projekt může být jen pro čtení z jiného důvodu než pro správu zdrojového kódu. Zavřením projektu zobrazí dialogové okno s dotazem, zda chcete přepsat soubor projektu, zahodit změny (Neukládat) nebo zavřít operaci zrušte. Pokud zvolíte přepsání, soubory projektu jsou přepsány a nastaveny pro čtení i zápis. Je přidán nový soubor diagramu tříd.

**Typy jen pro čtení**

Pokud se pokusíte uložit projekt obsahující typ, jejichž zdrojového kódu soubor je jen pro čtení, **uložit jen pro čtení souboru** se zobrazí dialogové okno, které nabízí možnosti k uložení souboru pod novým názvem nebo nové umístění nebo k přepsání souboru jen pro čtení . Pokud soubor přepíšete, nová kopie již není jen pro čtení.

Pokud soubor s kódem obsahuje chybu syntaxe, tvary zobrazující kód v daném souboru budou dočasně jen pro čtení, dokud chyba syntaxe nebude opravena. Tvary v tomto stavu zobrazí červený text a červenou ikonu, která zobrazí popisek s textem „Soubor zdrojového kódu obsahuje chybu analýzy“.

Odkazovaný typ (například typ rozhraní .NET Framework), který existuje v rámci jiného uzlu projektu nebo uzlu odkazovaného sestavení, je na návrhové ploše Návrháře tříd uveden jako jen pro čtení. Místní typ, který existuje v projektu, jež chcete otevřít, je pro čtení i zápis a jeho tvar na návrhové ploše Návrháře tříd je takto označen.

Indexery jsou pro čtení a zápis v kódu a **podrobností třídy** okno, ale název indexeru je jen pro čtení.

Částečné metody nelze upravit pomocí návrháře tříd nebo **podrobností třídy** okno; je nutné použít Editor kódu upravovat je.

Nelze upravit nativní kód C++ pomocí návrháře tříd nebo **podrobností třídy** okno; je nutné použít Editor kódu upravit nativního kódu C++.

## <a name="see-also"></a>Viz také

- [Zobrazování typů a vztahů](viewing-types-and-relationships.md)
- [Refaktoring tříd a typů](refactoring-classes-and-types.md)