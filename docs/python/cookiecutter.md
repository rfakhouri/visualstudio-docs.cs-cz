---
title: "CookieCutter rozšíření pro jazyk Python v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 07/12/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: article
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload: python
ms.openlocfilehash: 0844526b7c5dbc0955bc9cafff6f63121b9d7182
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="using-the-cookiecutter-extension"></a>Pomocí rozšíření Cookiecutter

[Cookiecutter](https://cookiecutter.readthedocs.io/en/latest/) poskytuje grafické uživatelské rozhraní k zjištění šablony, zadejte možnosti šablony a vytváření projektů a soubory. To je součástí Visual Studio 2017 a je možné nainstalovat odděleně v dřívějších verzích sady Visual Studio.

Cookiecutter vyžaduje Python 3.3 nebo vyšší (32bitové nebo 64bitové verze) nebo Anaconda 3 4.2 nebo novější (32bitová nebo 64bitová verze). Pokud není k dispozici vhodný překladač Pythonu, Visual Studio zobrazí upozornění. Pokud instalujete překladač Pythonu je spuštěn v sadě Visual Studio, klikněte na tlačítko Domů na panelu nástrojů Cookiecutter ke zjištění překladač nově nainstalovaný. (Viz [prostředí Python](python-environments.md) Další informace o prostředí v obecné.)

Po instalaci, vyberte **zobrazení > Cookiecutter Explorer** otevřete její okno:

![Hlavní okno Cookiecutter](media/cookiecutter-overview.png)

## <a name="cookiecutter-workflow"></a>Pracovní postup Cookiecutter

Práce s Cookiecutter je proces procházení a výběrem šablony, klonování do místního počítače, nastavení možností a pak vytváření kódu z této šablony, jak je popsáno v následujících částech.

### <a name="browsing-templates"></a>Procházení šablony

Domovská stránka Cookiecutter zobrazí seznam šablon můžete vybírat, uspořádány do následujících skupin:

| Skupina | Popis | 
| --- | --- |
| nainstalovaná | Šablony, které byly nainstalovány do místního počítače. Pokud je online šablony, je jeho úložiště automaticky klonovat do podsložky `~/.cookiecutters`. Stisknutím kombinace kláves můžete odstranit vybrané nainstalované šablony **Del**. |
| Doporučeno | Šablony načíst z doporučené informačního kanálu. Výchozí informačního kanálu je spravovaných společností Microsoft. V tématu [Cookiecutter možnosti](#cookiecutter-options) níže podrobnosti o přizpůsobení informačního kanálu. |
| GitHub | Výsledky hledání Githubu – klíčové slovo cookiecutter. Výsledky z Githubu se vraťte čísla stránek vložena, pokud jsou k dispozici, další výsledky **zatížení Další** se zobrazí na konci tohoto seznamu. |
| Vlastní | Do pole hledání zadáte do vlastního umístění, zobrazí se v této skupině. Můžete buď zadejte úplnou cestu k úložišti GitHub, nebo úplnou cestu ke složce na místním pevném disku. |

### <a name="cloning"></a>Klonování

Když vyberete některou šablonu následuje **Další**, Cookiecutter umožňuje pracovat na místní kopii.

Pokud vyberete šablonu z **doporučeno** nebo **Githubu** skupin, nebo zadejte vlastní adresu URL do pole pro vyhledávání a vyberte tuto šablonu, nemá klonovat a nainstalované na místním počítači. Pokud tato šablona byla nainstalována v předchozí relaci sady Visual Studio, se automaticky odstraní a naklonována na nejnovější verzi.

Pokud vyberete šablonu z **nainstalovaná** skupiny, nebo zadejte cestu ke složce vlastní do vyhledávacího pole a vyberte šablonu, Visual Studio načte šablona bez klonování.

> [!Important]
> Cookiecutter šablony jsou klonovat v jedné složce `~/.cookiecutters`. Každé podsložky jmenuje po název úložiště git, který nezahrnuje uživatelské jméno Githubu. Pokud klonovat různé šablony se stejným názvem, které pocházejí z různých autoři, může dojít v konfliktu. V takovém případě Cookiecutter nebudete přepsal stávající šablony s jinou šablonou se stejným názvem. Pokud chcete nainstalovat další šablony, musíte nejprve odstranit stávající.

### <a name="setting-template-options"></a>Možnosti nastavení šablony

Po instalaci šablony místně Cookiecutter zobrazí stránku možnosti, kde můžete určit, kam chcete Cookiecutter pro vygenerování souborů společně s dalšími možnostmi:

![Stránka Možnosti Cookiecutter](media/cookiecutter-template-options.png)

Každé šabloně Cookiecutter definuje vlastní sadu možností a určí výchozí hodnotu pro každé z nich (zobrazené jako navrhované text v každém vstupu). Výchozí hodnota může být fragment kódu, často, pokud je dynamická hodnotu, která používá jiné možnosti. 

Je možné upravit výchozí hodnoty pro konkrétní možnosti konfigurační soubor uživatele. Zjistí-li rozšíření Cookiecutter konfigurační soubor uživatele, přepíše výchozí hodnoty šablony s výchozími hodnotami konfiguraci uživatele. Toto chování je podrobněji [konfiguraci uživatele](https://cookiecutter.readthedocs.io/en/latest/advanced/user_config.html) části dokumentace Cookiecutter.

Pokud šablona specifikuje konkrétní úlohy sady Visual Studio spustit po generování kódu, další **spustit další úkoly při dokončení** možnost se zobrazí, která umožňuje pro vyjádření výslovného nesouhlasu tyto úlohy. Úlohy slouží nejčastěji otevřete webový prohlížeč, otevření souborů v editoru, nainstalujte závislosti a tak dále.

### <a name="create"></a>Create

Jakmile nastavíte možnosti, vyberte **vytvořit** pro generování kódu (zobrazí se upozornění, pokud zadaná výstupní složka není prázdná). Pokud jste se seznámili s výstupem šablony a nevadí přepsání souborů, toto upozornění můžete zavřít. Jinak vyberte možnost **zrušit**, zadejte prázdnou složku a ručně zkopírujte vytvořený soubory do složky neprázdný výstup.

Po úspěšném vytvoření soubory Cookiecutter nabízí možnost, chcete-li otevřít soubory v **Průzkumníku řešení**:

![Příkaz Průzkumník řešení zobrazující Cookiecutter](media/cookiecutter-files-created.png)

## <a name="cookiecutter-options"></a>Možnosti Cookiecutter

Jsou k dispozici prostřednictvím možnosti Cookiecutter **nástroje > Možnosti > Cookiecutter**:

![Možnosti Cookiecutter](media/cookiecutter-tools-options.png)

| Možnost | Popis |
| --- | --- |
| Doporučená adresa URL informačního kanálu | Umístění doporučené šablon informačního kanálu. Může být adresa URL nebo cestu k místnímu souboru. Ponechte prázdné použít výchozí Microsoft kurátorované kanálu adresu URL. Informační kanál poskytuje seznam umístění šablon, oddělených vložení znaků newline jednoduché. K žádosti o změny kurátorované informačního kanálu, ujistěte se, žádost o přijetí změn proti [zdroji na Githubu](https://github.com/Microsoft/PTVS/blob/master/Python/Product/Cookiecutter/CookiecutterFeed.txt). |
| Zobrazit nápovědu | Určuje viditelnost panelu Informace nápovědy v horní části okna Cookiecutter. |

## <a name="optimizing-cookiecutter-templates-for-visual-studio"></a>Optimalizace Cookiecutter šablon pro Visual Studio

Základní informace o vytváření šablony Cookiecutter, najdete v článku [Cookiecutter dokumentaci](https://cookiecutter.readthedocs.io/en/latest/first_steps.html). Cookiecutter rozšíření pro Visual Studio podporuje šablony vytvořené pro Cookiecutter v1.4.

Výchozí vykreslování proměnných šablony, závisí na typu dat (řetězec nebo seznam):

- Řetězec: Popisek název proměnné, textové pole pro zadání hodnoty a vodoznak zobrazující výchozí hodnota. Popis tlačítka v textovém poli se zobrazí výchozí hodnota.
- Seznam: Popisek název proměnné, pole se seznamem pro výběr hodnotu. Popis tlačítka na pole se seznamem zobrazí výchozí hodnota.

Je možné zvýšit na tento vykreslování zadáním dalších metadat v vaší `cookiecutter.json` soubor, který je specifické pro Visual Studio (a ignoruje pomocí rozhraní příkazového řádku Cookiecutter). Všechny vlastnosti jsou volitelné:

| Vlastnost | Popis |
| --- | --- |
| Popisek | Určuje, co se zobrazí nad editor pro proměnnou, ne v názvu proměnné. |
| Popis | Určuje popisek, který se zobrazí na textové pole, namísto výchozí hodnoty pro tuto proměnnou. |
| Adresa URL | Změní štítek na hypertextový odkaz popisku, který zobrazuje adresu URL. Kliknutím na hypertextový odkaz otevře výchozí prohlížeč uživatele pro tuto adresu URL. |
| Selektor | Umožňuje přizpůsobení editoru proměnné. Aktuálně jsou podporovány následující selektory:<ul><li>`string`: Standardního textového pole, výchozí hodnoty pro řetězce.</li><li>`list`: Pole se seznamem standard, výchozí hodnoty pro seznamy.</li><li>`yesno`: Pole se seznamem si vybrat mezi `y` a `n`, pro řetězce.</li><li>`odbcConnection`: Textové pole s tlačítko "...", které se zobrazí dialogové okno připojení databáze.</li></ul> |

Příklad:

```json
{
    "site_name": "web-app",
    "python_version": ["3.5.2", "2.7.12"],
    "use_azure": "y",

    "_visual_studio": {
        "site_name": {
            "label": "Site name",
            "description": "E.g. <site-name>.azurewebsites.net (can only contain alphanumeric characters and `-`)"
        },
        "python_version": {
            "label": "Python version",
            "description": "The version of Python to run the site on"
        },
        "use_azure" : {
            "label": "Use Azure",
            "description": "Include Azure deployment files",
            "selector": "yesno",
            "url": "https://azure.microsoft.com"
        }
    }
}
```

### <a name="running-visual-studio-tasks"></a>Spuštěné úlohy v sadě Visual Studio

Cookiecutter má funkci *Post-Generate zachytí* , který umožňuje spuštění libovolný kód Python po vygenerování soubory. I když je flexibilní, neumožňuje snadný přístup k sadě Visual Studio.

Můžete například chtít otevření souboru v editoru Visual Studio nebo v jeho webový prohlížeč nebo aktivovat rozhraní Visual Studio, které vyzývá uživatele k vytvoření virtuálního prostředí a nainstalujte balíček požadavky.

Povolit tyto scénáře, Visual Studio hledá rozšířené metadata v `cookiecutter.json` příkazů pro spuštění po uživatel otevře generované soubory v Průzkumníkovi řešení nebo po přidání souborů do existujícího projektu, který popisuje. (Znovu, můžete uživatele vyjádření výslovného nesouhlasu s spuštění úlohy tak, že smažete **spustit další úkoly při dokončení** v možnostech této šablony.)

Příklad:

```json
"_visual_studio_post_cmds": [
    {
        "name": "File.OpenFile",
        "args": "{{cookiecutter._output_folder_path}}\\readme.txt"
    },
    {
        "name": "Cookiecutter.ExternalWebBrowser",
        "args": "https://docs.microsoft.com"
    },
    {
        "name": "Python.InstallProjectRequirements",
        "args": "{{cookiecutter._output_folder_path}}\\dev-requirements.txt"
    }
]
```

Příkazy jsou zadány podle názvu a neměl používat Nelokalizováno (v angličtině) název pro práci na lokalizované instalaci sady Visual Studio. Můžete si otestovat a zjistit názvy příkazů v příkazovém okně Visual Studio.

Pokud chcete předat jeden argument, zadejte ji jako řetězec jako v předchozím příkladu.

Pokud nepotřebujete předávání argument, ponechte prázdný řetězec nebo vynechejte z formátu JSON:

```json
"_visual_studio_post_cmds": [
    {
        "name": "View.WebBrowser"
    }
]
```

Pomocí pole pro více argumentů. Přepínače rozdělit na samostatné argumenty přepínač a jeho hodnotu a využívat správné citací. Příklad:

```json
"_visual_studio_post_cmds": [
    {
        "name": "File.OpenFile",
        "args": [
            "{{cookiecutter._output_folder_path}}\\read me.txt",
            "/e:",
            "Source Code (text) Editor"
        ]
    }
]
```

Argumenty mohou odkazovat na jiné proměnné Cookiecutter. V příkladech výše, interní `_output_folder_path` proměnná se používá k vytvoření absolutní cestu k generované soubory.

Všimněte si, že `Python.InstallProjectRequirements` příkaz funguje jenom v případě přidávání souborů do existujícího projektu. Toto omezení existuje, protože příkaz zpracovává Python projekt v Průzkumníku řešení a neexistuje žádný projekt pro příjem zprávy v Průzkumníku řešení - zobrazení složky. Doufáme, odeberte omezení win budoucí verzi (a obecně poskytují lepší podporu zobrazení složky).

## <a name="troubleshooting"></a>Poradce při potížích

### <a name="error-loading-template"></a>Chyba načítání šablony

Některé šablony může používat typy neplatná data, jako je logická hodnota, v jejich `cookiecutter.json`. Tyto instance nahlásit Autor šablony výběrem **problémy** odkaz v informačním podokně šablony.

### <a name="hook-script-failed"></a>Propojte skriptu se nezdařilo

Některé šablony může použít po generování skripty, které nejsou kompatibilní s Cookiecutter uživatelského rozhraní. Například skriptů tento dotaz na vstup uživatele nezdaří z důvodu absence terminálu konzoly.

### <a name="hook-script-not-supported-on-windows"></a>Propojte skript není podporován v systému Windows

Pokud se skript post `.sh`, nemusí být přidružena k aplikaci na počítač se systémem Windows. Může se zobrazit dialogové okno Windows s žádostí o najít kompatibilní aplikace ve službě Windows store.

### <a name="templates-with-known-issues"></a>Šablony s známé problémy

Selhání klonu:

- **wildfish/cookiecutter-django-crud** (neplatný znak `|` v podsložce s názvem)
- **cookiecutter pyvanguard** (neplatný znak `|` v podsložce s názvem)

Selhání načtení:

- **chrisdev/wagtail-cookiecutter-foundation** (používá se v cookiecutter.json logický typ)
- **quintoandar/cookiecutter-android** (složka žádné šablony)

Spusťte selhání:

- **iknite nebo cookiecutter-ansible-role** (pozálohovacího skriptu háku vyžaduje konzoly vstup)
- **benregn/cookiecutter-django-ansible** (Jinja chyba)

Používá bash (ne závažné):

- **openstack-dev/cookiecutter**
