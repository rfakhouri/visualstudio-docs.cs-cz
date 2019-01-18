---
title: Ladění aplikace v jazyce JavaScript nebo TypeScript
description: Visual Studio poskytuje podporu pro ladění aplikací jazyka JavaScript a TypeScript v sadě Visual Studio
ms.date: 12/03/2018
ms.topic: conceptual
ms.devlang: javascript
author: mikejo5000
ms.author: mikejo
manager: douge
dev_langs:
- JavaScript
ms.workload:
- nodejs
ms.openlocfilehash: 29b58d588a07be8ba25ab844da171222c57df545
ms.sourcegitcommit: 8bfabab73b39b3b3e68a3e8dc225515e8b310fed
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/18/2019
ms.locfileid: "54398231"
---
# <a name="debug-a-javascript-or-typescript-app-in-visual-studio"></a>Ladění aplikací v jazyce JavaScript nebo TypeScript v sadě Visual Studio

Můžete ladit JavaScript a TypeScript kódu pomocí sady Visual Studio. Můžete nastavit a dosažení zarážky, připojení ladicího programu, kontrolovat proměnné, zobrazení zásobníku volání a používat další funkce ladění.

> [!TIP]
> Pokud jste ještě nenainstalovali aplikaci Visual Studio, přejděte [soubory ke stažení Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) stránku a nainstalovat zdarma. V závislosti na typu vývoj aplikací, které vám to jde, budete muset nainstalovat **úlohy pro vývoj Node.js** pomocí sady Visual Studio.

## <a name="debug-server-side-script"></a>Ladění skriptů na straně serveru

1. S svůj projekt otevřít v sadě Visual Studio, otevřete soubor jazyka JavaScript na straně serveru (například *server.js*), klikněte na ovládací prvek na levém hřbetu nastavit zarážku:

    ![Nastavení zarážky](../javascript/media/tutorial-nodejs-react-set-breakpoint.png)

    Zarážky jsou základní a nejjednodušší funkcí spolehlivého ladění. Zarážka určuje, kde má Visual Studio spuštěný kód pozastavit, abyste mohli zkontrolovat hodnoty proměnných či chování paměti, nebo abyste zjistili, jestli se nějaká větev kódu spouští.

1. Ke spuštění vaší aplikace, stiskněte klávesu **F5** (**ladění** > **spustit ladění**).

    Ladicí program se pozastaví na zarážce, kterou jste nastavili (aktuální příkaz je označený žlutě). Teď můžete stav aplikace zkontrolovat tak, že přesunete ukazatel myši nad proměnné v aktuálním rozsahu a použijete okna ladicího programu, například okna **Místní hodnoty** a **Kukátko**.

1. Pokud chcete pokračovat v aplikaci, stiskněte **F5**.

1. Pokud chcete použít nástroje pro vývojáře v chromu nebo F12 Tools, stiskněte **F12**. Pomocí těchto nástrojů můžete prozkoumat model DOM a provádět interakce s aplikací pomocí konzoly jazyka JavaScript.

## <a name="debug-client-side-script"></a>Ladění skriptů na straně klienta

Visual Studio poskytuje podporu ladění pro Chrome a Internet Explorer pouze. V některých případech ladicí program automaticky narazí na zarážky v kódu jazyka JavaScript a TypeScript a vložené skripty na soubory ve formátu HTML.

