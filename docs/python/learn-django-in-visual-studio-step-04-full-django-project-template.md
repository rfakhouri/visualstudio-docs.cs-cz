---
title: Kurz – další Django v sadě Visual Studio, krok 4
description: Návod základní informace o rozhraní Django v kontextu projektů sady Visual Studio, konkrétně funkcí šablonou webový projekt Django.
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
ms.openlocfilehash: 9d48c8f86d29c990d254b2ed1d0adf471c24d6b8
ms.sourcegitcommit: 928885ace538bef5b25961358d4f166d648f196a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/27/2018
---
# <a name="tutorial-step-4-use-the-full-django-web-project-template"></a>Kurz – krok 4: použití kompletní šablonou webový projekt Django

**Předchozí krok: [obsluhovat statické soubory, přidat stránky a použití šablony dědičnosti](learn-django-in-visual-studio-step-03-serve-static-files-and-add-pages.md)**

Teď, když jste prozkoumali základní informace o rozhraní Django podle budovy aplikace na šabloně "Prázdný projekt Django aplikace" v sadě Visual Studio, můžete snadno pochopit úplnější aplikaci, která je produkovaný šabloně "Webový projekt Django".

V tomto kroku můžete nyní:

> [!div class="checklist"]
> - Vytvoření úplnější webové aplikace Django pomocí šablony "Webový projekt Django" a zkontrolujte strukturu projektu (krok 4 - 1)
> - Rady pro pochopení zobrazení a šablony stránek vytvořených šablonou projektu, které se skládají z tři stránky, které dědí ze šablony základní stránky a který využívá statické knihovny JavaScript jako jQuery a Bootstrap (krok 4-2)
> - Pochopení směrování adres URL poskytuje šablony (krok 4-3)

Šablona taky poskytuje základní ověřování, které je popsané v kroku 5.

## <a name="step-4-1-create-a-project-from-the-template"></a>Krok 4-1: Vytvořte projekt ze šablony

1. V sadě Visual Studio, přejděte na **Průzkumníku řešení**, klikněte pravým tlačítkem na řešení "LearningDjango" v tomto kurzu vytvořili a vyberte **přidat** > **nový projekt**. (Případně, pokud chcete používat nové řešení, vyberte **soubor** > **nový** > **projektu** místo.)

1. V dialogovém okně Nový projekt, vyhledejte a vyberte šablonu, "Webový projekt Django", volání "DjangoWeb" projekt a vyberte **OK**.

1. Protože znovu obsahuje šablony `requirements.txt` souboru, Visual Studio zobrazí dotaz, kam se má nainstalovat tyto závislosti. Zvolte možnost **nainstalovat do virtuálního prostředí**a v **Přidání virtuálního prostředí** dialogovém okně vyberte **vytvořit** přijměte výchozí hodnoty.

1. Po dokončení nastavení virtuální prostředí Python, postupujte podle pokynů v zobrazené `readme.html` vytvoření superuživatele uživatele Django (který je správcem). Právě klikněte pravým tlačítkem na projekt Visual Studio a vyberte **Python** > **vytvoření superuživatele Django** příkaz a potom postupujte podle pokynů. Ujistěte se, že záznam uživatelského jména a hesla při používání při výkonu funkce ověřování aplikace.

1. Nastavte projekt "DjangoWeb", který má být výchozí nastavení pro řešení sady Visual Studio tak, že kliknete pravým tlačítkem na takový projekt v **Průzkumníku řešení** a výběrem **nastavit jako spouštěný projekt**. Spouštěný projekt, který se zobrazí v tučné písmo, je co běží při spuštění ladicího programu.

    ![Průzkumník řešení zobrazující DjangoWeb projekt jako spouštěný projekt](media/django/step04-second-project-in-solution-set-as-startup-project.png)

1. Vyberte **ladění** > **spustit ladění** (F5) nebo pomocí **Webový Server** tlačítka na panelu nástrojů ke spuštění serveru:

    ![Spustit webový server tlačítka panelu nástrojů v sadě Visual Studio](media/django/run-web-server-toolbar-button.png)

1. Aplikace vytvořené pomocí šablony má tři stránky, domů, o a kontaktovat, což je přecházet mezi pomocí navigačního panelu. Trvat minutu nebo dvě prozkoumat různých částí aplikace. K ověřování pro aplikaci prostřednictvím **přihlásit** příkazu, použijte přihlašovací údaje superuživatel vytvořili dříve.

    ![Zobrazit v prohlížeči úplné aplikace webový projekt Django](media/django/step04-full-app-desktop-view.png)

