---
title: "Přehled protokolu Server jazyk | Microsoft Docs"
ms.custom: 
ms.date: 11/14/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6a7d93c2-31ea-4bae-8b29-6988a567ddf2
caps.latest.revision: "1"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9aeef820575a4fb055318fe11d401e85c9958bad
ms.sourcegitcommit: 26419ab0cccdc30d279c32d6a841758cfa903806
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/11/2017
---
# <a name="language-server-protocol"></a>Jazyk serveru protokolu

## <a name="what-is-the-language-server-protocol"></a>Co je protokol jazyk serveru?

Podpůrné bohaté funkce úpravy, jako zdrojový kód auto dokončování nebo **přechod na definici** pro programovací jazyk v editoru nebo IDE je tradičně velmi náročná a časově náročné. Obvykle vyžaduje zápis modelu domény (skener, analyzátor, nástroj pro kontrolu typu, tvůrce a další) v programovacím jazyce editoru nebo IDE. Například Eclipse CDT modul plug-in, který poskytuje podporu pro C/C++ v integrovaném vývojovém prostředí Eclipse napsanou v jazyce Java vzhledem k tomu, že je integrovaného vývojového prostředí Eclipse, samotné napsanou v jazyce Java. Následující tento přístup bude znamenat implementace modelu domény C/C++ v TypeScript pro Visual Studio Code a model samostatné doméně v jazyce C# pro sadu Visual Studio.

Vytváření modelů pro specifický jazyk domény jsou také mnohem jednodušší, pokud nástroj pro vývoj můžete opakovaně použít existující knihovny konkrétní jazyk. Tyto knihovny jsou obvykle implementované v programovacím jazyce samotné (například dobrý C/C++ domény modely jsou implementované v jazyce C/C++). Integrace knihovny jazyka C/C++ do editoru napsané v TypeScript je technicky možné ale těžko provést.

### <a name="language-servers"></a>Jazyk servery

Jiná možnost je ve svém vlastním procesu spuštění knihovny a použít ke komunikaci s jeho komunikaci mezi procesy. Zprávy odeslané a zpět formuláři protokol. Protokol server language (LSP) je produkt standardizace zprávy vyměňují mezi nástroj pro vývoj a proces jazyk serveru. Použití jazyka servery nebo demons není nové nebo nové představu. Editory jako Vim a mít provádění Emacs, to nějakou dobu poskytovat podporu sémantického automatické dokončování. Cílem LSP bylo zjednodušit tyto řazení integrace a poskytují užitečné rozhraní pro vystavení jazykové funkce pro celou řadu nástrojů.

Společný protokol umožní integraci programování jazykové funkce do nástroje a vývoj s minimálním fuss opětovným použitím stávající implementaci jazyka domény modelu. Jazyk serveru back-end může být napsané v PHP, Python nebo Java a LSP umožňuje, aby ji snadno integrovat do různých nástrojů. Protokol funguje na běžné úrovni abstrakce, aby nástroj nabízejí bohatou jazyk služby bez nutnosti k plnému pochopení specifické pro základní model domény drobné odlišnosti.

## <a name="how-work-on-the-lsp-started"></a>Jak fungují na LSP spuštění

Došlo k vývoji LSP v čase a dnes je ve verzi 3.0. Jeho spuštění, když koncept jazyk serveru byl zachyceny pomocí OmniSharp zajistit bohaté funkce úprav pro jazyk C#. Na začátku OmniSharp použít protokol HTTP s datovou část JSON a je integrována do několika editory včetně [Visual Studio Code](https://code.visualstudio.com).

Přibližně ve stejnou dobu spuštění Microsoft pro práci na serveru pro jazyk TypeScript, za účelem podpory TypeScript editorů jako Emacs a Sublime Text. V této implementaci editoru komunikuje přes stdin/stdout s procesu TypeScript serveru a používá vycházející protokol ladicí program v8: datové části JSON pro požadavky a odpovědi. TypeScript server integroval do TypeScript Sublime modul plug-in a VS Code pro úpravy bohaté TypeScript.

