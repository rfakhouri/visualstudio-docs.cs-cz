---
title: Kurz – další Django v sadě Visual Studio, krok 3
description: Návod, základní informace o rozhraní Django v kontextu projektů sady Visual Studio, konkrétně který ukazuje, jak statické soubory, přidání stránky v aplikaci, a používat šablonu dědičnosti
ms.date: 04/25/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: tutorial
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: a6eb2d2c690642a12be6ced7da29b0e85bdbb046
ms.sourcegitcommit: 4e605891d0dfb3ab83150c17c074bb98dba29d15
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/26/2018
ms.locfileid: "36947073"
---
# <a name="step-3-serve-static-files-add-pages-and-use-template-inheritance"></a>Krok 3: Obsluhovat statické soubory, přidat stránky a použití šablony dědičnosti

**Předchozí krok: [vytvoření aplikace Django s zobrazení a stránka šablony](learn-django-in-visual-studio-step-02-create-an-app.md)**

V předchozích krocích tohoto kurzu když jste se naučili vytvoření minimální aplikace Django s jednu stránku HTML, úplný a samostatný. Moderní webové aplikace, ale se obvykle skládají mnoho stránek a ujistěte se, používání sdílených prostředků, jako jsou soubory šablon stylů CSS a JavaScript zajistit konzistentní stylů a chování.

V tomto kroku, dozvíte, jak:

> [!div class="checklist"]
> - Použití šablon položek v sadě Visual Studio k rychle nové soubory různých typů s pohodlný často používaný kód (krok 3 - 1)
> - Konfigurace projektu Django poskytovat statické soubory (krok 3-2)
> - Přidání dalších stránek v aplikaci (krok 3-3)
> - Použití dědičnosti šablony pro vytvoření záhlaví a nav panel, který se používá více stránek (krok 3-4)

## <a name="step-3-1-become-familiar-with-item-templates"></a>Krok 3 – 1: seznámit se s šablony položek

Když budete vyvíjet aplikace Django, přidáte obvykle mnoho souborů další Python, HTML, CSS a JavaScript. Pro každý typ souboru (stejně jako další soubory jako `web.config` potřebné pro nasazení), Visual Studio poskytuje pohodlné [šablon položek](python-item-templates.md) které vám pomůžou začít.

Chcete-li zobrazit dostupné šablony, přejděte na **Průzkumníku řešení**, klikněte pravým tlačítkem na složku, ve kterém chcete vytvořit položku, vyberte **přidat** > **nová položka**:

![Přidat dialogové okno Nový položku v sadě Visual Studio](media/django/step03-add-new-item-dialog.png)

Pro použití šablony, vyberte požadované šablony, zadejte název souboru a vyberte **OK**. Přidání položky tímto způsobem automaticky přidá soubor do projektu sady Visual Studio a označí změny zdrojového kódu.

### <a name="question-how-does-visual-studio-know-which-item-templates-to-offer"></a>Otázka: jak Visual Studio vědět, které položky šablony na nabídku?

Odpověď: Souboru projektu Visual Studio (`.pyproj`) obsahuje identifikátor typ projektu, který označuje jako projekt Python. Visual Studio použije tento typ identifikátor zobrazit pouze položky šablony, která jsou vhodná pro typ projektu. Tímto způsobem, Visual Studio může poskytovat širokou škálu šablony položek, pro mnoho typů projektů bez zobrazení výzvy k přepínat mezi nimi pokaždé, když.

## <a name="step-3-2-serve-static-files-from-your-app"></a>Krok 3 – 2: obsluhovat statické soubory z vaší aplikace.

Ve webové aplikaci vytvořené s nástroji Python (pomocí libovolnou architekturu) vaše soubory Python vždy spustit na serveru webového hostitele a se nikdy nepřenáší na počítači uživatele. Další soubory, ale například šablon stylů CSS a JavaScript, jsou používány výhradně prohlížeči, je jako server hostitele jednoduše dodá – je vždy, když jste požadovali. Tyto soubory jsou označovány jako "statická" soubory a Django může poskytnout je automaticky bez nutnosti psaní jakéhokoli kódu.

Ve výchozím nastavení poskytovat statické soubory z aplikace je nakonfigurované na projekt Django `static` složky díky tyto řádky v projektu Django `settings.py`:

