---
title: Kurz – další Flask v sadě Visual Studio, krok 2
description: Návod Flask základy v kontextu projektů sady Visual Studio, konkrétně postup vytvoření aplikace a pomocí zobrazení a šablony.
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
ms.openlocfilehash: 907b20d3665a84f764619dc40a906b1d4096fd04
ms.sourcegitcommit: 4e605891d0dfb3ab83150c17c074bb98dba29d15
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/26/2018
ms.locfileid: "36946840"
---
# <a name="step-2-create-a-flask-app-with-views-and-page-templates"></a>Krok 2: Vytvoření aplikace Flask s zobrazení a šablony stránky

**Předchozí krok: [vytvoření projektu Visual Studia a řešení](learn-flask-visual-studio-step-01-project-solution.md)**

Máte z kroku 1 tohoto kurzu je aplikace Flask s jednu stránku a všechny kód do jednoho souboru. Povolit pro budoucí vývoj, je nejlepší Refaktorovat kód a vytvořit strukturu pro šablony stránek. Zejména budete chtít oddělit kód pro zobrazení aplikace z další aspekty jako spouštěcí kód.

V tomto kroku teď zjistíte, jak:

> [!div class="checklist"]
> - Refaktorovat kódu aplikace k oddělení zobrazení z spuštění kódu (krok 2 - 1)
> - Vykreslení zobrazení pomocí šablony stránky (krok 2-2)

## <a name="step-2-1-refactor-the-project-to-support-further-development"></a>Krok 2 – 1: Refaktorovat projektu pro podporu další vývoj

V kódu vytvořených šablonou "Prázdný webový projekt Flask", máte jediný `app.py` soubor, který obsahuje kód pro spuštění vedle jednoduchého zobrazení. Povolit pro další vývoj aplikace s více zobrazení a šablony, je nejvhodnější oddělit tyto problémy.

1. Ve složce projektu, vytvořte složku aplikaci s názvem `HelloFlask` (klikněte pravým tlačítkem na projekt v **Průzkumníku řešení** a vyberte **přidat** > **novou složku** .)

1. V `HelloFlask` složky, vytvořte soubor s názvem `__init.py__` s tímto obsahem, které vytvoří `Flask` instance a načte zobrazení aplikace (vytvořený v dalším kroku):

    ```python
    from flask import Flask
    app = Flask(__name__)

    import HelloFlask.views
    ```

1. V `HelloFlask` složky, vytvořte soubor s názvem `views.py` s tímto obsahem. Název `views.py` je důležité, protože jste použili `import HelloFlask.views` v rámci `__init__.py`; uvidíte chybu v době běhu Pokud se názvy neshodují.

    ```python
    from flask import Flask
    from HelloFlask import app

    @app.route('/')
    @app.route('/home')
    def home():
        return "Hello Flask!"
    ```

    Kromě přejmenování funkce a trasy, která má `home`, tento kód obsahuje kód vykreslování stránky z app.py a naimportuje `app` objekt, který je deklarován v `__init__.py`.

1. Vytvořit podsložku v `HelloFlask` s názvem `templates`, který zůstane prázdný nyní.

1. V kořenové složce projektu přejmenovat `app.py` k `runserver.py`a ujistěte se, obsah shodovat s následujícím kódem:

    ```python
    import os
    from HelloFlask import app    # Imports the code from HelloFlask/__init__.py

    if __name__ == '__main__':
        HOST = os.environ.get('SERVER_HOST', 'localhost')

        try:
            PORT = int(os.environ.get('SERVER_PORT', '5555'))
        except ValueError:
            PORT = 5555

        app.run(HOST, PORT)
    ```
1. Strukturu projekt by měl vypadat podobně jako na následujícím obrázku:

    ![Struktura projektu po refaktoring kódu](media/flask/step02-project-structure.png)

1. Vyberte **ladění** > **spustit ladění** (F5) nebo použít **Webový Server** tlačítka na panelu nástrojů (prohlížeč, najdete v části mohou lišit) otevřete prohlížeč a aplikaci spusťte. Zkuste i nebo a/home tras adresy URL.

1. Můžete také nastavit zarážky v různých částí kódu a restartujte aplikaci rozhodování o pořadí spouštění. Například nastavit zarážky první řádky `runserver.py` a `HelloFlask\__init__.py`a na `return "Hello Flask!"` řádek v `views.py`. Potom restartujte aplikaci (**ladění** > **restartujte**, Ctrl + F5 nebo tlačítka panelu nástrojů, viz následující obrázek) a projděte (F10) kód, nebo ji spustit z každé zarážky pomocí F5.

    ![Restartujte na ladění nástrojů v sadě Visual Studio](media/debugging-restart-toolbar-button.png)

1. Zastavte aplikaci, když jste hotovi.

