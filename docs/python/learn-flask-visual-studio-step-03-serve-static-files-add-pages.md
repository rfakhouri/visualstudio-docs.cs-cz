---
title: Kurz – další Flask v sadě Visual Studio, krok 3
description: Návod, Flask základy v kontextu projektů sady Visual Studio, konkrétně který ukazuje, jak statické soubory, přidání stránky v aplikaci, a používat šablonu dědičnosti
ms.date: 06/04/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: tutorial
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: 384905370a16cbdcd9b4c9165f079bcbdf71a250
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34752497"
---
# <a name="tutorial-step-3-serve-static-files-add-pages-and-use-template-inheritance"></a>Kurz – krok 3: statické soubory, přidat stránky a používat šablonu dědičnosti

**Předchozí krok: [vytvoření aplikace Flask s zobrazení a stránka šablony](learn-flask-visual-studio-step-02-create-app.md)**

V předchozích krocích tohoto kurzu když jste se naučili vytvoření minimální aplikace Flask obsahující pouze jednu stránku HTML, úplný a samostatný. Moderní webové aplikace, ale se obvykle skládají mnoho stránek a ujistěte se, používání sdílených prostředků, jako jsou soubory šablon stylů CSS a JavaScript zajistit konzistentní stylů a chování.

V tomto kroku, dozvíte, jak:

> [!div class="checklist"]
> - Použití šablon položek v sadě Visual Studio k rychle nové soubory různých typů s pohodlný často používaný kód (krok 3 - 1)
> - Poskytovat statické soubory z kódu (krok 3-2, volitelný)
> - Přidání dalších stránek v aplikaci (krok 3-3)
> - Použití dědičnosti šablony pro vytvoření záhlaví a nav panel, který se používá více stránek (krok 3-4)

## <a name="step-3-1-become-familiar-with-item-templates"></a>Krok 3 – 1: seznámit se s šablony položek

Když budete vyvíjet aplikace Flask, přidáte obvykle mnoho souborů další Python, HTML, CSS a JavaScript. Pro každý typ souboru (stejně jako další soubory jako `web.config` potřebné pro nasazení), Visual Studio poskytuje pohodlné [šablon položek](python-item-templates.md) které vám pomůžou začít.

Chcete-li zobrazit dostupné šablony, přejděte na **Průzkumníku řešení**, klikněte pravým tlačítkem na složku, ve kterém chcete vytvořit položku, vyberte **přidat** > **nová položka**:

![Přidat dialogové okno Nový položku v sadě Visual Studio](media/flask/step03-add-new-item-dialog.png)

Pro použití šablony, vyberte požadované šablony, zadejte název souboru a vyberte **OK**. Přidání položky tímto způsobem automaticky přidá soubor do projektu sady Visual Studio a označí změny zdrojového kódu.

### <a name="question-how-does-visual-studio-know-which-item-templates-to-offer"></a>Otázka: jak Visual Studio vědět, které položky šablony na nabídku?

Odpověď: Souboru projektu Visual Studio (`.pyproj`) obsahuje identifikátor typ projektu, který označuje jako projekt Python. Visual Studio použije tento typ identifikátor zobrazit pouze položky šablony, která jsou vhodná pro typ projektu. Tímto způsobem, Visual Studio může poskytovat širokou škálu šablony položek, pro mnoho typů projektů bez zobrazení výzvy k přepínat mezi nimi pokaždé, když.

## <a name="step-3-2-serve-static-files-from-your-app"></a>Krok 3 – 2: obsluhovat statické soubory z vaší aplikace.

Ve webové aplikaci vytvořené s nástroji Python (pomocí libovolnou architekturu) vaše soubory Python vždy spustit na serveru webového hostitele a se nikdy nepřenáší na počítači uživatele. Další soubory, ale například šablon stylů CSS a JavaScript, jsou používány výhradně prohlížeči, je jako server hostitele jednoduše dodá – je vždy, když jste požadovali. Tyto soubory jsou označovány jako "statická" soubory a Flask může poskytnout je automaticky bez nutnosti psaní jakéhokoli kódu. V rámci soubory HTML například lze odkazovat pouze na statické soubory pomocí relativní cesty v projektu. V první části v tomto kroku přidá soubor CSS do existující šablona stránky.

