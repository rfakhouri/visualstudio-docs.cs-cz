---
title: "JavaScript v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 04/10/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 74dca14c-5071-416f-a92b-d09f95e3dfb8
caps.latest.revision: 
author: bowdenk7
ms.author: wilkelly
manager: ghogen
ms.openlocfilehash: 5b13f01a1a5ba13503932c73aef3a4825115497e
ms.sourcegitcommit: 873c0e1a31def013bcca1b0caa0eb0249de89bec
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2018
---
# <a name="javascript-in-visual-studio-2017"></a>JavaScript ve Visual Studio 2017

JavaScript je první třídy jazyk v sadě Visual Studio. Při psaní kódu v jazyce JavaScript v sadě Visual Studio IDE můžete použít téměř všechny standardní editační pomůcky (fragmenty kódu, funkci IntelliSense atd.). Pro mnoho typů aplikací a služeb můžete napsat kód JavaScript.

## <a name="ES6"></a> Podpora pro ECMAScript 2015 (ES6) a nad rámec

Visual Studio teď podporuje syntaxi jazyka aktualizací ECMAScript například ECMAScript 2015. prosinci 2016.

### <a name="what-is-ecmascript-2015"></a>Co je ECMAScript 2015?

JavaScript je stále vyvíjejí jako programovací jazyk a [TC39](http://www.ecma-international.org/memento/TC39.htm) zodpovídá výbor pro provedení aktualizací.
ECMAScript 2015 je aktualizace jazyka JavaScript, která přináší užitečné nové syntaxe a funkce. Pro podrobné informace o ES6 funkcí, podívejte se na [to](http://es6-features.org) referenční webový server.

Kromě podpory pro ECMAScript 2015 Visual Studio také podporuje ECMAScript 2016 a bude mít podporu pro budoucí verze ECMAScript při jejich vydání. Chcete-li udržovat tempo s TC39 a nejnovějších změnách v ECMAScript, postupujte podle práci [githubu](https://github.com/tc39).

### <a name="transpile-javascript"></a>Transpile JavaScript

Častých problémů s JavaScript je, že chcete použít nejnovější funkce jazyka ES6 +, protože pomáhají zvýšit produktivitu, ale vaše prostředí runtime (často prohlížeče) zatím nepodporují tyto nové funkce. To znamená, že buď mít ke sledování prohlížečů, které podporujete jaké funkce (může to být zdlouhavé), nebo budete potřebovat způsob, jak převést váš kód ES6 + na verzi, že váš cílový runtimes pochopit (obvykle ES5). Převod kódu na verzi, který modul runtime rozumí se obvykle označuje jako "transpiling".

Jeden z klíčových funkcích služby TypeScript je možnost transpile ES6 + kódu ES5 nebo ES3, takže můžete napsat kód, který umožňuje vám nejvíc produktivní, ale stále svůj kód spustit na jakékoli platformě. Protože JavaScript v [!include[vs_dev15](../../docs/misc/includes/vs_dev15_md.md)] používá služby ve stejném jazyce jako TypeScript, je příliš můžete využít výhod ES6 + k ES5 transpilation.

Než transpilation můžete nastavit, je vyžadován některé pochopení možností konfigurace.
TypeScript je nakonfigurovaný pomocí `tsconfig.json` souboru.
Chybí takový soubor použijí se některé výchozí hodnoty.
Z důvodu kompatibility se liší v kontextu, kde pouze tyto výchozí hodnoty jazyka JavaScript soubory (a volitelně `.d.ts` soubory) jsou k dispozici.
Ke kompilaci souborů JavaScript `tsconfig.json` soubor musí být přidán, a některé z těchto možností musí být explicitně nastavena.

Požadovaná nastavení pro soubor tsconfig jsou následující:

 - `allowJs`: Tato hodnota musí být nastavena na `true` pro rozpoznat souborů JavaScript. Výchozí hodnota je `false`, protože TypeScript kompilovaný do jazyka JavaScript a kompilátor nesmí obsahovat soubory, které jsou právě zkompilovat.
 - `outDir`: Tato hodnota musí být nastavená na umístění není zahrnutý v projektu, aby nejsou zjištěn a pak zahrnutý v projektu emitovaného soubory JavaScript (viz `exclude`).
 - `module`: Pokud používáte moduly, toto nastavení určuje kompilátor formát modulu emitovaného kód by měl použít (například `commonjs` pro uzel, nebo je například Browserify).
 - `exclude`: Toto nastavení stavy, které složky nechcete zahrnout do projektu.
 Umístění výstupu, jakož i jiný projekt složek, jako `node_modules` nebo `temp`, musí být přidaní do tohoto nastavení.
 - `enableAutoDiscovery`: Toto nastavení umožňuje automatické zjišťování a stahování souborů definic, jak je uvedeno dříve.
 - `compileOnSave`: Toto nastavení určuje kompilátor, pokud by měl znovu zkompiluje kdykoli zdrojový soubor je uložen v sadě Visual Studio.
 - `typeAcquisition`: Tato sada nastavení řídí chování automatického Typ pořízení (dál vysvětlují v [v této části](https://docs.microsoft.com/en-us/visualstudio/ide/javascript-intellisense#Auto))

Chcete-li převést soubory JavaScript na CommonJS moduly a umístěte je do `./out` složky, můžete použít následující `tsconfig.json` souboru:

```json
{
  "compilerOptions": {
    "module": "commonjs",
    "allowJs": true,
    "outDir": "out"
  },
  "exclude": [
    "node_modules",
    "wwwroot",
    "out"
  ],
  "compileOnSave": true,
  "typeAcquisition": {
    "enable": true
  }
}
```

S nastavením na místě, pokud zdrojový soubor (`./app.js`) existoval a obsahovala několik funkcí jazyka ECMAScript 2015 následujícím způsobem:

```js
import {Subscription} from 'rxjs/Subscription';  // ES6 import

class Foo {  // ES6 Class
    sayHi(name) {
        return `Hi ${name}, welcome to Salsa!`;  // ES6 template string
    }
}

export let sqr = x => x * x;  //ES6 export, let, and arrow function
export default Subscription;  //ES6 default export
```

Potom soubor by vygenerované k `./out/app.js` cílení ECMAScript 5 (výchozí), která vypadá nějak takto:

```js
"use strict";
var Subscription_1 = require('rxjs/Subscription');
var Foo = (function () {
    function Foo() {
    }
    Foo.prototype.sayHi = function (name) {
        return "Hi " + name + ", welcome to Salsa!";
    };
    return Foo;
}());
exports.sqr = function (x) { return x * x; };
Object.defineProperty(exports, "__esModule", { value: true });
exports.default = Subscription_1.Subscription;
```

## <a name="better-intellisense"></a>Lepší IntelliSense

JavaScript IntelliSense v [!include[vs_dev15](../../docs/misc/includes/vs_dev15_md.md)] bude nyní zobrazení mnoho další informace o parametry a seznamy členů. Toto nové informace jsou poskytovány služba jazyka TypeScript, který používá statické analysis pozadí v době pro lepší pochopení vašeho kódu. Můžete si přečíst další informace o nové rozhraní IntelliSense a jak to funguje [zde](/visualstudio/ide/javascript-intellisense/).

## <a name="JSX"></a> Podpora syntaxi JSX

JavaScript ve [!include[vs_dev15](../../docs/misc/includes/vs_dev15_md.md)] má bohatou podporu pro syntaxi JSX. JSX je sada syntaxe, které umožňuje značky HTML v rámci soubory JavaScript.

Následující obrázek znázorňuje komponentu reagují definované v `comps.tsx` TypeScript soubor a pak tato součást je používán z `app.jsx` souboru, bylo dokončeno s IntelliSense pro dokumentaci v rámci výrazy JSX a dokončování operací.
Nepotřebujete TypeScript zde tomto konkrétním příkladu právě se stane, tak, aby obsahovala nějaký TypeScript kód.

<img src="./media/react.png" height="500" width="640"/>

> [!NOTE]
> Převést syntaxi JSX reagují volá, nastavení `"jsx": "react"` musí být přidán do `compilerOptions` v `tsconfig.json` souboru.

Soubor JavaScript vytvořený v ". / out/app.js při sestavení by obsahovat kód:

```js
"use strict";
var comps_1 = require('./comps');
var x = React.createElement(comps_1.RepoDisplay, {description: "test"});
```

## <a name="configure-your-javascript-project"></a>Nakonfigurujete svůj projekt jazyka JavaScript

Služba jazyka používá technologii statické analýzy, což znamená, že analyzuje zdrojový kód bez skutečně proveden ho, aby bylo možné výsledky IntelliSense a poskytovat další úpravy funkce.
Proto větší množství a velikosti souborů, které jsou obsaženy kontextu projektu, více paměti a procesoru se použije během analýzy.
Z toho důvodu jsou několik výchozí předpokladů, které jsou vytvářeny o váš projekt tvar:

- `package.json` a `bower.json` seznamu závislosti používaných projektu a ve výchozím nastavení jsou zahrnuty v automatické získání typ (ATA)
- Na nejvyšší úrovni `node_modules` složka obsahuje zdrojový kód knihovny a její obsah se vyloučí z kontextu projektu ve výchozím nastavení
- Každý druhý `.js`, `.jsx`, `.ts`, a `.tsx` soubor je pravděpodobně mezi *vlastní* zdrojové soubory a musí být obsaženy v kontextu projektu

Ve většině případů bude moci stačí otevřít projekt a máte skvělé zkušenosti s používáním výchozí konfigurace projektu. Nicméně v projektech, které jsou velké nebo struktury jinou složku, může být žádoucí dále konfigurovat službu jazyk lepší zaměřit pouze na zdrojové soubory.

### <a name="override-defaults"></a>Přepsat výchozí hodnoty

Přidáním můžete přepsat výchozí konfigurace `tsconfig.json` souboru do kořenového adresáře projektu.
A `tsconfig.json` má několik různých možností, které můžete upravit váš projekt kontext.
Několik z nich jsou uvedené níže, ale pro úplnou sadu všechny možnosti, které jsou k dispozici, [najdete v části schéma úložiště](http://json.schemastore.org/tsconfig).

## <a name="important-tsconfigjson-options"></a>Důležité `tsconfig.json` možnosti

```json
{
  "compilerOptions": {
    "allowJs": true,          // include .js and .jsx in project context (defaults to only .ts and .tsx)
    "noEmit": true            // turns off downlevel compiler
  },
  "files": [],                // list of explicit files to include in the project context. Highest priority.
  "include": [],              // list of folders or glob patterns to include in the project context.
  "exclude": [],              // list of folders or glob patterns to exclude. Overridden by files array.
  "typeAcquisition": {
    "enable": true,           // Defaulted to "false" with a tsconfig. Enables better IntelliSense in JS.
    "include": [ "jquery" ],  // Specific libs to fetch .d.ts files that weren't picked up by ATA
    "exclude": [ "node" ]     // Specific libs to not fetch .d.ts files for
  }
}
```

### <a name="example-project-configuration"></a>Příklad konfigurace projektu

Zadaný projekt s následujícím nastavením:

- zdrojové soubory projektu jsou v `wwwroot/js`
- soubory projektu lib jsou v `wwwrrot/lib`
- `bootstrap`, `jquery`, `jquery-validation`, a `jquery-validation-unobtrusive` jsou uvedeny v `bower.json`
- `kendo-ui` ručně přidaná do složky lib

![Struktura složek](./media/folderStructure.png)

Můžete použít následující `tsconfig.json` zajistit jazyk služby pouze analyzuje zdrojové soubory vašeho v `js` složku, i nadále však načte a používá `.d.ts` soubory pro knihovny v vaší `lib` složky.

```json
{
  "compilerOptions": {
    "allowJs": true,
    "noEmit": true
  },
  "exclude": ["wwwroot/lib"],  //ignore lib folders, we will get IntelliSense via ATA
  "typeAcquisition": {
    "enable": true,
    "include": [ "kendo-ui" ]  //kendo-ui wasn't added via bower, so we need to list it here
  }
}
```
# <a name="troubleshooting-the-javascript-language-service-has-been-disabled-for-the-following-projects"></a>Řešení potíží s služba jazyka JavaScript byla zakázána pro následujících projektech
Když otevřete projekt jazyka JavaScript, která má velmi velké množství obsahu, může získat zprávu, která čte "služba jazyka JavaScript byla zakázána pro následujících projektech". Nejběžnější důvodem pro velmi velký objem zdroj JavaScript je z důvodu včetně knihovny se zdrojovým kódem, která překračuje limit projektu 20 MB.

Jednoduchý způsob, jak optimalizovat projektu je přidat `tsconfig.json` souboru do kořenového adresáře projektu umožníte služba jazyka vědět, které soubory jsou bezpečně ignorovat. Podle následující ukázky vyloučit nejběžnější adresáře, kde jsou uloženy knihovny:

```json
{
  "compilerOptions": {
    "allowJs": true,
    "allowSyntheticDefaultImports": true,
    "maxNodeModuleJsDepth": 2,
    "noEmit": true,
    "skipLibCheck": true
  },
  "exclude": [
    "**/bin",
    "**/bower_components",
    "**/jspm_packages",
    "**/node_modules",
    "**/obj",
    "**/platforms"
  ]
}
```

Přidejte další adresáře podle svých potřeb. Mezi další příklady patří "dodavatel" nebo "wwwroot/lib" adresáře. 

> [!NOTE]
> Vlastnost kompilátoru `disableSizeLimit` umožňuje také zakázat kontrola omezení 20 MB. Při použití této vlastnosti, protože zakázání limitu může dojít k selhání služba jazyka je potřeba zaveďte zvláštní opatření.

## <a name="notable-changes-from-visual-studio-2015"></a>Upozorňují na důležité změny z Visual Studia 2015

Jako [!include[vs_dev15](../../docs/misc/includes/vs_dev15_md.md)] funkce zcela nové jazykové služby, se několik chování, které se budou lišit nebo nepřítomny z předchozí zkušenosti.
Nejdůležitější změny jsou nahrazení VSDoc s JSDoc, odebrání vlastní `.intellisense.js` rozšíření a omezené IntelliSense pro vzory konkrétního kódu.

### <a name="no-more-references-or-referencesjs"></a>Žádné další `///<references/>` nebo `_references.js`

Dřív byla poměrně složitá pochopit v každém okamžiku, které soubory byly ve vašem oboru IntelliSense. Někdy je žádoucí, aby všechny soubory v oboru a jindy ho nebyl, a to vedlo k komplexní konfigurace zahrnující odkaz na ruční správy. Do budoucna už nemusíte myslíte o odkaz na správu a nepotřebujete tedy Trojitá lomítko odkazuje komentáře nebo `_references.js` soubory.

Najdete v článku [JavaScript IntelliSense](/visualstudio/ide/javascript-intellisense/) stránka Další informace o tom, jak funguje technologie IntelliSense.

### <a name="vsdoc"></a>VSDoc

Dokumentační komentáře XML, který se někdy označuje jako VSDocs, dříve může pro uspořádání vašeho zdrojového kódu s další data, která se použije pro narážecím ústrojím až IntelliSense výsledky.
VSDoc již není podporována pro [JSDoc](http://usejsdoc.org/about-getting-started.html) což je snazší zápisu a přijaté standard pro jazyk JavaScript.

### <a name="intellisensejs-extensions"></a>`.intellisense.js` Rozšíření

Dříve, můžete třeba vytvořit [IntelliSense rozšíření](https://msdn.microsoft.com/en-us/library/hh874692.aspx) které by umožňují můžete přidat vlastní dokončení výsledky pro knihovny třetích stran.
Tato rozšíření byly poměrně složité zápisu a instalace a odkazy na ně byl náročnější, takže chvíle nové jazykové služby nebude podporovat tyto soubory.
Jako alternativu jednodušší, můžete napsat do mají stejné výhody IntelliSense jako starý soubor definice TypeScript `.intellisense.js` rozšíření.
Další informace o deklaraci (`.d.ts`) vytváření souboru [zde](http://www.typescriptlang.org/docs/handbook/declaration-files/introduction.html).

### <a name="unsupported-patterns"></a>Nepodporované vzory

Protože nové jazykové služby používá technologii statické analýzy, nikoli modul provádění (čtení [tento problém](https://github.com/Microsoft/TypeScript/issues/4789) informace rozdíly), existuje několik JavaScript vzorů, které již nebude možné zjišťovat.
Nejběžnější vzor je vzor "expando".
Služba jazyka aktuálně neposkytuje IntelliSense pro objekty, které mají vlastnosti standardní po deklaraci.
Příklad:

```js
var obj = {};
obj.a = 10;
obj.b = "hello world";
obj. // IntelliSense won't show properties a or b
```

Tento problém můžete získat pomocí deklarace vlastnosti při vytváření objektu:

```js
var obj = {
    "a": 10,
    "b": "hello world"
}
obj. // IntelliSense shows properties a and b
```

Můžete také přidat komentář, JSDoc následujícím způsobem:

```js
/**
 * @type {{a: number, b: string}}
 */
var obj = {};
obj.a = 10;
obj.b = "hello world";
obj. // IntelliSense shows properties a and b
```