### <a name="commit-to-source-control"></a>Zapsat do správy zdrojového kódu

Protože jste udělali změny kódu a jejich otestovali úspěšně, teď je nejvhodnější doba ke kontrole a uložte provedené změny do správy zdrojového kódu. Pozdější kroky v tomto kurzu vám připomene příslušná doba potvrzení znovu do správy zdrojového kódu a odkazovat zpět do této části.

1. Kliknutím na tlačítko změny ve spodní části Visual Studio (v kroužku níže), která přejde na **Team Explorer**.

    ![Tlačítko změny zdroj ovládacího prvku na stavovém řádku Visual Studio](media/flask/step02-source-control-changes-button.png)

1. V **Team Explorer**, zadejte zprávu o potvrzení jako "Kód Refaktorovat" a vyberte **potvrzení všechny**. Po dokončení potvrzení se zobrazí zpráva "potvrzení <hash> vytvoří místně. Synchronizace sdílet vaše změny se serverem." Pokud chcete doručte změny do vzdáleného úložiště, vyberte **synchronizace**, pak vyberte **nabízené** pod **odchozí potvrzení**. Můžete také obdržíte více místní potvrzení před odesláním vzdálené.

    ![Nabízená vzdálené v Team Exploreru potvrzení](media/flask/step02-source-control-push-to-remote.png)

### <a name="question-how-frequently-should-one-commit-to-source-control"></a>Otázka: jak často má jeden potvrzení do správy zdrojového kódu?

Odpověď: potvrzení změn do správy zdrojového kódu vytvoří záznam v protokolu změn a bod na které můžete obnovit úložiště v případě potřeby. Každý potvrzení můžete také ověřuje její konkrétní změny. Vzhledem k potvrzení v Git jsou nenákladné, je lepší často potvrzení, než se hromadit větší počet změn v jediné potvrzení. Je zřejmé nemusíte potvrdit každé změně malá pro jednotlivé soubory. Obvykle je nutné provést potvrzení změn při přidávání funkci Změna struktury, jako jste v tomto kroku nebo provést některé refaktoring kódu. Také zkontrolujte s jinými uživateli ve vašem týmu pro členitost potvrzení, které nejlépe vyhovuje všem uživatelům.

Jak často potvrzení a jak často push potvrzení do vzdáleného úložiště jsou dvě různá rizika. Před jejich odesláním do vzdáleného úložiště může shromažďovat více potvrzení v místním úložišti. Jak často potvrzení znovu, závisí na tom, jak váš tým chce spravovat úložiště.

## <a name="step-2-2-use-a-template-to-render-a-page"></a>Krok 2 – 2: použijte šablonu k vykreslení stránky

`home` Funkce, která máte, pokud v `views.py` nic jiného než prostého textu odpovědi HTTP pro stránku generuje. Většina reálného webové stránky, ale odpovědět s bohaté stránky HTML, které jsou často dynamická data. Hlavním důvodem k definování zobrazení pomocí funkce je ve skutečnosti dynamicky generovat obsah.

Protože návratovou hodnotu pro zobrazení pouze řetězec, můžete vytvořit až všechny HTML, který chcete v rámci řetězce, pomocí dynamický obsah. Protože je nejlepší kód oddělit od data, je však mnohem lepší umístit značku do šablony a ponechat data v kódu.

1. Pro začátek upravit `views.py` tak, aby obsahovala následující kód, který používá vložený HTML stránky s některé dynamický obsah:

    ```python
    from datetime import datetime
    from flask import render_template
    from HelloFlask import app

    @app.route('/')
    @app.route('/home')
    def home():
        now = datetime.now()
        formatted_now = now.strftime("%A, %d %B, %Y at %X")

        html_content = "<html><head><title>Hello Flask</title></head><body>"
        html_content += "<strong>Hello Flask!</strong> on " + formatted_now
        html_content += "</body></html>"

        return html_content
    ```

1. Spusťte aplikaci a aktualizujte stránku několikrát zobrazíte, že se aktualizuje datum a čas. Zastavte aplikaci, když jste hotovi.

1. Převést vykreslování stránky pro použití šablony, vytvořte soubor s názvem `index.html` v `templates` složku s následujícím obsahem, kde `{{ content }}` je zástupný symbol nebo nahrazení tokenu (také nazývané *proměnná šablony*) pro kterou je zadat hodnotu v kódu:

    ```html
    <html>
        <head><title>Hello Flask</title></head>

        <body>
            {{ content }}
        </body>
    </html>
    ```

1. Změnit `home` funkce použité `render_template` načtení šablony a zadat hodnotu "obsah", která se provádí pomocí pojmenovaného argumentu odpovídající názvu zástupného textu. Flask automaticky vyhledá šablony v `templates` složku, takže oath v šabloně je relativní vzhledem k této složce:

    ```python
    def home():
        now = datetime.now()
        formatted_now = now.strftime("%A, %d %B, %Y at %X")

        return render_template(
            "index.html",
            content = "<strong>Hello, Flask!</strong> on " + formatted_now)
    ```