Když potřebujete poskytovat statický soubor z kódu, například prostřednictvím implementace koncový bod rozhraní API, Flask poskytuje pohodlnou metodu, která umožňuje odkazovat na soubory pomocí relativní cesty ve složce s názvem `static` (v kořenu projektu). Druhá část v tomto kroku ukazuje dané metody pomocí jednoduchého statických dat souboru.

V obou případech můžete uspořádat soubory v `static` ale chcete.

### <a name="use-a-static-file-in-a-template"></a>Použití statických souborů v šabloně

1. V **Průzkumníku řešení**, klikněte pravým tlačítkem na složku "HelloFlask" v projektu sady Visual Studio, vyberte **přidat** > **novou složku**a název složky `static`.

1. Klikněte pravým tlačítkem myši `static` složky a vyberte **přidat** > **novou položku**. V dialogovém okně se zobrazí, vyberte šablonu, "Šablony stylů", zadejte název souboru `site.css`a vyberte **OK**. `site.css` Souboru se zobrazí v projektu a je otevřen v editoru. Struktury složky by měla vypadat podobně jako na následujícím obrázku:

    ![Struktura statického souboru, jak je znázorněno v Průzkumníku řešení](media/flask/step03-static-file-structure.png)

1. Nahraďte obsah `site.css` následujícím kódem a uložte soubor:

    ```css
    .message {
        font-weight: 600;
        color: blue;
    }
    ```

1. Nahraďte obsah aplikace `templates/index.html` soubor s následující kód, který nahrazuje `<strong>` element použitým v kroku 2 s `<span>` odkazující `message` styl třídy. Použití třídy styl tímto způsobem vám dává mnohem větší flexibilitu v styly prvku.

    ```html
    <html>
        <head>
            <title>{{ title }}</title>
            <link rel="stylesheet" type="text/css" href="/static/site.css" />
        </head>
        <body>
            <span class="message">{{ message }}</span>{{ content }}
        </body>
    </html>
    ```