Po s v integrované dva servery s jiným jazykem, spustit týmem VS Code a prozkoumejte společný protokol serveru jazyk pro editory a integrovaného vývojového prostředí. Společný protokol umožňuje poskytovatele jazyka vytvoření jeden jazyk serveru, která mohou být spotřebovávána různých integrovaného vývojového prostředí. Příjemce jazyk serveru má jenom jednou implementace protokolu na straně klienta. Výsledkem win-win situaci pro poskytovatele jazyka a jazyk příjemce.

Práce s jazyk protokolu používané serverem TypeScript, byl další obecné vlastnosti a jazykově neutrální. Protokol byl s jazykem VS Code rozhraní API pro inspiraci další funkce jazyka. Samotný protokol je zálohovaný s JSON-RPC pro vzdálené volání z důvodu jeho jednoduchost a podpora knihovny pro řadě programovacích jazyků.

Dogfooded team VS Code protokol implementací několik serverů linter jazyk. Jazyk serveru linter reaguje na požadavky na hadříkem (kontrola) souboru a vrátí sadu zjištěné upozornění a chyby. Cílem bylo hadříkem soubor jako uživatelské úpravy v dokumentu, což znamená, že bude mnoho požadavků linting během relace editoru. Byly provedeny smysl zachovat server nahoru a spuštěný, aby nový proces linting nebylo nutné spustit pro každý uživatel upravit. Několik serverů linter byly implementovány, včetně VS Code ESLint a TSLint rozšíření. Tyto dva servery linter jsou implementované v TypeScript/JavaScript i spustit na Node.js. Sdílení knihovny, který implementuje klientskou a serverovou součást protokolu.

## <a name="how-the-lsp-works"></a>Jak funguje LSP

Jazyk serveru běží ve svém vlastním procesu a nástroje, například Visual Studio nebo VS Code komunikaci se serverem pomocí protokolu jazyk přes JSON-RPC. Další výhodou jazyk serveru operační ve vyhrazeném procesu je, že se tak předejde problémy s výkonem související s modelem jeden proces. Kanál skutečné přenosu může být buď stdio sockets, pojmenované kanály nebo uzel ipc Pokud klient i server jsou zapsány v Node.js.

Níže je příklad, jak nástroj a jazyk serveru komunikují během rutinu, která úpravy relace:

![Vývojový diagram LSP](media/lsp-flow-diagram.png)

* **Uživatel otevře soubor (označované jako dokument) v nástroji**: nástroj upozorní jazyk serveru je otevřený dokument (' textDocument/didOpen'). Od této chvíle pravdivosti o obsahu dokumentu již není v systému souborů, ale ponechá nástroj v paměti.

