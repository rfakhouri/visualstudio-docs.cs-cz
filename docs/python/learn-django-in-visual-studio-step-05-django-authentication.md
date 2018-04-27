---
title: Kurz – další Django v sadě Visual Studio, krok 5
description: Návod základní informace o rozhraní Django v kontextu projektů sady Visual Studio, konkrétně funkce ověřování podle šablony webový projekt Django.
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
ms.openlocfilehash: 87d123e4da3d27d9b8c3ac1db5c3d02fe4b5ac44
ms.sourcegitcommit: 928885ace538bef5b25961358d4f166d648f196a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/27/2018
---
# <a name="tutorial-step-5-authenticate-users-in-django"></a>Kurz – krok 5: ověření uživatele v Django

**Předchozí krok: [použít úplnou šablonu webový projekt Django](learn-django-in-visual-studio-step-04-full-django-project-template.md)**

Protože ověřování je potřebují společné pro webové aplikace, šablona "Webový projekt Django" obsahuje toku základní ověřování. ("Hlasovací webový projekt Django" šablony popsané v kroku 6 tohoto kurzu také zahrnuje stejného toku.) Pokud používáte některou z šablon projektu Django, sada Visual Studio obsahuje všechny moduly, které jsou nezbytné pro ověřování v projektu Django `settings.py`.

V tomto kroku dozvíte:

> [!div class="checklist"]
> - Jak používat tok ověřování, které jsou součástí šablony sady Visual Studio (krok 5 - 1)

## <a name="step-5-1-use-the-authentication-flow"></a>Krok 5 – 1: použití toku ověřování

Následující kroky postupu tok ověřování a popisují části projektu, které se podílejí:

1. Pokud jste ještě již postupovali podle pokynů v `readme.html` soubor v kořenu projektu pro vytvoření účtu superuživatele (správce), udělejte to teď.

1. Spusťte aplikaci pomocí sady Visual Studio **ladění** > **spustit ladění** (F5). Když se aplikace zobrazí v prohlížeči, sledovat **přihlásit** se zobrazí v pravém horním rohu stránky navigačního panelu.

    ![Ovládací prvek přihlášení na stránce aplikace webový projekt Django](media/django/step05-login-control.png)

1. Otevřete `templates/app/layout.html` a zjistěte, který `<div class="navbar ...>` element obsahuje značky `{% include app/loginpartial.html %}`. `{% include %}` Dá Django je ukázka systému stáhnout obsah souboru zahrnuté v tomto okamžiku v šabloně obsahující pokyn značky.

1. Otevřete `templates/app/loginpartial.html` a zjistěte, jak používá podmíněného značky `{% if user.is_authenticated %}` spolu s `{% else %}` značky k vykreslení různé prvky uživatelského rozhraní v závislosti na tom, zda byl uživatel ověřen:

    ```html
    {% if user.is_authenticated %}
    <form id="logoutForm" action="/logout" method="post" class="navbar-right">
        {% csrf_token %}
        <ul class="nav navbar-nav navbar-right">
            <li><span class="navbar-brand">Hello {{ user.username }}!</span></li>
            <li><a href="javascript:document.getElementById('logoutForm').submit()">Log off</a></li>
        </ul>
    </form>

    {% else %}

    <ul class="nav navbar-nav navbar-right">
        <li><a href="{% url 'login' %}">Log in</a></li>
    </ul>

    {% endif %}
    ```