1. Spusťte projekt pozorovat výsledky. Ukončete aplikaci po dokončení a potvrdit změny jako zdroj ovládacího prvku, pokud chcete (jak je popsáno v [krok 2](learn-flask-visual-studio-step-02-create-app.md#commit-to-source-control)).

### <a name="serve-a-static-file-from-code"></a>Poskytovat statický soubor z kódu

Flask poskytuje funkci s názvem `serve_static_file` , kterou můžete volat z kódu odkazovat na všechny soubory v projektu `static` složky. Jednoduché koncový bod rozhraní API, která vrací soubor statických dat vytvoří následující proces).

1. Pokud jste tak ještě neučinili, vytvořte `static` složky: v **Průzkumníku řešení**, klikněte pravým tlačítkem na složku "HelloFlask" v projektu sady Visual Studio, vyberte **přidat**  >  **Novou složku**a název složky `static`.

1. V `static` složku vytvořit statický soubor dat JSON s názvem `data.json` s tímto obsahem (které jsou smysl ukázková data):

    ```json
    {
        "01": {
            "note" : "Data is very simple because we're demonstrating only the mechanism."
        }
    }
    ```

1. V `views.py`, přidat funkci s trasy nebo rozhraní api nebo data, která vrátí statický datový soubor pomocí `send_static_file` metoda:

    ```python
    @app.route('/api/data')
    def get_data():
      return app.send_static_file('data.json')
    ```

1. Spusťte aplikaci a přejděte do koncového data bodu/api/zobrazíte, že se vrátí statických souborů. Zastavte aplikaci, když jste hotovi.

### <a name="question-are-there-any-conventions-for-organizing-static-files"></a>Otázka: existují jakékoli konvence pro uspořádání statické soubory?

Odpověď: Můžete přidat další soubory HTML, CSS a JavaScript v vaší `static` složky ale chcete. Typickým způsobem uspořádat statické soubory, je vytvořit podsložky s názvem `fonts`, `scripts`, a `content` (pro šablony stylů a všechny další soubory).

### <a name="question-how-do-i-handle-url-variables-and-query-parameters-in-an-api"></a>Otázka: jak I zpracování adresy URL proměnné a parametry dotazu v rozhraní API?

Odpověď: Naleznete v odpovědi v kroku 1 – 4 [Otázka: jak Flask pracovat proměnné tras adresy URL a parametrů dotazu?](learn-flask-visual-studio-step-01-project-solution.md#qa-url-variables)

## <a name="step-3-3-add-a-page-to-the-app"></a>Krok 3 – 3: Přidat stránku do aplikace

Přidání další stránky do aplikace znamená následující:

- Přidejte funkci Python, která definuje zobrazení.
- Přidáte šablonu pro značek.
- Přidat potřebné směrování na projekt Django `urls.py` souboru.

Následující postup přidání stránky "O" na "HelloFlask" projekt a odkazy na této stránce z domovské stránky:

1. V **Průzkumníku řešení**, klikněte pravým tlačítkem myši `templates` složky, vyberte **přidat** > **nová položka**, vyberte šablonu, položka "HTML stránka", zadejte název souboru `about.html`a vyberte **OK**.

    > [!Tip]
    > Pokud **nová položka** příkaz se nezobrazí na **přidat** nabídky, ujistěte se, že jste zastavená aplikace tak, aby Visual Studio ukončí režim ladění.

1. Nahraďte obsah `about.html` s následující kód (nahradíte explicitní odkaz na domovskou stránku s jednoduché navigačního panelu v kroku 3-4):

    ```html
    <html>
        <head>
            <title>{{ title }}</title>
            <link rel="stylesheet" type="text/css" href="/static/site.css" />
        </head>
        <body>
            <div><a href="home">Home</a></div>
            {{ content }}
        </body>
    </html>
    ```

1. Otevřete aplikaci `views.py` souboru a přidejte funkce s názvem `about` šablony, který používá:

    ```python
    @app.route('/about')
    def about():
        return render_template(
            "about.html",
            title = "About HelloFlask",
            content = "Example app page for Flask.")
    ```

1. Otevřete `templates/index.html` souboru a přidejte následující řádek hned v rámci `<body>` elementu, který chcete propojit stránku o (znovu, nahradíte tento odkaz s navigačního panelu v kroku 3-4):

    ```html
    <div><a href="about">About</a></div>
    ```

1. Uložte všechny soubory pomocí **soubor** > **Uložit vše** příkazu nabídky, nebo jenom stiskněte nebo Ctrl + Shift + S. (Technicky, tento krok není potřeba, protože spuštění projektu v sadě Visual Studio automaticky uloží soubory. Nicméně je dobré příkazu, který bude vědět o!)

1. Spusťte projekt chcete pozorovat výsledky a zkontrolovat, navigace mezi stránkami. Zastavte aplikaci po dokončení.

### <a name="question-does-the-name-of-a-page-function-matter-to-flask"></a>Otázka: Název stránky funkce vás Flask?

Odpověď: Ne, protože je `@app.route` dekoratéra, který určuje adresy URL, pro které Flask volá funkci ke generování odpovědi. Vývojáři obvykle odpovídal názvu funkce na trasu, ale tyto odpovídající není povinné.

## <a name="step-3-4-use-template-inheritance-to-create-a-header-and-nav-bar"></a>Krok 3 – 4: použití dědičnosti šablony pro vytvoření záhlaví a nav panelu

Místo nutnosti explicitní navigační odkazy na každé stránce, použijte moderní webové aplikace obvykle hlavičku značky a navigační panel, který poskytuje nejdůležitější odkazů na stránky, místní nabídky a tak dále. Pokud chcete mít jistotu, že hlavičku a navigačního panelu jsou stejné na všech stránkách, ale nechcete zopakujte stejný kód v každé šabloně stránky. Místo toho můžete definovat společné části všech stránek na jednom místě.

Ukázka systému na flask (Jinja ve výchozím nastavení) poskytuje dva prostředky pro opětovné použití konkrétní prvky napříč více šablon: zahrnuje a dědičnost.

- *Zahrnuje* se další stránka šablony, které můžete vložit na určitém místě v šabloně odkazující pomocí syntaxe `{% include <template_path> %}`. Proměnnou můžete také použít, pokud chcete změnit cestu dynamicky v kódu. Zahrnuje jsou obvykle používány v těle stránky načítat v šabloně sdílené na určité místo na stránce.

- *Dědičnost* používá `{% extends <template_path> %}` na začátku stránky šablonu, která má zadejte sdílený základní šablonu, která odkazující šablony pak staví na. Dědičnost se běžně používá k definování sdílené rozložení, navigačního panelu a jiných struktur pro stránky aplikace tak, aby odkazující šablony potřebovat pouze přidávat nebo upravovat určité oblasti základní šablony názvem *bloky*.

V obou případech `<template_path>` je relativní vzhledem ke aplikace `templates` složky (`../` nebo `./` povolené jsou i).

Určí šablonu základní *bloky* pomocí `{% block <block_name> %}` a `{% endblock %}` značky. Pokud šablonu odkazující se stejným názvem bloku použije značky, přednost před jeho obsah bloku, základní šablony.

Následující kroky ukazují dědičnosti:

1. V dané aplikaci `templates` složky, vytvořte nový soubor HTML (pomocí **přidat** > **nová položka** kontextové nabídky nebo **přidat**  >   **Stránky HTML**) názvem `layout.html`a nahraďte jeho obsah kód níže. Můžete zjistit, že tato šablona obsahuje blok s názvem "obsah", je všechno, co odkazující stránky potřeba nahradit:

    ```html
    <!DOCTYPE html>
    <html>
    <head>
        <meta charset="utf-8" />
        <title>{{ title }}</title>
        <link rel="stylesheet" type="text/css" href="/static/site.css" />
    </head>

    <body>
        <div class="navbar">
            <a href="/" class="navbar-brand">Hello Flask</a>
            <a href="{{ url_for('home') }}" class="navbar-item">Home</a>
            <a href="{{ url_for('about') }}" class="navbar-item">About</a>
        </div>

        <div class="body-content">
            {% block content %}
            {% endblock %}
            <hr/>
            <footer>
                <p>&copy; 2018</p>
            </footer>
        </div>
    </body>
    </html>
    ```

1. Přidejte následující styly do aplikace `static/site.css` souboru (Tento postup není pokusu ukázka tady přizpůsobivý návrh; tyto styly jsou jednoduše generovat výsledek zajímavé):

    ```css
    .navbar {
        background-color: lightslategray;
        font-size: 1em;
        font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
        color: white;
        padding: 8px 5px 8px 5px;
    }

    .navbar a {
        text-decoration: none;
        color: inherit;
    }

    .navbar-brand {
        font-size: 1.2em;
        font-weight: 600;
    }

    .navbar-item {
        font-variant: small-caps;
        margin-left: 30px;
    }

    .body-content {
        padding: 5px;
        font-family:'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    }
    ```

1. Upravit `templates/index.html` odkazovat na základní šablony a přepsat blok s obsahem. Můžete zjistit, že pomocí dědičnosti této šablony se změní na jednoduchý:

    ```html
    {% extends "layout.html" %}
    {% block content %}
    <span class="message">{{ message }}</span>{{ content }}
    {% endblock %}
    ```

1. Upravit `templates/about.html` také odkazovat na základní šablony a přepsat blok s obsahem:

    ```html
    {% extends "layout.html" %}
    {% block content %}
    {{ content }}
    {% endblock %}
    ```

1. Spusťte server, abyste mohli pozorovat výsledky. Server po dokončení zavřete.

    ![Spuštěné aplikaci zobrazující navigačního panelu](media/flask/step03-nav-bar.png)

1. Protože jste provedli významné změny aplikace, znovu je vhodná doba na [uložte provedené změny do správy zdrojového kódu](learn-django-in-visual-studio-step-02-create-an-app.md#commit-to-source-control).

## <a name="next-steps"></a>Další kroky

> [!div class="nextstepaction"]
> [Použít úplnou šablonu webový projekt Flask](learn-flask-visual-studio-step-04-full-flask-project-template.md)

## <a name="going-deeper"></a>Budete hlubší

- Další možnosti Jinja šablon, jako je například tok řízení, najdete v části [dokumentace návrháře šablony Jinja](http://jinja.pocoo.org/docs/2.10/templates) (jinja.pocoo.org)
- Podrobnosti o použití `url_for`, najdete v části [url_for](http://flask.pocoo.org/docs/1.0/api/?highlight=url_for#flask.url_for) v dokumentaci k objektu aplikace Flask (flask.pocoo.org)
- Kurz zdrojového kódu na Githubu: [Microsoft nebo python – ukázka vs-learning-flask](https://github.com/Microsoft/python-sample-vs-learning-flask)