1. Spusťte aplikaci najdete v tématu výsledky a že vložený HTML v `content` není vykreslit hodnotu *jako* HTML vzhledem k tomu ukázka modul (Jinja) automaticky řídicí sekvence obsah HTML. Automatické uvozovací znaky zabránit náhodnému ohrožení zabezpečení prostřednictvím injektáže: vývojáři často shromažďovat vstup z jedné stránky a použít jako hodnotu v jiném prostřednictvím zástupný text šablony. Uvozovací znaky slouží také jako připomenutí, že je znovu nejlepší mít mimo kód HTML.

    Podle toho, zkontrolujte `templates\index.html` tak, aby obsahovala odlišné zástupné symboly pro každou část dat v rámci kód:

    ```html
    <html>
        <head>
            <title>{{ title }}</title>
        </head>
        <body>
            <strong>{{ message }}</strong>{{ content }}
        </body>
    </html>
    ```

    Aktualizujte `home` funkce zadat hodnoty pro všechny zástupné symboly:

    ```python
    def home():
        now = datetime.now()
        formatted_now = now.strftime("%A, %d %B, %Y at %X")

        return render_template(
            "index.html",
            title = "Hello Flask",
            message = "Hello, Flask!",
            content = " on " + formatted_now)
    ```

1. Spusťte aplikaci znovu zobrazovat správně Vykreslený výstup.

    ![Spuštěné aplikaci pomocí šablony](media/flask/step02-result.png)

1. Potvrdit změny pro zdroj ovládacího prvku a aktualizujte vzdálené úložiště, v případě potřeby, jak je popsáno v části [kroku 2-1](#commit-to-source-control).

### <a name="question-do-page-templates-have-to-be-in-a-separate-file"></a>Otázka: stránky šablony musí být v samostatném souboru?

Odpověď: I když šablony jsou obvykle zachován v samostatné soubory HTML, můžete taky šablonu vložené. Použít samostatné soubory se doporučuje, ale k udržování čisté oddělení mezi značek a kódu.

### <a name="question-must-templates-use-the-html-file-extension"></a>Otázka: musí být šablony používat příponu souboru .html?

Odpověď: `.html` přípony souborů, šablona stránky je zcela volitelný, protože je vždy určit přesnou relativní cestu k souboru v první argument `render_template` funkce. Však Visual Studio (a dalšími editory) obvykle poskytují funkce, například kód dokončení a syntaxe zabarvení s `.html` soubory, které převáží skutečnost, že stránka šablony nejsou nezbytně HTML.

Ve skutečnosti při práci s projektem Django, Visual Studio automaticky rozpozná, pokud je ve skutečnosti šablonu Django soubor HTML, který upravujete a poskytuje určité funkce automatického dokončování. Například když začnete psát komentář šablony stránky Django, `{#`, Visual Studio automaticky vám dává ukončovací `#}` znaků. **Výběru jako komentáře** a **zrušte komentář u výběru** příkazy (na **upravit** > **Upřesnit** nabídky a na panelu nástrojů) komentáře k šabloně používají taky místo komentáře HTML.

### <a name="question-when-i-run-the-project-i-see-an-error-that-the-template-cannot-be-found-whats-wrong"></a>Otázka: Při spuštění projektu, zobrazuje chybu, která šablona nebyla nalezena. Co je?

Odpověď: Pokud se zobrazí chyby, které nelze nalézt šablonu, ujistěte se, přidání aplikace do projektu Django `settings.py` v `INSTALLED_APPS` seznamu. Bez této položky Django Nepozná k prohledání aplikace `templates` složky.

### <a name="question-can-templates-be-organized-into-further-subfolders"></a>Otázka: můžete šablony uspořádat do další podsložky?

Odpověď: Ano, můžete použít podsložky a potom se podívejte na relativní cestu v části `templates` ve voláních `render_template`. Díky tomu je skvělým způsobem, jak efektivně vytváření oborů názvů pro vaše šablony.

## <a name="next-steps"></a>Další kroky

> [!div class="nextstepaction"]
> [Statické soubory, přidat stránky a používat šablonu dědičnosti](learn-flask-visual-studio-step-03-serve-static-files-add-pages.md)

## <a name="go-deeper"></a>Přejděte hlubší

- [Rychlý start flask - vykreslování šablony](http://flask.pocoo.org/docs/1.0/quickstart/#rendering-templates) (flask.pocoo.org)
- Kurz zdrojového kódu na Githubu: [Microsoft nebo python – ukázka vs-learning-flask](https://github.com/Microsoft/python-sample-vs-learning-flask)