```python
# Static files (CSS, JavaScript, Images)
# https://docs.djangoproject.com/en/1.9/howto/static-files/

STATIC_URL = '/static/'

STATIC_ROOT = posixpath.join(*(BASE_DIR.split(os.path.sep) + ['static']))
```

Můžete uspořádat soubory pomocí libovolné struktury složek v rámci `static` a pak použít relativní cesty k odkazování na soubory v této složce. K předvedení tento proces, přidá soubor CSS do aplikace následující kroky a potom pomocí této šablony stylů v `index.html` šablony:

1. V **Průzkumníku řešení**, klikněte pravým tlačítkem na složku "HelloDjangoApp" v projektu sady Visual Studio, vyberte **přidat** > **novou složku**a název složky `static`.

1. Klikněte pravým tlačítkem myši `static` složky a vyberte **přidat** > **novou položku**. V dialogovém okně se zobrazí, vyberte šablonu, "Šablony stylů", zadejte název souboru `site.css`a vyberte **OK**. `site.css` Souboru se zobrazí v projektu a je otevřen v editoru. Struktury složky by měla vypadat podobně jako na následujícím obrázku:

    ![Struktura statického souboru, jak je znázorněno v Průzkumníku řešení](media/django/step03-static-file-structure.png)

1. Nahraďte obsah `site.css` následujícím kódem a uložte soubor:

    ```css
    .message {
        font-weight: 600;
        color: blue;
    }
    ```