* **Uživatel provede úpravy**: nástroj upozorní serveru o změně dokumentu (' textDocument/didChange") a sémantické informace programu je aktualizován serverem jazyk. K tomu dojde, jazyk serveru analýzy tyto informace a upozorní nástroj zjištěné chyby a upozornění (' textDocument/publishDiagnostics').

* **Uživatel provede "Přejít k definici" na symbol v editoru**: Tento nástroj se odešle požadavek 'textDocument a definic, s dva parametry: (1) je dokument URI a (2) pozice text, ze kterého byla spuštěna přejít k definici požadavek na server. Server odpoví dokumentu URI a pozice definice symbolu uvnitř dokumentu.

* **Uživatel nezavře dokumentu (soubor)**: ' textDocument/didClose' oznámení se odesílá z nástroje informování serveru jazyk, který dokument je teď už v paměti a aktuální obsah je nyní aktuální v systému souborů.

Tento příklad ukazuje, jak protokol komunikuje se serverem jazyka na úrovni funkcí editoru, jako je "Přejít k definici", "Najít všechny odkazy". Datové typy, které používá protokol jsou editor nebo IDE datové typy jako aktuálně otevřených textového dokumentu a pozice kurzoru. Datové typy nejsou na úrovni programovací model jazyka domény, které by obvykle nabízejí abstraktní syntaxe stromy a kompilátoru symboly (například přeložit typy, obory názvů,...). To výrazně zjednodušuje protokol.

Nyní Podíváme se na žádost, textDocument a definic, podrobněji. V následující tabulce jsou datových částí, které přejděte mezi nástroj klienta a serverem jazyka pro daný požadavek "Přejít k definici" v dokumentu C++.

Toto je žádost:

```json
{
    "jsonrpc": "2.0",
    "id" : 1,
    "method": "textDocument/definition",
    "params": {
        "textDocument": {
            "uri": "file:///p%3A/mseng/VSCode/Playgrounds/cpp/use.cpp"
        },
        "position": {
            "line": 3,
            "character": 12
        }
    }
}
```

Jedná se o odpověď:

```json
{
    "jsonrpc": "2.0",
    "id": "1",
    "result": {
        "uri": "file:///p%3A/mseng/VSCode/Playgrounds/cpp/provide.cpp",
        "range": {
            "start": {
                "line": 0,
                "character": 4
            },
            "end": {
                "line": 0,
                "character": 11
            }
        }
    }
}
```

V retrospect popisující typy dat na úrovni editoru a nikoli na úrovni modelu programovací jazyk je jedním z důvodů pro úspěch protokolu jazyk serveru. Je mnohem jednodušší standardizovat textový dokument URI nebo pozice kurzoru ve srovnání s standardizace abstraktního syntaktického stromu a kompilátoru symboly v různých programovacích jazyků.

Když uživatel pracuje s různými jazyky, VS Code obvykle spustí jazyk serveru pro každý programovací jazyk. Následující příklad ukazuje relace, kde uživatel pracuje v jazyce Java a SASS soubory.

![Java a sass](media/lsp-java-and-sass.png)

### <a name="capabilities"></a>Možnosti

Ne každý jazyk serveru může podporovat všechny funkce, které jsou definované protokol. Proto klient a server ohlášen jejich sada funkcí podporovaných prostřednictvím 'možnosti'. Jako příklad ohlášen serveru ji může zpracovat žádost 'textDocument a definic, že se nemusí 'pracovního prostoru nebo symbol' požadavek zpracovat. Podobně můžete klienty oznamujeme jsou schopný poskytnout, Chystáte se uložit' oznámení před uložením dokumentu, tak, aby server můžete vypočítat textové úpravy automaticky formátovat upravená dokumentu.

## <a name="integrating-a-language-server"></a>Integrace serveru jazyk

Skutečné integrace jazyk serveru do konkrétní nástroj není definována protokolem jazyk serveru a je zleva implementors nástroj. Některé nástroje obecně integrovat jazyk servery tak, že rozšíření, které lze spustit a obraťte se na jakýkoli druh jazyk serveru. Jiné, jako VS Code, vytvořte vlastní rozšíření za jazyk serveru, aby rozšíření je stále schopen poskytnout některé funkce vlastní jazyk.

Pro zjednodušení implementace jazyk serverů a klientů, jsou knihovny nebo sady SDK pro klientské a serverové části. Tyto knihovny jsou k dispozici pro různé jazyky. Například, že je [jazyk klient npm modul](https://www.npmjs.com/package/vscode-languageclient) k usnadnění integrace jazyk serveru do rozšíření VS Code a druhý [modul npm jazyk serveru](https://www.npmjs.com/package/vscode-languageserver) zapisovat jazyk serveru pomocí Node.js. Toto je aktuální [seznamu](https://github.com/Microsoft/language-server-protocol/wiki/Protocol-Implementations) podporu knihoven.

## <a name="using-the-language-server-protocol-in-visual-studio"></a>Pomocí protokolu serveru jazyk v sadě Visual Studio

* [Přidání rozšíření jazyk serveru protokol](adding-an-lsp-extension.md) -Další informace o integraci jazyk serveru do sady Visual Studio.
