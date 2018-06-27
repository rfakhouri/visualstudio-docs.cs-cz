---
title: Kurz – další Flask v sadě Visual Studio, krok 4
description: Návod Flask základy v kontextu projektů sady Visual Studio, konkrétně funkce poskytuje webový projekt Flask a webový projekt Flask/Jade šablony.
ms.date: 05/25/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: tutorial
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: c463fdde3c22986211ed7345c3552b288516a4de
ms.sourcegitcommit: 4e605891d0dfb3ab83150c17c074bb98dba29d15
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/26/2018
ms.locfileid: "36947483"
---
# <a name="step-4-use-the-full-flask-web-project-template"></a>Krok 4: Použití kompletní šablonou webový projekt Flask

**Předchozí krok: [obsluhovat statické soubory, přidat stránky a použití šablony dědičnosti](learn-flask-visual-studio-step-03-serve-static-files-add-pages.md)**

Teď, když jste prozkoumali základní informace o Flask podle budovy aplikace na šabloně "Prázdný projekt Flask aplikace" v sadě Visual Studio, můžete snadno pochopit úplnější aplikaci, která je produkovaný šabloně "Webový projekt Flask".

V tomto kroku můžete nyní:

> [!div class="checklist"]
> - Vytvoření úplnější Flask webové aplikace pomocí šablony "Webový projekt Flask" a zkontrolujte strukturu projektu (krok 4 - 1)
> - Rady pro pochopení zobrazení a šablony stránek vytvořených šablonou projektu, které se skládají z tři stránky, které dědí ze šablony základní stránky a který využívá statické knihovny JavaScript jako jQuery a Bootstrap (krok 4-2)
> - Pochopení směrování adres URL poskytuje šablony (krok 4-3)

Tento článek se týká také k šabloně "Webový projekt Flask/Jade", která vytvoří aplikaci, která je stejná jako "Flask webového projektu" pomocí modulu Jade ukázka místo Jinja. Další podrobnosti jsou zahrnuty na konci tohoto článku.

## <a name="step-4-1-create-a-project-from-the-template"></a>Krok 4-1: Vytvořte projekt ze šablony

1. V sadě Visual Studio, přejděte na **Průzkumníku řešení**, klikněte pravým tlačítkem na řešení "LearningFlask" v tomto kurzu vytvořili a vyberte **přidat** > **nový projekt**. (Případně, pokud chcete používat nové řešení, vyberte **soubor** > **nový** > **projektu** místo.)

1. V dialogovém okně Nový projekt, vyhledejte a vyberte šablonu, "Webový projekt Flask", volání "FlaskWeb" projekt a vyberte **OK**.

1. Protože znovu obsahuje šablony `requirements.txt` souboru, Visual Studio zobrazí dotaz, kam se má nainstalovat tyto závislosti. Zvolte možnost **nainstalovat do virtuálního prostředí**a v **Přidání virtuálního prostředí** dialogovém okně vyberte **vytvořit** přijměte výchozí hodnoty.

1. Po dokončení nastavení virtuálního prostředí sady Visual Studio nastavte projekt "FlaskWeb", který má být výchozí nastavení pro řešení sady Visual Studio tak, že kliknete pravým tlačítkem na takový projekt v **Průzkumníku řešení** a výběrem **nastavit jako Spouštěný projekt**. Spouštěný projekt, který se zobrazí v tučné písmo, je co běží při spuštění ladicího programu.

    ![Průzkumník řešení zobrazující FlaskWeb projekt jako spouštěný projekt](media/flask/step04-second-project-in-solution-set-as-startup-project.png)

1. Vyberte **ladění** > **spustit ladění** (F5) nebo pomocí **Webový Server** tlačítka na panelu nástrojů ke spuštění serveru:

    ![Spustit webový server tlačítka panelu nástrojů v sadě Visual Studio](media/flask/run-web-server-toolbar-button.png)

1. Aplikace vytvořené pomocí šablony má tři stránky, domů, o a kontaktovat, což je přecházet mezi pomocí navigačního panelu. Trvat minutu nebo dvě prozkoumat různých částí aplikace. K ověřování pro aplikaci prostřednictvím **přihlásit** příkazu, použijte přihlašovací údaje superuživatel vytvořili dříve.

    ![Zobrazit v prohlížeči úplné webový projekt Flask aplikace](media/flask/step04-full-app-desktop-view.png)

1. Aplikace vytvořené pomocí šablony "Webový projekt Flask" využívá Bootstrap přizpůsobivé rozložení, která bude vyhovovat typy mobilních zařízení. Pokud chcete zobrazit tento odezvy velikosti prohlížeče úzké zobrazení tak, aby obsah vykreslí svisle a navigačního panelu se zobrazí ikona nabídky:

    ![Zobrazení Mobile (úzké) webový projekt Flask aplikace](media/flask/step04-full-app-mobile-view.png)

