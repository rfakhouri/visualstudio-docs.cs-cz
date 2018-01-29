---
title: IntelliSense C# | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- C#, IntelliSense
- IntelliSense [C#]
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: 9da494eaf71a02f7b46ce68b1cf9f781fe32e716
ms.sourcegitcommit: b18844078a30d59014b48a9c247848dea188b0ee
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/29/2018
---
# <a name="c-intellisense"></a>C# IntelliSense

C# IntelliSense je k dispozici, pokud kódování v editoru a při ladění v [přímý režim](../ide/reference/immediate-window.md) příkazové okno.

## <a name="completion-lists"></a>Seznamy dokončení

Seznamy dokončení IntelliSense v jazyce C# obsahovat tokeny od seznamu členů, dokončení Word a další. Poskytuje rychlý přístup k:

- Členy typu nebo obor názvů

- Proměnné, příkazy a funkce na názvy

- Fragmenty kódu

- Klíčová slova jazyka

- Metody rozšíření

Seznamu dokončení v jazyce C# je také důležité tokeny pomocí filtrů a předem vyberte token na základě kontextu. Další informace najdete v tématu [filtrované seznamy dokončení](#filtered-completion-lists).

## <a name="code-snippets-in-completion-lists"></a>Fragmenty kódu v seznamy dokončení

Seznam dokončení v jazyce C#, zahrnuje fragmenty kódu můžete snadno vložit předdefinované těla kódu do vaší aplikace. Fragmenty kódu jsou uvedeny v seznamu dokončení jako uvedeném fragmentu [zástupce text](../ide/code-snippets-schema-reference.md#shortcut). Další informace o fragmentech kódu, které jsou k dispozici v jazyce C# ve výchozím nastavení najdete v tématu [fragmenty kódu v C#](../ide/visual-csharp-code-snippets.md).

## <a name="language-keywords-in-completion-lists"></a>Klíčová slova jazyka v seznamy dokončení

Seznam dokončení v jazyce C#, také zahrnuje klíčová slova jazyka. Další informace o klíčová slova jazyka C#, najdete v části [klíčová slova jazyka C#](/dotnet/csharp/language-reference/keywords/index).

## <a name="extension-methods-in-completion-lists"></a>Rozšiřující metody v seznamy dokončení

Seznam dokončení v jazyce C#, obsahuje rozšiřující metody, které jsou v oboru.

> [!NOTE]
> Seznam dokončení nejsou zobrazeny všechny rozšiřující metody pro <xref:System.String> objekty.

Metody rozšíření použití různých ikony než instance metody. Výpis seznamu ikon, najdete v části [zobrazení tříd a ikony v prohlížeči objekt](../ide/class-view-and-object-browser-icons.md). Pokud instanci metody a metoda rozšíření se stejným názvem jsou v oboru, zobrazí se seznam dokončení ikonu – metoda rozšíření.

## <a name="filtered-completion-lists"></a>Filtrované seznamy dokončení

IntelliSense odebere nepotřebné členy ze seznamu dokončení pomocí filtrů. C# filtry seznamy dokončení, které se zobrazují pro tyto položky:

- **Základní třídy a rozhraní**: IntelliSense automaticky odebere položky z rozhraní a základní třída dokončení seznamů, v deklaraci třídy základní a rozhraní seznamy a seznamy omezení. Například výčty se nezobrazí v seznamu dokončení pro základní třídy, protože výčty nelze použít pro základní třídy. Seznam dokončení základní třídy obsahuje pouze rozhraní a obory názvů. Pokud jste v seznamu vyberte položku a potom zadejte do čárkami, IntelliSense odebere ze seznamu dokončení základní třídy, protože C# nepodporuje vícenásobná dědičnost. Stejné chování dochází v klauzulích omezení taky.

- **Atributy**: Pokud použijete typ atributu, je seznamu dokončení filtrované tak, že seznam obsahuje pouze ty typy, které sestup z obory názvů, které obsahují tyto typy, jako <xref:System.Attribute>.

- **Catch – klauzule**

- **Inicializátory objektu**: pouze členové, které jde inicializovat se objeví v seznamu dokončení.

- **New – klíčové slovo**: Pokud zadáte `new` a pak stiskněte MEZERNÍK, zobrazí se seznam dokončení. Automaticky se vybere položka v seznamu, na základě kontextu ve vašem kódu. Položky se automaticky vybrán v seznamu dokončení pro deklarace a příkazech return v metodách.

- **enum – klíčové slovo**: když stiskněte MEZERNÍK po symbolem rovná pro přiřazení výčtu, zobrazí se seznam dokončení. Automaticky se vybere položka v seznamu, na základě kontextu ve vašem kódu. Například jsou automaticky vybrány položky v seznamu dokončení po zadání – klíčové slovo návratový, a pokud provedete deklaraci.

- **jako a operátory**: seznam filtrované dokončení se zobrazí automaticky, když stiskněte MEZERNÍK po jste zadali `as` nebo `is` – klíčové slovo.

- **Události**: Pokud zadáte klíčové slovo `event`, seznamu dokončení obsahuje pouze typů delegátů.

- **Parametr nápovědy** automaticky seřadí na první přetížení metody, která odpovídá parametry, jako je zadat. Pokud více přetížení metody jsou k dispozici, můžete pomocí nahoru a dolů šipky přejděte na další možné přetížení v seznamu.

## <a name="most-recently-used-members"></a>Naposledy použité členy

IntelliSense pamatuje členů, které jste vybrali v místní nabídce nedávno [vypsat členy](../ide/using-intellisense.md) pole pro dokončení název automatické objektu. Při příštím použití seznam členů, naposledy použité členy se zobrazí v horní části. Historii naposledy použité členy není zaškrtnuté mezi každou relaci v prostředí IDE.

## <a name="override"></a>override

Pokud zadáte [přepsat](/dotnet/csharp/language-reference/keywords/override) a pak stiskněte MEZERNÍK, IntelliSense zobrazí všechny platnou třídu base členy, kteří v rozbalovací seznam se dá přepsat. Zadáním návratový typ metody za `override` vyzve IntelliSense, aby se zobrazily pouze metody, které vracejí stejného typu. Když IntelliSense nelze najít žádné shody, se zobrazí všechny členy základní třídy.

## <a name="automatic-code-generation"></a>Automatické vytváření kódu

### <a name="add-using"></a>Přidat direktivu using

**Přidat pomocí** IntelliSense operace automaticky přidá požadované `using` direktivy do souboru kódu. Tato funkce umožňuje udržovat vaše zaměřit se na kód zápis nechcete vyžadující, abyste posun vaší zaměření na jinou část kódu.

Chcete-li iniciovat přidat pomocí operace, umístěte kurzor na odkaz na typ, který nelze vyřešit. Například když Vytvořte konzolovou aplikaci a poté přidejte `XmlTextReader` k tělu `Main` metody červenou vlnovkou se zobrazuje na tohoto řádku kódu protože odkaz na typ nelze přeložit. Potom můžete vyvolat přidat pomocí prostřednictvím rychlé akce. Rychlé akce je viditelná, pouze pokud kurzor je nastavený na nevázaný typ.

![Přidat pomocí, rychlá rozšířené obrázek akce](../ide/media/addusing-quickaction.png "AddUsing QuickAction")

Klikněte na ikonu žárovky a potom zvolte **pomocí System.Xml;** a automaticky tak přidejte použití – direktiva.

### <a name="remove-and-sort-usings"></a>Odebrat a řazení direktiv Using

**Odebrat a řazení direktiv Using** možnost seřadí a odebere `using` a `extern` deklarace bez změny chování zdrojového kódu. Zdrojové soubory v čase, může přestat opakovaném a obtížně se číst z důvodu nepotřebné a neuspořádaný `using` direktivy. **Odebrat a řazení direktiv Using** možnost odebráním nevyužité zkomprimuje zdrojového kódu `using` direktivy a lepší čitelnost seřazením. Na **upravit** nabídce zvolte **IntelliSense**a potom zvolte **uspořádání direktiv Using**.

### <a name="implement-interface"></a>Implementovat rozhraní

IntelliSense nabízí možnost, která vám pomůže implementovat [rozhraní](/dotnet/csharp/language-reference/keywords/interface) při práci v editoru kódu. Za normálních okolností správně implementovat rozhraní, musíte vytvořit deklaraci metody pro každého člena rozhraní v třídě. Používání atributu IntelliSense, zadejte název rozhraní v deklaraci třídy po, zobrazí se žárovky rychlé akce. Žárovky vám dává možnost automaticky, toto rozhraní implementovat pomocí explicitní nebo implicitní názvy. V části explicitní názvy deklarace metoda provádění název rozhraní; v části implicitní pojmenování deklarace metoda neoznačují rozhraní, do které patří. Metodu explicitně rozhraní jsou přístupné pouze prostřednictvím instance rozhraní a ne prostřednictvím instance třídy. Další informace najdete v tématu [explicitní implementace rozhraní](/dotnet/csharp/programming-guide/interfaces/explicit-interface-implementation).

Implementovat rozhraní vygeneruje minimální počet zástupných procedur metoda, které je potřeba splnit rozhraní. Pokud základní třída implementuje části rozhraní, nejsou tyto zástupných procedur obnovovaly.

### <a name="implement-abstract-base-class"></a>Implementace třídy base abstraktu

IntelliSense nabízí možnost, která vám pomůže implementovat členy abstraktní základní třídu automaticky při práci v editoru kódu. Za normálních okolností implementace členů abstraktní základní třída vyžaduje vytváření nové definice metoda abstraktní základní třída pro každou metodu v odvozené třídě. Používání atributu IntelliSense, po zadání názvu abstraktní základní třídy v deklaraci třídy, se zobrazí žárovky rychlé akce. Žárovky vám dává možnost automaticky implementovat metody třídy base.

Metoda zástupných procedur, vytvořených pomocí funkce abstraktní základní třída implementace jsou modelovány pomocí fragmentu kódu, který je definován v souboru MethodStub.snippet. Fragmenty kódu jsou změn. Další informace najdete v tématu [návod: Vytvoření fragmentu kódu](../ide/walkthrough-creating-a-code-snippet.md).

### <a name="generate-from-usage"></a>Generování před využitím

**Generování před využitím** funkce umožňuje používání tříd a členů, než je definovat. Můžete vygenerovat zástupnou proceduru pro všechny třídy, konstruktor, metoda, vlastnost, pole nebo výčet, který chcete použít, ale ještě nebyly definovány. Nové typy a členy můžete vygenerovat aniž byste museli opustit vaše aktuální umístění v kódu. Tím se minimalizují přerušení pracovního postupu.

Red vlnovkou se zobrazí pod každý nedefinovaný identifikátor. Při umístění ukazatele myši na identifikátor, zobrazí se chybová zpráva v popisu tlačítka. Pokud chcete zobrazit příslušné možnosti, můžete použít jednu z následujících postupů:

- Klikněte na tlačítko nedefinovaný identifikátor. Žárovky rychlé akce se zobrazí pod identifikátor. Klikněte na tlačítko žárovky.

- Klikněte na nedefinovaný identifikátor a stiskněte klávesu **Ctrl** + **.** (Ctrl + tečka).

- Klikněte pravým tlačítkem na nedefinovaný identifikátor a pak klikněte na **rychlé akce a refaktoring**.

Možnosti, které se zobrazují patří:

- **Generovat vlastnost**

- **Generované pole**

- **Generování metody**

- **Generovat – třída**

- **Vytvořit nový typ...**  (pro třída, struktura, rozhraní nebo výčtu)

## <a name="generate-event-handlers"></a>Generovat obslužné rutiny událostí

V editoru kódu technologie IntelliSense můžete spojit metody (obslužné rutiny událostí) na pole událostí.

Pokud zadáte `+=` operátor po na pole událostí v souboru .cs IntelliSense zobrazí výzvu s možností stiskněte **kartě** klíč. Vloží novou instanci třídy delegáta, který odkazuje na metodu zpracování události.

![Button Auto Hook Up](../ide/media/vxautohookup.gif "vxAutoHookUp")

Pokud vyberete **kartě**, IntelliSense automaticky dokončení příkazu a odkazu na obslužnou rutinu události se zobrazí jako vybraný text v editoru kódu. K dokončení automatického událostí spojení, IntelliSense vyzváni ke stisknutí tlačítka **kartě** klíč znovu a vytvořit prázdný se zakázaným inzerováním obslužné rutiny událostí.

![Generate Event Handler](../ide/media/vxgenerateeventhandler.gif "vxGenerateEventHandler")

> [!NOTE]
> Pokud nové delegáta, který je vytvořen pomocí IntelliSense odkazuje stávající obslužné rutiny události, IntelliSense komunikuje tyto informace v popisu tlačítka. Poté můžete upravit tento odkaz; text je již vybrána v editoru kódu. Jinak automatické událostí spojení je dokončena v tomto okamžiku.

Pokud vyberete **kartě**, IntelliSense zástupných procedur se metoda se správným podpisem a vloží kurzor v těle obslužné rutiny události.

> [!NOTE]
> Použití **přejděte zpětné** příkaz na **zobrazení** nabídky (**Ctrl** + **-**) se vrátíte k události příkaz spojení.

## <a name="see-also"></a>Viz také

[Používání atributu IntelliSense](../ide/using-intellisense.md)  
[Integrované vývojové prostředí sady Visual Studio](../ide/visual-studio-ide.md)