1. Vzhledem k tomu, že žádný uživatel ověřen při prvním spuštění aplikace, tento kód šablony vykreslí pouze "Přihlášení" odkaz na relativní cestou "přihlášení". Jak je uvedeno v `urls.py` znázorněné v předchozí části tohoto postupu je namapována na `django.contrib.auth.views.login` zobrazení, který je uveden následující data:

    ```python
    {
        'template_name': 'app/login.html',
        'authentication_form': app.forms.BootstrapAuthenticationForm,
        'extra_context':
        {
            'title': 'Log in',
            'year': datetime.now().year,
        }
    }
    ```

    Zde `template_name` identifikuje šablonu pro přihlašovací stránku, v takovém případě `templates/app/login.html`. `extra_context` Vlastnost je přidána dat výchozí kontext zadané v šabloně. Nakonec `authentication_form` Určuje třídu s formuláře pro použití s přihlášení se v šabloně se jeví jako `form` objektu. Výchozí hodnota je `AuthenticationForm` (z `django.contrib.auth.views`); v šabloně projektů sady Visual Studio místo toho používá formuláře definované v dané aplikaci `forms.py` souboru:

    ```python
    from django import forms
    from django.contrib.auth.forms import AuthenticationForm
    from django.utils.translation import ugettext_lazy as _

    class BootstrapAuthenticationForm(AuthenticationForm):
        """Authentication form which uses boostrap CSS."""
        username = forms.CharField(max_length=254,
                                   widget=forms.TextInput({
                                       'class': 'form-control',
                                       'placeholder': 'User name'}))
        password = forms.CharField(label=_("Password"),
                                   widget=forms.PasswordInput({
                                       'class': 'form-control',
                                       'placeholder':'Password'}))
    ```

    Jak vidíte, tato třída tvaru odvozená z `AuthenticationForm` a konkrétně přepsání pole uživatelské jméno a heslo pro přidání zástupný text. Šablony sady Visual Studio obsahuje tento explicitní kód za předpokladu, že budete pravděpodobně chtít přizpůsobení formuláře, jako je například přidávání ověření síly hesla.

1. Když přejdete na stránku přihlášení pak vykreslí aplikace `login.html` šablony. Proměnné `{{ form.username }}` a `{{ form.password }}` vykreslení `CharField` forms z `BootstrapAuthenticationForm`. Je také předdefinované části zobrazíte chyby ověření a element připravenou pro sociálních přihlášení, pokud zvolíte možnost Přidat těchto služeb.

    ```html
    {% extends "app/layout.html" %}

    {% block content %}

    <h2>{{ title }}</h2>
    <div class="row">
        <div class="col-md-8">
            <section id="loginForm">
                <form action="." method="post" class="form-horizontal">
                    {% csrf_token %}
                    <h4>Use a local account to log in.</h4>
                    <hr />
                    <div class="form-group">
                        <label for="id_username" class="col-md-2 control-label">User name</label>
                        <div class="col-md-10">
                            {{ form.username }}
                        </div>
                    </div>
                    <div class="form-group">
                        <label for="id_password" class="col-md-2 control-label">Password</label>
                        <div class="col-md-10">
                            {{ form.password }}
                        </div>
                    </div>
                    <div class="form-group">
                        <div class="col-md-offset-2 col-md-10">
                            <input type="hidden" name="next" value="/" />
                            <input type="submit" value="Log in" class="btn btn-default" />
                        </div>
                    </div>
                    {% if form.errors %}
                    <p class="validation-summary-errors">Please enter a correct user name and password.</p>
                    {% endif %}
                </form>
            </section>
        </div>
        <div class="col-md-4">
            <section id="socialLoginForm"></section>
        </div>
    </div>

    {% endblock %}
    ```

1. Při odesílání formuláře Django pokus o ověření přihlašovacích údajů, které poskytnete (například přihlašovací údaje super uživatele). Pokud se ověření nezdaří, zůstanete na stejné stránce, ale `form.errors` nastaven na hodnotu true. Pokud je ověření úspěšné, Django přejde na relativní adresu URL do pole "Další" `<input type="hidden" name="next" value="/" />`, který v tomto případě je domovská stránka (`/`).

1. Teď, když na domovskou stránku vykreslením znovu, `user.is_authenticated` vlastnost má hodnotu true, pokud `loginpartial.html` šablony je vykreslen. V důsledku toho zobrazí zpráva "Hello (username)" a "Odhlásit". Můžete použít `user.is_authenticated` v dalších částech tohoto aplikaci kontrolovat ověřování.

    ![Hello zprávu a odhlášení řízení na stránce aplikace webový projekt Django](media/django/step05-logoff-control.png)