1. Nahraďte obsah aplikace `templates/HelloDjangoApp/index.html` soubor s následující kód, který nahrazuje `<strong>` element použitým v kroku 2 s `<span>` odkazující `message` styl třídy. Použití třídy styl tímto způsobem vám dává mnohem větší flexibilitu v styly prvku. (Pokud jste to ještě přesunuli `index.html` do podsložky v `templates`, odkazovat na [šablony namespacing](learn-django-in-visual-studio-step-02-create-an-app.md#template-namespacing) v kroku 2.)

    ```html
    <html>
        <head>
            <title>{{ title }}</title>
            {% load staticfiles %} <!-- Instruct Django to load static files -->
            <link rel="stylesheet" type="text/css" href="{% static 'site.css' %}" />
        </head>
        <body>
            <span class="message">{{ message }}</span>{{ content }}
        </body>
    </html>
    ```

1. Spusťte projekt pozorovat výsledky. Stop pro server po dokončení a provést změny jako zdroj ovládacího prvku, pokud chcete (jak je popsáno v [krok 2](learn-django-in-visual-studio-step-02-create-an-app.md#commit-to-source-control)).

### <a name="question-what-is-purpose-of-the--load-staticfiles--tag"></a>Otázka: co je účelem {% zatížení, které staticfiles %} značku?

Odpověď: `{% load staticfiles %}` řádku je vyžadována před odkazující na statické soubory v elementech jako `<head>` a `<body>`. V příkladu v této části "staticfiles" odkazuje na vlastní Django šablony značky sadu, která je, co vám umožňuje používat `{% static %}` syntaxe odkazovat na statické soubory.  Bez `{% load staticfiles %}`, uvidíte výjimku při spuštění aplikace.

### <a name="question-are-there-any-conventions-for-organizing-static-files"></a>Otázka: existují jakékoli konvence pro uspořádání statické soubory?

Odpověď: Můžete přidat další soubory HTML, CSS a JavaScript v vaší `static` složky ale chcete. Typickým způsobem uspořádat statické soubory, je vytvořit podsložky s názvem `fonts`, `scripts`, a `content` (pro šablony stylů a všechny další soubory). V každém případě nezapomeňte zahrnout tyto složky relativní cesta k souboru v `{% static %}` odkazy.

## <a name="step-3-3-add-a-page-to-the-app"></a>Krok 3 – 3: Přidat stránku do aplikace

Přidání další stránky do aplikace znamená následující:

- Přidejte funkci Python, která definuje zobrazení.
- Přidáte šablonu pro značek.
- Přidat potřebné směrování na projekt Django `urls.py` souboru.

Následující postup přidání stránky "O" na "HelloDjangoApp" projekt a odkazy na této stránce z domovské stránky:

1. V **Průzkumníku řešení**, klikněte pravým tlačítkem myši `templates/HelloDjangoApp` složky, vyberte **přidat** > **nová položka**, vyberte šablonu, položka "HTML stránka", zadejte název souboru `about.html`a vyberte **OK**.

    > [!Tip]
    > Pokud **nová položka** příkaz se nezobrazí na **přidat** nabídky, ujistěte se, že jste zastavená serveru tak, aby Visual Studio ukončí režim ladění.

1. Nahraďte obsah `about.html` s následující kód (nahradíte explicitní odkaz na domovskou stránku s jednoduché navigačního panelu v kroku 3-4):

    ```html
    <html>
        <head>
            <title>{{ title }}</title>
            {% load staticfiles %}
            <link rel="stylesheet" type="text/css" href="{% static 'site.css' %}" />
        </head>
        <body>
            <div><a href="home">Home</a></div>
            {{ content }}
        </body>
    </html>
    ```

1. Otevřete aplikaci `views.py` souboru a přidejte funkce s názvem `about` šablony, který používá:

    ```python
    def about(request):
        return render(
            request,
            "HelloDjangoApp/about.html",
            {
                'title' : "About HelloDjangoApp",
                'content' : "Example app page for Django."
            }
        )
    ```

1. Otevřete projekt Django `urls.py` souboru a přidejte následující řádek na `urlPatterns` pole:

    ```python
    url(r'^about$', HelloDjangoApp.views.about, name='about'),
    ```

1. Otevřete `templates/HelloDjangoApp/index.html` souboru a přidejte následující řádek níže `<body>` elementu, který chcete propojit stránku o (znovu, nahradíte tento odkaz s navigačního panelu v kroku 3-4):

    ```html
    <div><a href="about">About</a></div>
    ```

1. Uložte všechny soubory pomocí **soubor** > **Uložit vše** příkazu nabídky, nebo jenom stiskněte nebo Ctrl + Shift + S. (Technicky, tento krok není potřeba, protože spuštění projektu v sadě Visual Studio automaticky uloží soubory. Nicméně je dobré příkazu, který bude vědět o!)

1. Spusťte projekt chcete pozorovat výsledky a zkontrolovat, navigace mezi stránkami. Server po dokončení zavřete.

### <a name="question-i-tried-using-index-for-the-link-to-the-home-page-but-it-didnt-work-why"></a>Otázka: Pokus o použití "index" pro odkaz na domovskou stránku, ale nepracuje. Proč?

Odpověď: I když zobrazení fungovat v `views.py` jmenuje `index`, adresu URL směrování vzory v projektu Django `urls.py` soubor neobsahuje regulární výraz, který se shoduje s řetězcem "index". Tak, aby odpovídaly tento řetězec, budete muset přidat další položku pro vzor `^index$`.

Jak je znázorněno v další části, je mnohem lepší použít `{% url '<pattern_name>' %}` značky v šabloně stránky k odkazování na *název* vzoru, ve kterém případu Django správnou adresu URL pro vás vytvoří. Například nahradit `<div><a href="home">Home</a></div>` v `about.html` s `<div><a href="{% url 'index' %}">Home</a></div>`. Použití 'index' funguje tady, protože první adresa URL vzor v `urls.py` se ve skutečnosti s názvem "index" (základě `name='index'` argument). 'Domácí, můžete použít také k odkazování na druhém vzorku.

## <a name="step-3-4-use-template-inheritance-to-create-a-header-and-nav-bar"></a>Krok 3 – 4: použití dědičnosti šablony pro vytvoření záhlaví a nav panelu

Místo nutnosti explicitní navigační odkazy na každé stránce, použijte moderní webové aplikace obvykle hlavičku značky a navigační panel, který poskytuje nejdůležitější odkazů na stránky, místní nabídky a tak dále. Pokud chcete mít jistotu, že hlavičku a navigačního panelu jsou stejné na všech stránkách, ale nechcete zopakujte stejný kód v každé šabloně stránky. Místo toho můžete definovat společné části všech stránek na jednom místě.

Django je ukázka systém poskytuje dva znamená pro opětovné použití konkrétní prvky napříč více šablon: zahrnuje a dědičnost.

- *Zahrnuje* se další stránka šablony, které můžete vložit na určitém místě v šabloně odkazující pomocí syntaxe `{% include <template_path> %}`. Proměnnou můžete také použít, pokud chcete změnit cestu dynamicky v kódu. Zahrnuje jsou obvykle používány v těle stránky načítat v šabloně sdílené na určité místo na stránce.

- *Dědičnost* používá `{% extends <template_path> %}` na začátku stránky šablonu, která má zadejte sdílený základní šablonu, která odkazující šablony pak staví na. Dědičnost se běžně používá k definování sdílené rozložení, navigačního panelu a jiných struktur pro stránky aplikace tak, aby odkazující šablony potřebovat pouze přidávat nebo upravovat určité oblasti základní šablony názvem *bloky*.

V obou případech `<template_path>` je relativní vzhledem ke aplikace `templates` složky (`../` nebo `./` povolené jsou i).

Základní šablonu určí bloky pomocí `{% block <block_name> %}` a `{% endblock %}` značky. Pokud šablonu odkazující se stejným názvem bloku použije značky, přednost před jeho obsah bloku, základní šablony.

Následující kroky ukazují dědičnosti:

1. V dané aplikaci `templates/HelloDjangoApp` složky, vytvořte nový soubor HTML (pomocí **přidat** > **nová položka** kontextové nabídky nebo **přidat**  >   **Stránky HTML**) názvem `layout.html`a nahraďte jeho s kód níže. Můžete zjistit, že tato šablona obsahuje blok s názvem "obsah", je všechno, co odkazující stránky potřeba nahradit:

    ```html
    <!DOCTYPE html>
    <html>
    <head>
        <meta charset="utf-8" />
        <title>{{ title }}</title>
        {% load staticfiles %}
        <link rel="stylesheet" type="text/css" href="{% static 'site.css' %}" />
    </head>

    <body>
        <div class="navbar">
           <a href="/" class="navbar-brand">Hello Django</a>
           <a href="{% url 'home' %}" class="navbar-item">Home</a>
           <a href="{% url 'about' %}" class="navbar-item">About</a>
        </div>

        <div class="body-content">
    {% block content %}{% endblock %}
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

1. Upravit `templates/HelloDjangoApp/index.html` odkazovat na základní šablony a přepsat blok s obsahem. Můžete zjistit, že pomocí dědičnosti této šablony se změní na jednoduchý:

    ```html
    {% extends "HelloDjangoApp/layout.html" %}
    {% block content %}
    <span class="message">{{ message }}</span>{{ content }}
    {% endblock %}
    ```

1. Upravit `templates/HelloDjangoApp/about.html` také odkazovat na základní šablony a přepsat blok s obsahem:

    ```html
    {% extends "HelloDjangoApp/layout.html" %}
    {% block content %}
    {{ content }}
    {% endblock %}
    ```

1. Spusťte server, abyste mohli pozorovat výsledky. Server po dokončení zavřete.

    ![Spuštěné aplikaci zobrazující navigačního panelu](media/django/step03-nav-bar.png)

1. Protože jste měli významné změny do aplikace, znovu je vhodná doba na [uložte provedené změny do správy zdrojového kódu](learn-django-in-visual-studio-step-02-create-an-app.md#commit-to-source-control).

## <a name="next-steps"></a>Další kroky

> [!div class="nextstepaction"]
> [Použít úplnou šablonu webový projekt Django](learn-django-in-visual-studio-step-04-full-django-project-template.md)

## <a name="go-deeper"></a>Přejděte hlubší

- [Zápis první aplikace Django, část 3 (zobrazení)](https://docs.djangoproject.com/en/2.0/intro/tutorial03/) (docs.djangoproject.com)
- Další možnosti šablon Django, například tok řízení, najdete v části [jazyk šablony Django](https://docs.djangoproject.com/en/2.0/ref/templates/language/) (docs.djangoproject.com)
- Úplné podrobnosti o použití `{% url %}` značky najdete v tématu [url](https://docs.djangoproject.com/en/2.0/ref/templates/builtins/#url) v rámci [předdefinované šablony značky a filtry pro referenční informace k šablonám Django](https://docs.djangoproject.com/en/2.0/ref/templates/builtins/) (docs.djangoproject.com)
- Kurz zdrojového kódu na Githubu: [Microsoft nebo python – ukázka vs-learning-django](https://github.com/Microsoft/python-sample-vs-learning-django)