---
title: "Vytváření a konfigurace členů typů (návrhář tříd) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "24"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 43bb62a2c1b6aef5827e358da2b04905e9325365
ms.sourcegitcommit: 64c7682ec3a2cbea684e716803398d4278b591d1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/15/2017
---
# <a name="creating-and-configuring-type-members-class-designer"></a>Vytváření a konfigurace členů typů (návrhář tříd)
Můžete přidat diagram tito členové pro typy třídy a konfigurace členů v **podrobností třídy** okno:
  
|**Typ**|**Členů, které může obsahovat**|  
|--------------|--------------------------------|  
|Třída|metoda, vlastnost (pro C# a Visual Basic), pole, událost (pro C# a Visual Basic), konstruktor (metoda), konstruktor (metoda), konstanta|  
|Výčet|člen|  
|Rozhraní|metoda, vlastnost, událost (pro C# a Visual Basic)|  
|Abstraktní třída|metoda, vlastnost (pro C# a Visual Basic), pole, událost (pro C# a Visual Basic), konstruktor (metoda), konstruktor (metoda), konstanta|  
|Struktura (struktura v jazyce C#)|metoda, vlastnost (pro C# a Visual Basic), pole, událost (pro C# a Visual Basic), konstruktor (metoda), konstanta|  
|Delegát|Parametr|  
|Modul (pouze VB)|metoda, vlastnost, pole, událost, konstruktor, konstanta|  
  
> [!NOTE]
>  Když přístupové objekty get a set nepotřebují další logiku, můžete deklaraci vlastnosti zestručnit pomocí automaticky implementovaných vlastností (pouze jazyk C#). Zobrazit se úplné podpis, **diagramu tříd** nabídce zvolte **změnit členy formát**, **úplné podpis zobrazení**. Další informace o automaticky implementované vlastnosti najdete v tématu [Auto-Implemented vlastnosti](/dotnet/csharp/programming-guide/classes-and-structs/auto-implemented-properties).  
  
## <a name="common-tasks"></a>Obecné úlohy  
  
|Úloha|Podpůrný obsah|  
|----------|------------------------|  
|**Začínáme:** předtím, než vytvoříte a nakonfigurujete členy typu, je nutné otevřít okno podrobností třídy.|-   [Otevřete okno Podrobnosti – třída](creating-and-configuring-type-members.md#OpenClassDetails)<br />-   [Poznámky pro použití podrobnosti – třída](creating-and-configuring-type-members.md#ClassDetailsUsageNotes)<br />-   [Zobrazení jen pro čtení informací](creating-and-configuring-type-members.md#ReadOnlyInfo)<br />-   [Klávesové zkratky a zkratky myši v diagramu tříd a okně podrobností třídy](keyboard-and-mouse-shortcuts-in-the-class-diagram-and-class-details-window.md)|  
|**Vytvořit a upravit členy typu:** můžete vytvořit nové členy, upravit členy a přidat parametry do metody pomocí okno podrobností třídy.|-   [Vytváření členů](creating-and-configuring-type-members.md#CreateMembers)<br />-   [Úprava členy typu](creating-and-configuring-type-members.md#ModifyTypeMembers)<br />-   [Přidání parametrů do metod](creating-and-configuring-type-members.md#AddMethodParams)|  
  
##  <a name="OpenClassDetails"></a>Otevřete okno Podrobnosti – třída  
Ve výchozím okně podrobností třídy se zobrazí automaticky při otevření nové diagramu tříd (viz [postupy: Přidání diagramů tříd do projektů](how-to-add-class-diagrams-to-projects.md)). Okno podrobností třídy můžete také otevřít explicitně následujícími způsoby.  
  
#### <a name="to-open-the-class-details-window"></a>Otevření okna podrobností třídy  
  
1.  Klikněte pravým tlačítkem myši na libovolné třídy v diagramu zobrazíte z kontextové nabídky.  
  
2.  V místní nabídce klikněte na tlačítko **okně podrobností třídy**.  
  
 - nebo –  
  
-   Přejděte na příkaz **ostatní okna** v nabídce zobrazení a pak klikněte na tlačítko **podrobností třídy**.  
  
##  <a name="CreateMembers"></a>Vytváření členů  
Člen můžete vytvořit pomocí libovolného z následujících nástrojů:  
  
-   Návrhář tříd  
  
-   Panel nástrojů okno podrobností třídy  
  
-   Okno podrobností třídy  
  
> [!NOTE]
>  Pomocí postupů v tomto oddíle můžete také vytvořit konstruktory a destruktory. Nezapomínejte, že konstruktory a destruktory jsou zvláštní druhy metody a jako takový se objeví v **metody** obrazců diagramu tříd a v prostředí **metody** části třídy Podrobnosti o okno mřížky.  
  
> [!NOTE]
>  Parametr je jediná entita, kterou můžete přidat k delegátu. Upozorňujeme, že postup s názvem „Vytvoření členu pomocí panelu nástrojů okna podrobností třídy“ není pro tuto akci platný.  
  
#### <a name="to-create-a-member-using-class-designer"></a>Vytvoření členu pomocí Návrháře třídy  
  
1.  Klikněte pravým tlačítkem na typ, do které chcete přidat člena, přejděte na **přidat**a pak vyberte typ člena, který chcete přidat.  
  
     Vytvoří se nový podpis člena a přidá se k typu. Ho je zadána výchozí název, který můžete změnit v **návrhář tříd**, **podrobností třídy** okno, nebo **vlastnosti** okno.  
  
2.  Volitelně můžete určit další detaily členu, například jeho typ.  
  
#### <a name="to-create-a-member-using-the-class-details-window-toolbar"></a>Vytvoření členu pomocí panelu nástrojů okna podrobností třídy  
  
1.  Na ploše diagramu vyberte typ, ke kterému chcete přidat člen.  
  
     Typ získá fokus a jeho obsah se zobrazí v okně podrobností třídy.  
  
2.  V panelu nástrojů v okně podrobností třídy, klikněte na ikonu horní a vyberte **nový \<člen >** z rozevíracího seznamu.  
  
     Posune kurzor **název** pole řádek pro typ člena, který chcete přidat. Například pokud jste klikli na **novou vlastnost**, kurzor se přesune na nový řádek v **vlastnosti** části okno podrobností třídy.  
  
3.  Zadejte název členu, který chcete vytvořit, a stiskněte klávesu Enter (nebo jinak přesuňte fokus, například stisknutím klávesy Tab).  
  
     Vytvoří se nový podpis člena a přidá se k typu. Člen nyní existuje v kódu a zobrazí se v **návrhář tříd**, okno podrobností třídy a vlastnosti okna.  
  
4.  Volitelně můžete určit další detaily členu, například jeho typ.  
  
#### <a name="to-create-a-member-using-the-class-details-window"></a>Vytvoření členu pomocí okna podrobností třídy  
  
1.  Na ploše diagramu vyberte typ, ke kterému chcete přidat člen.  
  
     Typ získá fokus a jeho obsah se zobrazí v okně podrobností třídy.  
  
2.  V okně podrobností třídy v oddílu, který obsahuje typ člena, který chcete přidat, klikněte na  **\<přidat člena >**. Například pokud chcete přidat pole, klikněte na možnost  **\<přidat pole >**.  
  
3.  Zadejte název členu, který chcete vytvořit, a stiskněte klávesu Enter.  
  
     Vytvoří se nový podpis člena a přidá se k typu. Člen nyní existuje v kódu a v se zobrazí **návrhář tříd**, okno podrobností třídy a vlastnosti okna.  
  
4.  Volitelně můžete určit další detaily členu, například jeho typ.  
  
     **Poznámka:** klávesové zkratky můžete také použít k vytvoření členy. Další informace najdete v tématu [klávesové zkratky a zkratky myši v diagramu tříd a okně podrobností třídy](keyboard-and-mouse-shortcuts-in-the-class-diagram-and-class-details-window.md).  
  
##  <a name="ModifyTypeMembers"></a>Úprava členy typu  
V Návrháři tříd můžete upravit členy typů, které se zobrazí v diagramu. Můžete upravit členy libovolného typu, které se zobrazí v diagramu třídy a nejsou jen pro čtení. Členy typu změníte úpravou na místě na návrhové ploše, v okně Vlastnosti a v okně podrobností třídy  
  
Všechny členy zobrazené v okně podrobností třídy představují členy typů v diagramu třídy. Existují čtyři typy členů: metody, vlastnosti, pole a události.  
  
Všechny řádky členů jsou zobrazeny pod nadpisy, které je seskupují podle druhu. Například všechny vlastnosti se zobrazí v části **vlastnosti**, který jako uzel v mřížce, možné sbalit nebo rozbalit.  
  
Každý řádek členu zobrazuje následující prvky:  
  
-   **Ikona člena**  
  
     Každý druh členu znázorňuje jeho vlastní ikona. Bod myší na ikonu člen zobrazíte podpis člena. Kliknutím na ikonu členu nebo na prázdné znaky vlevo od ikony členu vyberete řádek.  
  
-   **Název členu**  
  
     **Název** sloupce v řádku člen zobrazí název člena. Tento název se zobrazí také v **název** vlastnost v okně Vlastnosti. Tuto buňku můžete použít ke změně názvu jakéhokoli členu, který má oprávnění pro čtení i zápis.  
  
     Pokud **název** sloupec je příliš úzké, chcete-li zobrazit celý název odkazující myši na název člena zobrazí celý název.  
  
-   **Typ člena**  
  
     **MemberType** buňky používá technologii IntelliSense, které lze vybrat ze seznamu všechny typy, které jsou dostupné v aktuálním projektu nebo odkazované projekty.  
  
-   **Člen modifikátor**  
  
     Změňte buď modifikátor viditelnosti člena `Public` (`public`), `Private` (`private`), `Friend` (`internal`) `Protected` (`protected`), `Protected``Friend` (`protected``internal`), nebo `Default`.  
  
-   **\<Přidání člena >**  
  
     Poslední řádek v okně podrobností třídy obsahuje text  **\<přidat člena >** v **název** buňky. Pokud na tuto buňku klikněte, můžete vytvořit nový člen. Další informace najdete v tématu [vytváření členy](creating-and-configuring-type-members.md#CreateMembers).  
  
-   **Vlastnosti člena v okně vlastností**  
  
     Okno podrobností třídy zobrazuje podmnožinu vlastností členů, které jsou zobrazeny v okně Vlastnosti. Změna vlastnosti na jednom místě aktualizuje hodnotu vlastnosti globálně. Aktualizuje se i zobrazení hodnoty členu v jiném umístění.  
  
-   **Shrnutí**  
  
     **Souhrnné** buňky zpřístupní souhrnné informace o člen. Klikněte na tlačítko se třemi tečkami v **Souhrn** buňky do umožňuje zobrazit nebo upravit informace o **Souhrn**, **návratového typu**, a **poznámky** pro člena .  
  
-   **Skrýt**  
  
     Když **skrýt** je zaškrtnuté políčko, člen není zobrazen v typu.  
  
#### <a name="to-modify-a-type-member"></a>Změna členu typu  
  
1.  Pomocí Návrháře tříd vyberte typ.  
  
2.  Pokud se nezobrazí okno podrobností třídy, klikněte **okně podrobností třídy** tlačítka na panelu nástrojů návrhář tříd.  
  
3.  Upravte hodnoty v polích v mřížce okno podrobností třídy. Po každé úpravě stiskněte klávesu ENTER nebo jinak přesuňte fokus z upravovaného pole, například stisknutím klávesy TAB. Úpravy se v kódu projeví okamžitě.  
  
    > [!NOTE]
    >  Pokud chcete změnit pouze název členu, můžete to provést úpravou na místě.  
  
##  <a name="AddMethodParams"></a>Přidání parametrů do metod  
Přidání parametrů do metody pomocí okna podrobností třídy. Parametry lze konfigurovat jako povinné, či volitelné. Poskytnutí hodnotu **volitelné výchozí** přikazuje parametru návrháře pro generování kódu jako volitelný parametr.  
  
Řádky parametru obsahují následující položky:  
  
-   **Jméno**  
  
     **Název** sloupce v řádku parametr zobrazí název parametru. Tento název se zobrazí také v **název** vlastnost v okně Vlastnosti. Tuto buňku můžete použít ke změně názvu jakéhokoli parametru, který má oprávnění pro čtení i zápis.  
  
     Název parametru odkazující na název parametru zobrazí, pokud **název** sloupec je příliš úzké, chcete-li zobrazit celý název.  
  
-   **Typ**  
  
     **Typ parametru** buňky používá technologii Intellisense, která umožňuje vybrat ze seznamu všechny typy, které jsou dostupné v aktuálním projektu nebo odkazované projekty.  
  
-   **Modifikátor**  
  
     **Modifikátor** buňky v řádku parametr přijme a zobrazí new – modifikátor parametru. Pokud chcete zadat nové – modifikátor parametrů, použijte rozevírací seznam a vyberte z **žádné**, **ref**, **out**, nebo **parametry** v C# a **ByVal**, **ByRef**, nebo **ParamArray** v jazyce VB.  
  
-   **Shrnutí**  
  
     **Souhrn** buňky v řádku parametr umožňuje zadávání komentářů kódu, které se zobrazují v IntelliSense při zadávání parametru do editoru kódu.  
  
-   **\<Přidejte parametr >**  
  
     Poslední řádek parametr člena obsahuje text  **<add parameter>**  v **název** buňky. Kliknutím na tuto buňku vytvoříte nový parametr. Další informace najdete v tématu [přidání parametru k metodě](creating-and-configuring-type-members.md#HowToAddParameterToMethod).  
  
**Parametr vlastností v okně vlastností**  
  
V okně Vlastnosti se zobrazí stejné vlastnosti parametru zobrazí v okně podrobností třídy: **název**, **typ**, **modifikátor**, **Souhrn**, a taky **volitelné výchozí** vlastnost. Změnou vlastnosti na jednom místě aktualizujete hodnotu vlastnosti globálně, včetně zobrazení hodnoty v jiném umístění.  
  
> [!NOTE]
>  Pro přidání parametru s delegátem, najdete v části [vytváření členy](creating-and-configuring-type-members.md#CreateMembers).  
  
> [!NOTE]
>  Ačkoli je destruktor metoda, nemůže mít parametry.  
  
###  <a name="HowToAddParameterToMethod"></a>Přidání parametru k metodě  
  
1.  Na ploše diagramu klikněte na typ obsahující metodu, ke které chcete přidat parametr.  
  
     Typ získá fokus a jeho obsah se zobrazí v okně podrobností třídy.  
  
2.  V okně podrobností třídy rozbalte řádek metody, do které chcete přidat parametr.  
  
     Se zobrazí řádek zobrazují odsazené parametr, obsahující jenom pár kulaté závorky a slova  **\<přidat parametr >.**  
  
3.  Klikněte na tlačítko  **\<přidat parametr >**, zadejte název nového parametru a stiskněte klávesu **Enter**.  
  
     Metoda a kód metody je přidán nový parametr. Zobrazí se v okně podrobností třídy a v okně Vlastnosti.  
  
4.  Volitelně můžete určit další detaily parametru, například jeho typ.  
  
### <a name="to-add-an-optional-parameter-to-a-method"></a>Přidání volitelného parametru do metody  
  
1.  Na ploše diagramu klikněte na typ obsahující metodu, ke které chcete přidat volitelný parametr.  
  
     Typ získá fokus a jeho obsah se zobrazí v okně podrobností třídy.  
  
2.  V okně podrobností třídy rozbalte řádek metody, do které chcete přidat volitelný parametr.  
  
     Se zobrazí řádek zobrazují odsazené parametr, obsahující jenom pár kulaté závorky a slova  **\<přidat parametr >.**  
  
3.  Klikněte na tlačítko  **\<přidat parametr >**, zadejte název nového parametru a stiskněte klávesu **Enter**.  
  
     Metoda a kód metody je přidán nový parametr. Zobrazí se v okně podrobností třídy a v okně Vlastnosti.  
  
4.  V okně vlastností zadejte hodnotu **volitelné výchozí** vlastnost. Nastavením vlastnosti Volitelné výchozí nastavíte daný parametr na volitelný.  
  
    > [!NOTE]
    >  Volitelné parametry musí být posledními parametry v seznamu parametrů.  
  
##  <a name="ClassDetailsUsageNotes"></a>Poznámky pro použití podrobnosti – třída  
Při používání okna podrobností třídy mějte prosím na paměti následující tipy.  
  
**Upravitelné a upravovat buňky**  
  
Všechny buňky v okně podrobností třídy jsou editovatelné, s několika výjimkami:  
  
-   Celý typ je jen pro čtení, když, například se nachází v odkazované sestavení. Při výběru tvaru v Návrháři tříd, okno podrobností třídy zobrazí jeho detaily ve stavu jen pro čtení.  
  
-   V případě indexerů je název jen pro čtení a zbytek (typ, modifikátor, shrnutí) je editovatelný.  
  
-   V okně podrobností třídy mají všechny obecné typy parametry jen pro čtení. Chcete-li změnit obecný parametr, upravte jeho zdrojový kód.  
  
-   Název parametru typu, který je definován na obecném typu, je jen pro čtení.  
  
-   Když je kód typu porušen (nelze jej analyzovat), okno podrobností třídy zobrazí obsah typu jen pro čtení.  
  
**Okno podrobností třídy a zdrojový kód**  
  
-   Kliknutím pravým tlačítkem myši na tvar v okně podrobností třídy (nebo Návrhář tříd) a následným kliknutím na příkaz Zobrazit kód můžete zobrazit zdrojový kód. Otevře se soubor zdrojového kódu a zobrazení se posune na vybraný prvek.  
  
-   Změna zdrojového kódu se okamžitě projeví v zobrazení informací podpisu v okně Návrhář třídy a Podrobnosti třídy. Pokud je okno podrobností třídy v daném okamžiku zavřeno, nové informace se zobrazí při příštím otevření okna.  
  
-   Když je kód typu porušen (nelze jej analyzovat), okno podrobností třídy zobrazí obsah typu jen pro čtení.  
  
**Funkce schránky v okně podrobností třídy**  
  
 Z okna podrobností třídy můžete kopírovat nebo vyjímat pole či řádky a vkládat je do jiného typu. Řádek můžete vyjmout, pouze pokud je jen pro čtení. Po vložení řádku okno podrobností třídy přiřadí nový název (odvozený od názvu zkopírovaného řádku), aby nedošlo ke konfliktu.  
  
##  <a name="ReadOnlyInfo"></a>Zobrazení jen pro čtení informací  
Návrhář tříd a okno podrobností třídy mohou zobrazit typy (a členy typů) pro:  
  
-   projekt, který obsahuje diagram třídy  
  
-   projekt odkazovaný z projektu, který obsahuje diagram třídy  
  
-   sestavení odkazované z projektu, který obsahuje diagram třídy  
  
V posledních dvou případech je odkazovaná entita (typ nebo člen) v diagramu tříd, který ji reprezentuje, jen pro čtení.  
  
Celý projekt nebo jeho části, například jednotlivé soubory, mohou být jen pro čtení. Většina běžných případů, ve kterých projekt nebo jeden z jeho souborů, je jen pro čtení, jsou takové, kdy se projekt nachází v rámci správy zdrojového kódu (a není rezervován), existuje v externím sestavení nebo když operační systém považuje soubory za soubory jen pro čtení.  
  
**Řízení zdrojového kódu**  
  
Protože diagram tříd je uložen jako soubor v projektu, je třeba projekt rezervovat, aby se uložily všechny změny, které provedete v okně Návrhář tříd nebo okně podrobností třídy.  
  
**Projekty jen pro čtení**  
  
Projekt může být jen pro čtení z jiného důvodu než pro správu zdrojového kódu. Zavřením projektu zobrazí dialogové okno s dotazem, zda chcete přepsat soubor projektu, zahodit změny (Neukládat) nebo zavřít operaci zrušte. Pokud zvolíte přepsání, soubory projektu jsou přepsány a nastaveny pro čtení i zápis. Je přidán nový soubor diagramu tříd.  
  
**Typy jen pro čtení**  
  
Pokud se pokusíte uložit projekt obsahující typ, jejichž zdrojového kódu soubor je jen pro čtení, **uložit jen pro čtení souboru** se zobrazí dialogové okno, které nabízí možnosti k uložení souboru pod novým názvem nebo nové umístění nebo k přepsání souboru jen pro čtení . Pokud soubor přepíšete, nová kopie již není jen pro čtení.  
  
Pokud soubor s kódem obsahuje chybu syntaxe, tvary zobrazující kód v daném souboru budou dočasně jen pro čtení, dokud chyba syntaxe nebude opravena. Tvary v tomto stavu zobrazí červený text a červenou ikonu, která zobrazí popisek s textem „Soubor zdrojového kódu obsahuje chybu analýzy“.  
  
Odkazovaný typ (například typ rozhraní .NET Framework), který existuje v rámci jiného uzlu projektu nebo uzlu odkazovaného sestavení, je na návrhové ploše Návrháře tříd uveden jako jen pro čtení. Místní typ, který existuje v projektu, jež chcete otevřít, je pro čtení i zápis a jeho tvar na návrhové ploše Návrháře tříd je takto označen.  
  
Indexery jsou pro čtení i zápis v kódu a v okně podrobností třídy, ale název indexeru je jen pro čtení.  
  
Částečné metody nelze upravovat pomocí Návrháře tříd nebo v okně podrobností třídy; k úpravám je nutné použít Editor kódu.  
  
Nativní kód C++ nelze upravovat pomocí Návrháře tříd nebo v okně podrobností třídy; k úpravám je nutné použít Editor kódu.  
  
## <a name="see-also"></a>Viz také
[Zobrazování typů a vztahů](viewing-types-and-relationships.md)  
[Refaktoring tříd a typů](refactoring-classes-and-types.md)