Pokud váš zdroj minifikovaný nebo vytvořené transpiler jako TypeScript nebo Babel, použití [zdrojového mapování](#generate_sourcemaps) se vyžaduje k zajištění nejlepšího prostředí ladění. Bez zdrojových mapování může pořád připojit ladicí modul k spuštění klientský skript. Ale může pouze budete moci nastavit a dosažení zarážky v souboru minifikovaný nebo transpiled, ne na původní zdrojový soubor. V aplikaci pro Vue.js, například minifikovaný skriptu bude předána jako řetězec `eval` příkaz, a neexistuje žádný způsob, jak projít tento kód efektivně pomocí ladicího programu sady Visual Studio, pokud nechcete použít zdrojových mapování. V některých komplexní scénáře ladění může také použít nástroje pro vývojáře v chromu nebo F12 Tools pro Microsoft Edge.

Připojit ladicí program sady Visual Studio a dosažení zarážky v kódu na straně klienta, ladicí program obvykle potřebuje nápovědu k identifikaci správný proces. Tady je jeden způsob, jak povolit použití Chrome.

### <a name="attach-the-debugger-to-client-side-script-using-chrome"></a>Připojit ladicí modul k skriptu na straně klienta s použitím Chrome

1. Zavřete všechna okna Chromu.

    Tato akce je nutné před spuštěním Chrome v režimu ladění.

2. Otevřete příkaz **Spustit** z tlačítka Windows **Start** (klikněte na něj pravým tlačítkem a zvolte **Spustit**) a zadejte následující příkaz:

    `chrome.exe --remote-debugging-port=9222`

    Tento příkaz spustí Chrome s povoleným laděním.

3. Přepněte do aplikace Visual Studio a nastavte zarážku ve zdrojovém kódu. (Nastavit zarážku do řádku kódu, který umožňuje zarážky, jako například `return` příkazu nebo `var` prohlášení).

    ![Nastavení zarážky](../javascript/media/tutorial-nodejs-react-set-breakpoint-client-code.png)

    Pokud potřebujete vyhledat konkrétní kód ve velké a vygenerovaný soubor, použijte **Ctrl**+**F** (**upravit** > **najít a nahradit**  >  **Rychle najít**).

4. Jako cíl ladění je v sadě Visual Studio vybraný Chrome. Stisknutím **Ctrl**+**F5** (**Ladit** > **Spustit bez ladění**) spusťte aplikaci v prohlížeči.

    Aplikace se otevře na nové kartě prohlížeče.

    Pokud je k dispozici na svém počítači Chrome, ale nezobrazí jako možnost, zvolte **procházet s** z rozevíracího seznamu cíl ladění a jako cíl výchozí prohlížeč vybrat Chrome (zvolte **nastavit jako výchozí**).

5. Zvolte **Ladit** > **Připojit k procesu**.

6. V **připojit k procesu** dialogového okna zvolte **komponenty WebKit kód** v **připojit k** zadejte **chrome** v poli filtru pro filtrování výsledky hledání.

    **Kód komponenty WebKit** je požadovaná hodnota pro Chrome, což je prohlížeče na základě Webkit.

7. Vyberte zpracování Chrome pomocí správného hostitele, portu (1337 na tomto obrázku) a vyberte **připojit**.

    ![Připojení k procesu](../javascript/media/tutorial-nodejs-react-attach-to-process.png)

    Pokud se v sadě Visual Studio otevřely Průzkumník modelu DOM a konzola jazyka JavaScript, je ladicí program správně připojený. Tyto nástroje pro ladění jsou podobné Chrome vývojářské nástroje a nástrojích F12 Tools pro Microsoft Edge.

    > [!NOTE]
    > Pokud se ladicí program nepřipojí a zobrazí se zpráva „Nelze připojit k procesu. Operace není platný v aktuálním stavu", použijte Správce úloh zavřete všechny instance chromu před zahájením Chrome v režimu ladění. Můžou být spuštěná rozšíření Chromu, která brání plnému režimu ladění.

8. Pokud kód se zarážkou již spuštěn, aktualizujte stránku vašeho prohlížeče k zarážce.

    Při pozastavení můžete v ladicím programu zkontrolovat stav aplikace tak, že přesunete ukazatel myši nad proměnné a použijete okna ladicího programu. Můžete v ladicím programu procházet kód pomocí krokování (**F5**, **F10** a **F11**).

    Pro minifikovaný nebo transpiled jazyka JavaScript, můžete narazit na zarážce v buď transpiled JavaScript nebo její namapované umístění v souboru TypeScript (pomocí zdrojových mapování), v závislosti na stavu vašeho prostředí a prohlížeče. V obou případech můžete procházet kód pomocí krokování a zkoumat proměnné.

    * Pokud potřebujete proniknout do kódu v souboru TypeScript a nemůžou to udělat, použijte **připojit k procesu** jak je popsáno v předchozích krocích připojení ladicího programu. Pak otevřete dynamicky generovaný soubor TypeScript z Průzkumníka řešení tak, že otevřete **dokumenty skriptu** > **filename.tsx**, nastavte zarážku a aktualizujte stránku v prohlížeči (nastavit Zarážka v řádku kódu, který umožňuje zarážky, například `return` příkaz nebo `var` prohlášení).

        Případně, pokud potřebujete proniknout do kódu v souboru TypeScript a nejde provést, použijte `debugger;` výroky TypeScript souboru, nebo místo toho nastavte zarážky v Chrome Developer Tools.

    * Pokud potřebujete proniknout do kódu v souboru jazyka JavaScript transpiled (například *aplikace bundle.js*) a nemůžou to udělat, odeberte soubor zdrojového mapování *filename.js.map*.

     > [!TIP]
     > Po prvním připojení k procesu podle tohoto postupu se v sadě Visual Studio 2017 můžete rychle znovu připojit ke stejnému procesu tak, že zvolíte **Ladit** > **Znovu připojit k procesu**.

## <a name="generate_sourcemaps"></a> Generovat zdrojová mapování pro ladění

Visual Studio poskytuje možnost používat a generovat zdrojová mapování na zdrojové soubory jazyka JavaScript. To je často potřeba, pokud zdrojem je minifikovaný nebo vytvořené transpiler jako TypeScript nebo Babel. Dostupné možnosti závisí na typu projektu.

* Ve výchozím nastavení projekt TypeScript v sadě Visual Studio generuje zdrojových mapování za vás.

* V projektu jazyka JavaScript potřebujete generovat zdrojová mapování například položky bundler jako webpacku a kompilátoru jako kompilátor TypeScript (nebo v Babel), které můžete přidat do projektu. Pro kompilátor TypeScript, musíte taky přidat *tsconfig.json* souboru. Příklad, který ukazuje, jak to udělat pomocí webpacku základní konfigurace, najdete v části [vytvoření aplikace Node.js pomocí React](../javascript/tutorial-nodejs-with-react-and-jsx.md).

> [!NOTE]
> Pokud jste ještě zdrojových mapování, přečtěte si prosím [Úvod do jazyka JavaScript zdrojového mapování](https://www.html5rocks.com/en/tutorials/developertools/sourcemaps/) než budete pokračovat.

Konfigurace rozšířených nastavení zdrojových mapování, použijte buď *tsconfig.json* nebo nastavení projektu na projekt TypeScript, ale ne obojí.

### <a name="configure-source-maps-using-a-tsconfigjson-file"></a>Konfigurovat pomocí souboru tsconfig.json zdrojových mapování

Pokud chcete přidat *tsconfig.json* soubor do projektu sady Visual Studio považuje za kořenový adresář projektu TypeScript. Chcete-li přidat soubor, klikněte pravým tlačítkem na projekt v Průzkumníku řešení a zvolte **Přidat > Nová položka > Web > Skripty > konfiguračního souboru JSON TypeScript**. A *tsconfig.json* souboru jako následující přidá do vašeho projektu.

```json
{
  "compilerOptions": {
    "noImplicitAny": false,
    "noEmitOnError": true,
    "removeComments": false,
    "sourceMap": true,
    "target": "es5"
  },
  "exclude": [
    "node_modules",
    "wwwroot"
  ]
}
```

#### <a name="compiler-options-for-tsconfigjson"></a>Možnosti kompilátoru pro tsconfig.json

* **inlineSourceMap**: Vygeneruje jediný soubor se zdrojovými mapováními namísto vytvoření samostatného zdrojového mapování pro každý zdrojový soubor.
* **inlineSources**: Vygeneruje zdroj spolu zdrojových mapování v rámci jednoho souboru; vyžaduje *inlineSourceMap* nebo *zdrojového mapování* nastavit.
* **mapRoot**: Určuje umístění, kde by měl ladicí program najít zdrojové mapovámí (*.map*) místo výchozího umístění souborů. Pomocí tohoto příznaku, pokud doba běhu *.map* soubory musí mít v jiném umístění než *js* soubory. Zadané umístění je součástí mapování zdroje pro přesměrování ladicí program na umístění *.map* soubory.
* **sourceMap**: Generuje odpovídající *.map* souboru.
* **sourceRoot**: Určuje umístění, kde by měl ladicí program najít soubory TypeScript namísto umístění zdroje. Tento příznak použijte, pokud za běhu zdroje musí být v jiném umístění než umístění v době návrhu. Zadané umístění se vloží do zdrojové mapovámí ke směrování ladicího programu k umístění zdrojových souborů.

Další informace o možnostech kompilátoru, najdete na stránce [– možnosti kompilátoru](https://www.typescriptlang.org/docs/handbook/compiler-options.html) na příručka TypeScript.

### <a name="configure-source-maps-using-project-settings"></a>Konfigurace zdrojových mapování pomocí nastavení projektu

Můžete také nakonfigurovat nastavení mapování zdroje pomocí vlastnosti projektu tak, že pravým tlačítkem myši projekt a následným výběrem možnosti **projektu > Vlastnosti > sestavení TypeScript > ladění**.

Tato nastavení projektu jsou k dispozici.

* **Generovat zdrojová mapování** (ekvivalentní **zdrojového mapování** v *tsconfig.json*): Generuje odpovídající *.map* souboru.
* **Zadat kořenový adresář zdrojových mapování** (ekvivalentní **mapRoot** v *tsconfig.json*): Určuje umístění, kde by měl ladicí program najít soubory mapy namísto generovaných umístění. Pomocí tohoto příznaku, pokud doba běhu *.map* soubory musí být umístěné v jiném umístění než souborů .js. Zadané umístění se vloží do zdrojové mapovámí ke směrování ladicího programu k umístění souborů mapy.
* **Zadat kořenový adresář souborů TypeScript** (ekvivalentní **sourceRoot** v *tsconfig.json*): Určuje umístění, kde by měl ladicí program najít soubory TypeScript namísto umístění zdroje. Tento příznak použijte, pokud za běhu zdrojové soubory musí být v jiném umístění než umístění v době návrhu. Zadané umístění se vloží do zdrojové mapovámí ke směrování ladicího programu k umístění zdrojových souborů.

## <a name="debug-javascript-in-dynamic-files-using-razor-aspnet"></a>Ladění JavaScriptu v dynamické soubory pomocí syntaxe Razor (ASP.NET)

Visual Studio poskytuje podporu ladění pro Chrome a Internet Explorer pouze. Zarážky se automaticky připojí JavaScript/TypeScript a vložené skripty na soubory ve formátu HTML.

Ladění dynamicky generované soubory není automatické. Nelze automaticky dosažení zarážky na soubory vygenerované se syntaxí Razor (cshtml, vbhtml). Existují dvě metody, která vám pomůže ladit tento typ souboru:

* **Místo `debugger;` příkazu, ve kterém chcete provést přerušení**: To způsobí, že dynamické skript pro zastavení spuštěného procesu a spustit ladění hned, zatímco se vytváří.
* **Načtení stránky a dynamické dokument v sadě Visual Studio otevřete**: Je budete potřebovat dynamické otevřít při ladění, nastavte zarážku a aktualizujte stránku pro tuto metodu za účelem práce. V závislosti na tom, jestli používáte Chrome nebo Internet Explorer najdete soubor pomocí jedné z následujících strategií:

   Pro Chrome, přejděte na **Průzkumníka řešení > dokumenty skriptu > YourPageName**.

    > [!NOTE]
    > Pokud používáte Chrome, může se zobrazit zpráva `no source is available between `<script>` tags.`This is OK, just continue debugging.

   Internet Explorer, přejděte na **Průzkumníka řešení > dokumenty skriptu > Windows Internet Explorer > YourPageName**.

Další informace najdete v tématu [Client-side ladění projektů ASP.NET v prohlížeči Google Chrome](https://blogs.msdn.microsoft.com/webdev/2016/11/21/client-side-debugging-of-asp-net-projects-in-google-chrome/).