1. Můžete nechat aplikaci spuštěnou pro oddíly, které následují.

    Pokud budete chtít aplikaci zastavit a [potvrzení změn do správy zdrojového kódu](learn-flask-visual-studio-step-02-create-app.md#commit-to-source-control), poprvé otevřete **změny** stránky v **Team Explorer**, klikněte pravým tlačítkem na složku (virtuálního prostředí pravděpodobně `env`) a vyberte **ignorovat tyto místní položky**.

### <a name="examine-what-the-template-creates"></a>Zkontrolujte, vytvoří šablona

Šablona "Webový projekt Flask" vytvoří strukturu níže. Obsah je velmi podobné co jste vytvořili v předchozích krocích. Rozdílem je, že šablona "Webový projekt Flask" obsahuje více struktury `static` složky, protože obsahuje jQuery a Bootstrap přizpůsobivý návrh. Obraťte se na stránku také přidá šablona. Celkově platí Pokud jste postupovali podle předchozích kroků v tomto kurzu, všechno z šablony musí být známé.

- Soubory v kořenu projektu:
  - `runserver.py`, skript a spusťte aplikaci v rámci vývojového serveru.
  - `requirements.txt` obsahující závislost na Flask 0.x.
- `FlaskWeb` Složka obsahuje všechny soubory aplikace:
  - `__init.py__` označí kód aplikace jako modul Python, vytvoří objekt Flask a importuje zobrazení aplikace.
  - `views.py` obsahuje kód pro vykreslení stránky.
  - `static` Složka obsahuje podsložky s názvem `content` (soubory šablon stylů CSS), `fonts` (písma soubory), a `scripts` (JavaScript soubory).
  - `templates` Složka obsahuje `layout.html` základní šablony spolu s `about.html`, `contact.html`, a `index.html` pro konkrétní stránky, které každý rozšířit `layout.html`.

### <a name="question-is-it-possible-to-share-a-virtual-environment-between-visual-studio-projects"></a>Otázka: Je možné sdílet mezi projektů sady Visual Studio virtuálního prostředí?

Odpověď: Ano, ale učinit povědomí o různé projekty, které mohou používat různé balíčky v čase, a proto sdílené virtuální prostředí musí obsahovat všechny balíčky pro všechny projekty, které ho používají.

Nicméně pokud chcete použít existující virtuální prostředí, postupujte takto:

1. Po zobrazení výzvy k instalaci závislosti v sadě Visual Studio, vyberte **I je nainstaluje sám** možnost.
1. V **Průzkumníku řešení**, klikněte pravým tlačítkem myši **prostředí Python** uzel a vyberte možnost **přidat existující virtuální prostředí**.
1. Přejděte do a vyberte složku, která obsahuje virtuální prostředí a potom vyberte **OK**.

## <a name="step-4-2-understand-the-views-and-page-templates-created-by-the-project-template"></a>Krok 4-2: pochopení zobrazení a stránka šablony vytvořené v šabloně projektů

Jak zjistíte při spuštění projektu, aplikace obsahuje tři zobrazení: Domů, o a obraťte se na. Kód pro tato zobrazení je nalezena v `FlaskWeb/views.py`. Jednotlivé funkce zobrazení jednoduše volá `flask.render_template` cestou k šablonu a seznam argumentů pro hodnoty k šabloně proměnné. Například stránku o jsou zpracována `about` – funkce (jehož dekoratéra poskytuje směrování adres URL):

```python
@app.route('/about')
def about():
    """Renders the about page."""
    return render_template(
        'about.html',
        title='About',
        year=datetime.now().year,
        message='Your application description page.'
    )
```

`home` a `contact` jsou téměř shodná s podobnou dekoratéry a mírně odlišné argumenty funkce.

Šablony jsou umístěny v dané aplikaci `templates` složky. Základní šablony `layout.html`, je většina rozsáhlé. Ji označuje všechny potřebné statické soubory (JavaScript a CSS), definuje blok s názvem "obsah" jiných stránky přepsání a poskytuje další blok s názvem "skripty". Následující poznámky úryvky z `layout.html` zobrazit tyto konkrétní oblasti:

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8" />

    <!-- Define a viewport for Bootstrap's responsive rendering -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>{{ title }} - My Flask Application</title>

    <link rel="stylesheet" type="text/css" href="/static/content/bootstrap.min.css" />
    <link rel="stylesheet" type="text/css" href="/static/content/site.css" />
    <script src="/static/scripts/modernizr-2.6.2.js"></script>
</head>

<body>
    <!-- Navbar omitted -->

    <div class="container body-content">
        <!-- "content" block that pages are expected to override -->
        {% block content %}{% endblock %}
        <hr />
        <footer>
            <p>&copy; {{ year }} - My Flask Application</p>
        </footer>
    </div>

    <!-- Additional scripts; use the "scripts" block to add page-specific scripts.  -->
    <script src="/static/scripts/jquery-1.10.2.js"></script>
    <script src="/static/scripts/bootstrap.js"></script>
    <script src="/static/scripts/respond.js"></script>
    {% block scripts %}{% endblock %}

</body>
</html>
```

Šablony jednotlivých stránek, `about.html`, `contact.html`, a `index.html`, každý rozšíření základní šablony `layout.html`. `about.html` je nejjednodušší a zobrazuje `{% extends %}` a `{% block content %}` značky:

```html
{% extends "app/layout.html" %}

{% block content %}

<h2>{{ title }}.</h2>
<h3>{{ message }}</h3>

<p>Use this area to provide additional information.</p>

{% endblock %}
```

`index.html` a `contact.html` použít stejnou strukturu a zadejte delší obsahu v bloku "obsah".

## <a name="the-flaskjade-web-project-template"></a>Webový projekt Flask/Jade šablony

Jak je uvedeno na začátku tohoto článku, Visual Studio poskytují "Webový projekt Flask/Jade" šablony, která vytvoří aplikace, která je vizuálně identické co je produkovaný "Webový projekt Flask". Základní rozdíl je, že používá Jade ukázka modul, který je rozšíření Jinja, který implementuje koncepty s více stručného jazyk. Konkrétně Jade používá klíčová slova místo značky v {% oddělovače, například a umožňuje odkazujete stylů CSS a elementů HTML pomocí klíčových slov.

Povolit Jade, šablona projektu nejprve zahrnuje pyjade balíček v `requirements.txt`. 

Aplikace `__init__.py` soubor obsahuje řádek do

    ```python
    app.jinja_env.add_extension('pyjade.ext.jinja.PyJadeExtension')
    ```
V `templates` složky, uvidíte `.jade` soubory místo `.html` šablony a zobrazení `views.py` odkazují na tyto soubory v jejich volání `flask.render_template`. Zobrazení kódu v opačném případě je stejný.

Otevření jedné ze `.jade` soubory, zobrazí se více stručného výraz šablony. Zde je obsah například `templates/layout.jade` při vytváření šablony "Webový projekt Flask/Jade":

    ```jade
    doctype html
    html
      head
        meta(charset='utf-8')
        meta(name='viewport', content='width=device-width, initial-scale=1.0')
        title #{title} - My Flask/Jade Application
        link(rel='stylesheet', type='text/css', href='/static/content/bootstrap.min.css')
        link(rel='stylesheet', type='text/css', href='/static/content/site.css')
        script(src='/static/scripts/modernizr-2.6.2.js')
      body
        .navbar.navbar-inverse.navbar-fixed-top
          .container
            .navbar-header
              button.navbar-toggle(type='button', data-toggle='collapse', data-target='.navbar-collapse')
                span.icon-bar
                span.icon-bar
                span.icon-bar
              a.navbar-brand(href='/') Application name
            .navbar-collapse.collapse
              ul.nav.navbar-nav
                li
                  a(href='/') Home
                li
                  a(href='/about') About
                li
                  a(href='/contact') Contact
        .container.body-content
          block content
          hr
          footer
            p &copy; #{year} - My Flask/Jade Application

        script(src='/static/scripts/jquery-1.10.2.js')
        script(src='/static/scripts/bootstrap.js')
        script(src='/static/scripts/respond.js')

        block scripts
    ```

A tady je obsah `templates/about.jade`, znázorňujícího používání `#{ <name>}` pro zástupné symboly:

    ```jade
    extends layout

    block content
      h2 #{title}.
      h3 #{message}
      p Use this area to provide additional information.
    ```

Nebojte se, že experimentovat s Jinja a Jade syntaxe v tématu, které z nich vám nejvíce vyhovuje.

## <a name="next-steps"></a>Další kroky

> [!div class="nextstepaction"]
> [Šablona webový projekt Flask hlasování](learn-flask-visual-studio-step-05-polls-flask-web-project-template.md)

## <a name="go-deeper"></a>Přejděte hlubší

- [Zápis první aplikace Flask, část 4 - formulářů a obecného zobrazení](https://docs.djangoproject.com/en/2.0/intro/tutorial04/) (docs.djangoproject.com)
- [Jade na GitHib (dokumentace)](https://github.com/liuliqiang/pyjade) (webu github.com)
- Kurz zdrojového kódu na Githubu: [Microsoft nebo python – ukázka vs-learning-flask](https://github.com/Microsoft/python-sample-vs-learning-flask)