1. Aplikace vytvořené pomocí šablony "Webový projekt Django" využívá Bootstrap přizpůsobivé rozložení, která bude vyhovovat typy mobilních zařízení. Pokud chcete zobrazit tento odezvy velikosti prohlížeče úzké zobrazení tak, aby obsah vykreslí svisle a navigačního panelu se zobrazí ikona nabídky:

    ![Zobrazení (úzké) mobilní aplikace pro webový projekt Django](media/django/step04-full-app-mobile-view.png)

1. Můžete nechat aplikaci spuštěnou pro oddíly, které následují.

    Pokud budete chtít aplikaci zastavit a [potvrzení změn do správy zdrojového kódu](learn-django-in-visual-studio-step-02-create-an-app.md#commit-to-source-control), poprvé otevřete **změny** stránky v **Team Explorer**, klikněte pravým tlačítkem na složku (virtuálního prostředí pravděpodobně `env`) a vyberte **ignorovat tyto místní položky**.

### <a name="examine-what-the-template-creates"></a>Zkontrolujte, vytvoří šablona

Na úrovni nejširší vytvoří šablona "Webový projekt Django" následující strukturu:

- Soubory v kořenu projektu:
  - `manage.py`, nástroj pro správu Django.
  - `db.sqlite3`, výchozí databáze SQLite.
  - `requirements.txt` obsahující závislost na Django 1.x.
  - `readme.html`, soubor, který se zobrazí v sadě Visual Studio po vytvoření projektu. Jak je uvedeno v předchozí části, postupujte podle pokynů tady k vytvoření účtu superuživatele (správce) pro aplikaci.
- `app` Složka obsahuje všechny soubory aplikace, včetně zobrazení, modely, testů, formulářů, šablony a statické soubory (viz krok 4-2). Obvykle přejmenujete tuto složku a použít více rozlišovací název aplikace.
- `DjangoWeb` (Projekt Django) složka obsahuje typické soubory projekt Django: `__init.py__`, `settings.py`, `urls.py`, a `wsgi.py`. Pomocí šablony projektu, `settings.py` už je nakonfigurovaný pro aplikaci a databázový soubor, a `urls.py` už nakonfigurované trasy pro všechny aplikace stránky, včetně přihlašovací formulář.

### <a name="question-is-it-possible-to-share-a-virtual-environment-between-visual-studio-projects"></a>Otázka: Je možné sdílet mezi projektů sady Visual Studio virtuálního prostředí?

Odpověď: Ano, ale učinit povědomí o různé projekty, které mohou používat různé balíčky v čase, a proto sdílené virtuální prostředí musí obsahovat všechny balíčky pro všechny projekty, které ho používají.

Nicméně pokud chcete použít existující virtuální prostředí, postupujte takto:

1. Po zobrazení výzvy k instalaci závislosti v sadě Visual Studio, vyberte **I je nainstaluje sám** možnost.
1. V **Průzkumníku řešení**, klikněte pravým tlačítkem myši **prostředí Python** uzel a vyberte možnost **přidat existující virtuální prostředí**.
1. Přejděte do a vyberte složku, která obsahuje virtuální prostředí a potom vyberte **OK**.

## <a name="step-4-2-understand-the-views-and-page-templates-created-by-the-project-template"></a>Krok 4-2: pochopení zobrazení a stránka šablony vytvořené v šabloně projektů

Jak zjistíte při spuštění projektu, aplikace obsahuje tři zobrazení: Domů, o a obraťte se na. Kód pro tato zobrazení je nalezena v `app/views` složky. Jednotlivé funkce zobrazení jednoduše volá `django.shortcuts.render` cestou k šablonu a objekt jednoduché slovníku. Například stránku o jsou zpracována `about` funkce:

```python
def about(request):
    """Renders the about page."""
    assert isinstance(request, HttpRequest)
    return render(
        request,
        'app/about.html',
        {
            'title':'About',
            'message':'Your application description page.',
            'year':datetime.now().year,
        }
    )
```

Šablony jsou umístěny v dané aplikaci `templates/app` složky (a obvykle budete chtít přejmenovat `app` k názvu skutečné aplikace). Základní šablony `layout.html`, je většina rozsáhlé. Ji označuje všechny potřebné statické soubory (JavaScript a CSS), definuje blok s názvem "obsah" jiných stránky přepsání a poskytuje další blok s názvem "skripty". Následující poznámky úryvky z `layout.html` zobrazit tyto konkrétní oblasti:

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8" />

    <!-- Define a viewport for Bootstrap's responsive rendering -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>{{ title }} - My Django Application</title>

    {% load staticfiles %}
    <link rel="stylesheet" type="text/css" href="{% static 'app/content/bootstrap.min.css' %}" />
    <link rel="stylesheet" type="text/css" href="{% static 'app/content/site.css' %}" />
    <script src="{% static 'app/scripts/modernizr-2.6.2.js' %}"></script>
</head>
<body>
    <!-- Navbar omitted -->

    <div class="container body-content">

<!-- "content" block that pages are expected to override -->
{% block content %}{% endblock %}
        <hr/>
        <footer>
            <p>&copy; {{ year }} - My Django Application</p>
        </footer>
    </div>

<!-- Additional scripts; use the "scripts" block to add page-specific scripts.  -->
    <script src="{% static 'app/scripts/jquery-1.10.2.js' %}"></script>
    <script src="{% static 'app/scripts/bootstrap.js' %}"></script>
    <script src="{% static 'app/scripts/respond.js' %}"></script>
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

V `templates/app` složka je také čtvrté stránce `login.html`, spolu s `loginpartial.html` načtená do `layout.html` pomocí `{% include %}`. Tyto soubory šablony jsou popsané v kroku 5 na ověřování.

### <a name="question-can--block--and--endblock--be-indented-in-the-django-page-template"></a>Otázka: může {% blokovat %} a {% endblock %} odsazeny v šabloně Django stránky?

Odpověď: Ano, rozhraní Django stránky šablony bez problémů fungují Pokud odsazovat bloku značky, případně je uvést do v rámci jejich příslušné nadřazené elementy. Nejsou určeny v šablonách stránky generované v šabloně projektů sady Visual Studio, aby jasně uvidíte, kde jsou umístěny.

## <a name="step-4-3-understand-the-url-routing-created-by-the-template"></a>Krok 4 – 3: pochopení vytvořených šablonou směrování adres URL

Projekt Django `urls.py` soubor při vytváření šablony "Webový projekt Django" obsahuje následující kód:

```python
from datetime import datetime
from django.conf.urls import url
import django.contrib.auth.views

import app.forms
import app.views

urlpatterns = [
    url(r'^$', app.views.home, name='home'),
    url(r'^contact$', app.views.contact, name='contact'),
    url(r'^about$', app.views.about, name='about'),
    url(r'^login/$',
        django.contrib.auth.views.login,
        {
            'template_name': 'app/login.html',
            'authentication_form': app.forms.BootstrapAuthenticationForm,
            'extra_context':
            {
                'title': 'Log in',
                'year': datetime.now().year,
            }
        },
        name='login'),
    url(r'^logout$',
        django.contrib.auth.views.logout,
        {
            'next_page': '/',
        },
        name='logout'),
]
```

První tři vzory adresy URL přímo na mapování `home`, `contact`, a `about` zobrazení v dané aplikaci `views.py` souboru. Vzory `^login/$` a `^logout$`, na dalším ruční, použít předdefinovaná zobrazení Django místo zobrazení definované aplikací. Volání `url` metoda také zahrnovat doplňujících dat. Chcete-li přizpůsobit zobrazení. Krok 5 prozkoumá těchto volání.

### <a name="question-in-the-project-i-created-why-does-the-about-url-pattern-uses-about-instead-of-about-as-shown-here"></a>Otázka: v projektu vytvořený, proč "about" vzor adresy URL používá ' ^ o se místo ' ^ o$, jak je vidět tady?

Odpověď: Chybí koncové "$" v regulárním výrazu byl jednoduché dohledu v mnoha verzí šablona projektu. Vzor adresy URL funguje bez jakýchkoli problémů pro stránku s názvem "o", ale bez koncové $ vzor adresy URL také odpovídající adresy URL jako "o = django", "about09876", "aboutoflaughter" a tak na. Koncové $ se zobrazí tady vytvořit vzor adresy URL, která odpovídá *pouze* "o".

## <a name="next-steps"></a>Další kroky

> [!div class="nextstepaction"]
> [Ověřování uživatelů v Django](learn-django-in-visual-studio-step-05-django-authentication.md)

## <a name="going-deeper"></a>Budete hlubší

- [Zápis první aplikace Django, část 4 - formulářů a obecného zobrazení](https://docs.djangoproject.com/en/2.0/intro/tutorial04/) (docs.djangoproject.com)
- Kurz zdrojového kódu na Githubu: [Microsoft nebo python – ukázka vs další django](https://github.com/Microsoft/python-sample-vs-learn-django)