1. Pokud chcete zkontrolovat, zda je ověřený uživatel oprávnění pro přístup k určitým prostředkům, budete potřebovat pro načtení uživatelská oprávnění v databázi pro daného uživatele. Další podrobnosti najdete v tématu [pomocí ověřování systému Django](https://docs.djangoproject.com/en/2.0/topics/auth/default/#permissions-and-authorization) (Django dokumentace).

1. Superuživatele nebo správce, zejména, má oprávnění k přístupu integrované rozhraní správce Django pomocí relativní adresy URL "/admin/" a "/ správce/doc /". Chcete-li tato rozhraní, otevřete projekt Django `urls.py` a odebere komentáře z následující položky:

    ```python
    from django.conf.urls import include
    from django.contrib import admin
    admin.autodiscover()

    # ...
    urlpatterns = [
        # ...
        url(r'^admin/doc/', include('django.contrib.admindocs.urls')),
        url(r'^admin/', include(admin.site.urls)),
    ]
    ```

    Při dalším spuštění aplikace, můžete přejít na "/admin/" a "/ správce/doc /" a provádět úlohy, jako jsou vytvořit další uživatelské účty.

    ![Rozhraní správce Django](media/django/step05-administrator-interface.png)

1. Poslední část s tokem ověřování odhlášení. Jak je vidět v `loginpartial.html`, **Odhlásit** odkaz jednoduše nemá metodu POST SMĚŘUJÍCÍ do relativní adresy URL "/ přihlášení", který zpracovává předdefinovaných zobrazení `django.contrib.auth.views.logout`. Toto zobrazení se nezobrazí žádné uživatelské rozhraní a právě přejde na domovské stránce (jak je znázorněno v `urls.py` pro "^ odhlášení$" vzor). Pokud chcete zobrazit stránku odhlášení, nejprve změňte vzor adresy URL takto k přidání "template_name" vlastnosti a odeberte vlastnost "next_page":

    ```python
    url(r'^logout$',
        django.contrib.auth.views.logout,
        {
            'template_name': 'app/loggedoff.html',
            # 'next_page': '/',
        },
        name='logout')
    ```

    Pak vytvořte `templates/app/loggedoff.html` s tímto obsahem (minimální):

    ```html
    {% extends "app/layout.html" %}
    {% block content %}
    <h3>You have been logged off</h3>
    {% endblock %}
    ```

    Výsledek vypadá takto:

    ![Přidat odhlášením stránky](media/django/step05-logged-off-page.png)

1. Když jste všechny hotovi, stop pro server a znovu potvrďte změny do správy zdrojového kódu.

### <a name="question-what-is-the-purpose-of-the--crsftoken--tag-that-appears-in-the-form-elements"></a>Otázka: co je účelem {% crsf_token %} značek, které se zobrazí v \<formuláře\> elementy?

Odpověď: `{% crsf_token %}` značka zahrnuje integrovanou na Django [webů požadavek padělání (crsf) ochrany](https://docs.djangoproject.com/en/2.0/ref/csrf/) (Django dokumentace). Obvykle přidat tuto značku pro libovolný element, který zahrnuje POST, PUT a DELETE požadavek metody, jako jsou formuláře a vykreslování funkce šablony (`render`) vloží nezbytné ochrany.

## <a name="next-steps"></a>Další kroky

> [!div class="nextstepaction"]
> [Použít šablonu hlasovací webový projekt Django](learn-django-in-visual-studio-step-06-polls-django-web-project-template.md)

## <a name="going-deeper"></a>Budete hlubší

- [Ověření uživatele v Django](https://docs.djangoproject.com/en/2.0/topics/auth/) (docs.djangoproject.com)
- Kurz zdrojového kódu na Githubu: [Microsoft nebo python – ukázka vs další django](https://github.com/Microsoft/python-sample-vs-learn-django)