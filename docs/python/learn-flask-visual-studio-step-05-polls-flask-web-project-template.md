---
title: Kurz – další Flask v sadě Visual Studio, krok 5
description: Návod Flask základy v kontextu projektů sady Visual Studio, konkrétně funkce šablon webový projekt Flask hlasování a webový projekt Flask/Jade hlasování.
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
ms.openlocfilehash: 322e0bdc98751cda670206667cc8580bd498f682
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34752500"
---
# <a name="tutorial-step-5-use-the-polls-flask-web-project-template"></a>Kurz – krok 5: použití šablony webový projekt Flask hlasování

**Předchozí krok: [použít úplnou šablonu webový projekt Flask](learn-flask-visual-studio-step-04-full-flask-project-template.md)**

Porozumění "Webový projekt Flask" šablony sady Visual Studio můžete nyní prohlédnout třetí šablony Flask "Hlasovací webový projekt Flask", která staví na stejném základu kódu.

V tomto kroku zjistíte, jak:

> [!div class="checklist"]
> - Vytvoření projektu ze šablony a inicializace databáze (krok 5 - 1)
> - Pochopení datových modelech (krok 5-2)
> - Porozumět zálohování dat úložišť a (krok 5-3)
> - Pochopení dotazování podrobností a výsledky zobrazení (krok 5-4)

Visual Studio také projekty šabloně "Hlasovací webový projekt Flask/Jade", která vytváří stejné aplikaci, ale používá Jade rozšíření pro modul Jinja ukázka. Podrobnosti najdete v tématu [krokem 4 – šablony webový projekt Flask/Jade](learn-flask-visual-studio-step-04-full-flask-project-template.md#the-flaskjade-web-project-template).

## <a name="step-5-1-create-the-project"></a>Krok 5 – 1: vytvoření projektu

1. V sadě Visual Studio, přejděte na **Průzkumníku řešení**, klikněte pravým tlačítkem na řešení "LearningFlask" v tomto kurzu vytvořili a vyberte **přidat** > **nový projekt**. (Případně, pokud chcete používat nové řešení, vyberte **soubor** > **nový** > **projektu** místo.)

1. V dialogovém okně Nový projekt, vyhledejte a vyberte šablonu, "Hlasovací webový projekt Flask", volání "FlaskPolls" projekt a vyberte **OK**.

1. Jako další šablony projektů v sadě Visual Studio "Hlasovací webový projekt Flask" Šablona obsahuje `requirements.txt` souboru výzvy Visual Studio zobrazí dotaz, kde k instalaci těchto závislostí. Zvolte možnost **nainstalovat do virtuálního prostředí**a v **Přidání virtuálního prostředí** dialogovém okně vyberte **vytvořit** přijměte výchozí hodnoty. (Tato šablona vyžaduje Flask, jakož i úložiště azure a pymongo balíčky; "Hlasování Flask/Jade webového projektu" taky požadovat pyjade.)

1. Nastavte projekt "FlaskPolls", který má být výchozí nastavení pro řešení sady Visual Studio tak, že kliknete pravým tlačítkem na takový projekt v **Průzkumníku řešení** a výběrem **nastavit jako spouštěný projekt**. Spouštěný projekt, který se zobrazí v tučné písmo, je co běží při spuštění ladicího programu.

1. Vyberte **ladění > Spustit ladění** (F5) nebo pomocí **Webový Server** tlačítka na panelu nástrojů ke spuštění serveru:

    ![Spustit webový server tlačítka panelu nástrojů v sadě Visual Studio](media/django/run-web-server-toolbar-button.png)

1. Aplikace vytvořené pomocí šablony má tři stránky, domů, o a kontaktovat, což je přecházet mezi použití horního navigačního panelu. Trvat minutu nebo dvě prozkoumat různé části aplikace (o a obraťte se na stránky jsou velmi podobné "Webový projekt Flask" a nejsou popsané dál).

    ![Úplný přehled aplikace pro webový projekt Flask hlasování](media/flask/step06-full-app-view.png)

1. Na domovské stránce **vytvořit ukázková hlasování** tlačítko inicializuje aplikace datové úložiště se tři různé hlasování, které jsou popsány v `models/samples.json` stránky. Ve výchozím nastavení aplikace používá databázi v paměti (jak je znázorněno na stránce o), který se vynuluje pokaždé, když se aplikace restartuje. Aplikace také obsahuje kód pro práci s Azure Storage a Mongo databáze, jak je popsáno dále v tomto článku.

1. Jakmile jste inicializovat úložiště dat, vám může hlasovat v různých hlasování jak je znázorněno na domovské stránce (navigačního panelu a zápatí stránky byly vynechány jako stručný výtah):

    ![Zobrazení aplikace hlasování po inicializaci úložiště dat](media/flask/step06-polls-initialized.png)

1. Výběr hlasování zobrazí jeho konkrétní možnosti:

    ![Hlasování rozhraní pro hlasování](media/flask/step06-polls-voting-interface.png)

1. Jakmile jste hlasovat, aplikace zobrazí stránka s výsledky a vám umožní hlasovat znovu:

    ![Zobrazení výsledků po hlasování](media/flask/step06-polls-results.png)

1. Můžete nechat aplikaci spuštěnou pro oddíly, které následují.

    Pokud budete chtít aplikaci zastavit a [potvrzení změn do správy zdrojového kódu](learn-flask-visual-studio-step-02-create-app.md#commit-to-source-control), poprvé otevřete **změny** stránky v **Team Explorer**, klikněte pravým tlačítkem na složku (virtuálního prostředí pravděpodobně `env`) a vyberte **ignorovat tyto místní položky**.

### <a name="examine-the-project-contents"></a>Zkontrolujte obsah projektu

Jak jsme uvedli před. velká část Co je v projektu vytvořené z šablony "Hlasovací webový projekt Flask" (a šablony "Hlasovací webový projekt Flask/Jade") by měla být obeznámeni, pokud jste prozkoumali jiné šablony projektů v sadě Visual Studio. Další kroky v tomto článku shrnují více významné změny a dodatky, a to datové modely a další zobrazení.

## <a name="step-5-2-understand-the-data-models"></a>Krok 5 – 2: pochopit datové modely

Datové modely aplikace jsou Python třídy s názvem dotazování a volbou, která jsou definována v `models/__init__.py`. V hlasování představuje otázku, u kterého představují kolekci instancí volba k dispozici odpovědi. V hlasování také udržuje celkový počet hlasů (pro všechny volba) a metodu pro výpočet statistiky, které se používají ke generování zobrazení:

    ```python
    class Poll(object):
        """A poll object for use in the application views and repository."""
        def __init__(self, key=u'', text=u''):
            """Initializes the poll."""
            self.key = key
            self.text = text
            self.choices = []
            self.total_votes = None

        def calculate_stats(self):
            """Calculates some statistics for use in the application views."""
            total = 0
            for choice in self.choices:
                total += choice.votes
            for choice in self.choices:
                choice.votes_percentage = choice.votes / float(total) * 100 \
                    if total > 0 else 0
            self.total_votes = total

    class Choice(object):
        """A poll choice object for use in the application views and repository."""
        def __init__(self, key=u'', text=u'', votes=0):
            """Initializes the poll choice."""
            self.key = key
            self.text = text
            self.votes = votes
            self.votes_percentage = None
    ```

Tyto datové modely jsou obecné abstrakce, které umožňují zobrazení aplikace pro práci vůči různým typům zálohování úložiště dat, které jsou popsané v dalším kroku.

## <a name="step-5-3-understand-the-backing-data-stores"></a>Krok 5 – 3: pochopení zálohování úložišť dat

Pro úložiště dat v paměti, ve službě Azure table storage nebo v databázi Mongo DB můžete spouštět aplikace vytvořené pomocí šablony "Hlasovací webový projekt Flask".

Mechanizmus pro ukládání dat funguje takto:

1. Typ úložiště se specifikuje prostřednictvím `REPOSITORY_NAME` proměnné prostředí, která může být nastavena na hodnotu "paměti", "azuretablestore" nebo "mongodb". Bit kódu `settings.py` načte název, pomocí "paměti" jako výchozí. Pokud chcete změnit záložnímu úložišti, budete muset nastavit proměnnou prostředí a restartujte aplikaci.

    ```python
    from os import environ
    REPOSITORY_NAME = environ.get('REPOSITORY_NAME', 'memory')
    ```

1. `settings.py` Kód pak inicializuje `REPOSITORY_SETTINGS` objektu. Pokud chcete použít v úložišti Azure table nebo Mondo DB, musíte nejprve inicializovat jinde těchto úložištích dat a nastavení proměnných prostředí nezbytné, které informují aplikaci, jak se připojit k úložišti:

    ```python
    if REPOSITORY_NAME == 'azuretablestorage':
        REPOSITORY_SETTINGS = {
            'STORAGE_NAME': environ.get('STORAGE_NAME', ''),
            'STORAGE_KEY': environ.get('STORAGE_KEY', ''),
            'STORAGE_TABLE_POLL': environ.get('STORAGE_TABLE_POLL', 'polls'),
            'STORAGE_TABLE_CHOICE': environ.get('STORAGE_TABLE_CHOICE', 'choices'),
        }
    elif REPOSITORY_NAME == 'mongodb':
        REPOSITORY_SETTINGS = {
            'MONGODB_HOST': environ.get('MONGODB_HOST', None),
            'MONGODB_DATABASE': environ.get('MONGODB_DATABASE', 'polls'),
            'MONGODB_COLLECTION': environ.get('MONGODB_COLLECTION', 'polls'),
        }
    elif REPOSITORY_NAME == 'memory':
        REPOSITORY_SETTINGS = {}
    else:
        raise ValueError('Unknown repository.')
    ```

1. V `views.py`, aplikace volá metodu objektu pro vytváření, inicializace `Repository` pomocí název úložiště dat a nastavení:

    ```python
    from FlaskPolls.models import PollNotFound
    from FlaskPolls.models.factory import create_repository
    from FlaskPolls.settings import REPOSITORY_NAME, REPOSITORY_SETTINGS

    repository = create_repository(REPOSITORY_NAME, REPOSITORY_SETTINGS)
    ```

1. `factory.create_repository` Metoda se nachází v `models\factory.py`, který právě importuje modul odpovídající úložiště, pak vytvoří `Repository` instance:

    ```python
    def create_repository(name, settings):
        """Creates a repository from its name and settings. The settings
        is a dictionary where the keys are different for every type of repository.
        See each repository for details on the required settings."""
        if name == 'azuretablestorage':
            from .azuretablestorage import Repository
        elif name == 'mongodb':
            from .mongodb import Repository
        elif name == 'memory':
            from .memory import Repository
        else:
            raise ValueError('Unknown repository.')

        return Repository(settings)
    ```

1. Implementace `Repository` třídu, která jsou specifická pro každý úložiště dat lze nalézt v `models\azuretablestorage.py`, `models\mongodb.py`, a `models\memory.py`. Implementace úložiště Azure používá balíčku úložiště azure. implementace Mongo DB používá balíček pymongo. Jak jsme uvedli v kroku 5-1, oba balíčky jsou zahrnuty v šabloně projektů `requirements.txt` souboru. Prohlížení podrobností je ponechán jako cvičení pro čtečku.

Stručně řečeno `Repository` třída abstrahuje specifika úložiště dat a aplikace používá proměnné prostředí v době běhu na Vybrat a nakonfigurovat, které ze tří implementace používat.

Následující kroky přidat podporu pro jiné úložiště než tři poskytované šablony projektu, podle potřeby:

1. Kopírování `memory.py` do nového souboru tak, že máte základní rozhraní pro `Repository` třídy.
1. Upravte implementaci třídy jako vyhovuje úložiště dat, kterou používáte.
1. Upravit `factory.py` přidat další `elif` případu, který rozpozná název pro přidání datového úložiště a importuje příslušný modul.
1. Upravit `settings.py` rozpoznat jiný název v `REPOSITORY_NAME` proměnné prostředí a k chybě při inicializaci `REPOSITORY_SETTINGS` odpovídajícím způsobem.

### <a name="seed-the-data-store-from-samplesjson"></a>Úložiště dat z samples.json počáteční hodnoty

Na začátku úložiště všechny zvolené dat obsahuje žádné hlasování, tak domovskou stránku aplikace zobrazí zpráva "Žádné hlasování k dispozici" spolu s **vytvořit ukázková hlasování** tlačítko. Jakmile vyberete tlačítko, ale zobrazení změny zobrazení k dispozici hlasování. Tento přepínač se nakonfigurují podmíněného značky v `templates\index.html` (některé prázdné řádky vynechání jako stručný výtah):

    ```html
    {% extends "layout.html" %}
    {% block content %}
    <h2>{{title}}.</h2>

    {% if polls %}
    <table class="table table-hover">
        <tbody>
            {% for poll in polls %}
            <tr>
                <td>
                    <a href="/poll/{{poll.key}}">{{poll.text}}</a>
                </td>
            </tr>
            {% endfor %}
        </tbody>
    </table>
    {% else %}
    <p>No polls available.</p>
    <br />
    <form action="/seed" method="post">
        <button class="btn btn-primary" type="submit">Create Sample Polls</button>
    </form>
    {% endif %}
    {% endblock %}
    ```

`polls` Proměnné v šabloně pochází z volání `repository.get_polls`, dokud se neinicializuje úložiště dat vracející nic.

Výběr **vytvořit ukázková hlasování** tlačítko přejdete na adresu URL /seed. Obslužná rutina pro danou trasu je definována v `views.py`:

```python
@app.route('/seed', methods=['POST'])
def seed():
    """Seeds the database with sample polls."""
    repository.add_sample_polls()
    return redirect('/')
```

Volání `repository.add_sample_polls()` skončilo v jednom z konkrétní `Repository` implementace pro zvolený data store. Každá implementace volá `_load_samples_json` nalezena metoda v `models\__init__.py` načíst `models\samples.json` souboru do paměti a potom iteruje dat k vytvoření nezbytné `Poll` a `Choice` objektů v úložišti dat.

Po dokončení tohoto procesu `redirect('/')` příkaz v `seed` metoda přejde zpět na domovskou stránku. Protože `repository.get_polls` nyní vrátí objekt dat podmíněného značky v `templates\index.html` nyní vykreslí tabulku obsahující hlasování.

### <a name="question-how-does-one-add-new-polls-to-the-app"></a>Otázka: Jak jeden přidat nové hlasování do aplikace?

Odpověď: Aplikace podle pomocí šablony projektu neobsahuje do zařízení pro přidávání nebo úpravě hlasování. Můžete upravit `models\samples.json` vytvořit nová inicializace data, ale to by znamenalo, resetování úložišti. Chcete-li implementovat úpravy funkce, je potřeba rozšířit `Repository` třídy rozhraní s metody vytvoření nezbytné `Choice` a `Poll` instancí, pak implementovat uživatelského rozhraní v dalších stránek, které používají tyto metody.

## <a name="step-5-4-understand-the-poll-detail-and-results-views"></a>Krok 5 – 4: pochopení zobrazení podrobností a výsledky dotazování

Většina zobrazení vygenerované šablony "Hlasovací webový projekt Flask" a "Hlasovací webový projekt Flask/Jade", například zobrazení pro o a obraťte se na stránky, jsou velmi podobné zobrazením vytvořených šablonou "Webový projekt Flask" (nebo "Webový projekt Flask/Jade") můžete práce na incidentu pomocí výše v tomto kurzu. V předchozí části jste také zjistili, jak je implementována domovské stránce zobrazíte tlačítko inicializace nebo seznam hlasování.

Co je zde ještě je prozkoumat hlasujících (podrobnosti) a zobrazení výsledků jednotlivých dotazování.

Když vyberete hlasování z domovské stránky, aplikace přejde na adresu URL /poll/\<klíč\> kde *klíč* je jedinečný identifikátor v anketě. V `views.py` můžete uvidíte, že `details` funkci přiřazenou pro zpracování adresy URL směrování pro GET a požadavky. Můžete také zjistit, které používají `<key>` v adrese URL trasy mapuje trasy tohoto formuláře na stejnou funkci i generuje argument funkce této stejným názvem:

```python
@app.route('/poll/<key>', methods=['GET', 'POST'])
def details(key):
    """Renders the poll details page."""
    error_message = ''
    if request.method == 'POST':
        try:
            choice_key = request.form['choice']
            repository.increment_vote(key, choice_key)
            return redirect('/results/{0}'.format(key))
        except KeyError:
            error_message = 'Please make a selection.'

    return render_template(
        'details.html',
        title='Poll',
        year=datetime.now().year,
        poll=repository.get_poll(key),
        error_message=error_message,
    )
```

Pokud chcete zobrazit dotazování (požadavky GET), tato funkce jednoduše volá při `templates\details.html`, který iteruje nad dané dotazování `choices` pole, vytváření přepínače pro každou.

```html
{% extends "layout.html" %}

{% block content %}

<h2>{{poll.text}}</h2>
<br />

{% if error_message %}
<p class="text-danger">{{error_message}}</p>
{% endif %}

<form action="/poll/{{poll.key}}" method="post">
    {% for choice in poll.choices %}
    <div class="radio">
        <label>
            <input type="radio" name="choice" id="choice{{choice.key}}" value="{{choice.key}}" />
            {{ choice.text }}
        </label>
    </div>
    {% endfor %}
    <br />
    <button class="btn btn-primary" type="submit">Vote</button>
</form>

{% endblock %}
```

Protože **hlas** tlačítko má `type="submit"`, ho vyberete generuje požadavek POST zpět na stejnou adresu URL, který se směruje na `details` funkce ještě jednou. Tentokrát ale extrahuje volba z data formuláře a přesměruje na /results/\<volba\>.

/Results/\<klíč\> adresa URL se pak směruje na `results` fungovat v `views.py`, který pak zavolá dané dotazování `calculate_stats` metoda a zahrnuje `templates\results.html` pro vykreslování:

```python
@app.route('/results/<key>')
def results(key):
    """Renders the results page."""
    poll = repository.get_poll(key)
    poll.calculate_stats()
    return render_template(
        'results.html',
        title='Results',
        year=datetime.now().year,
        poll=poll,
    )
```

`results.html` Šablony, jeho části, jednoduše iteruje v rámci dané dotazování volby a generuje pro každou indikátor průběhu:

```html
{% extends "layout.html" %}

{% block content %}

<h2>{{poll.text}}</h2>
<br />

{% for choice in poll.choices %}
<div class="row">
    <div class="col-sm-5">{{choice.text}}</div>
    <div class="col-sm-5">
        <div class="progress">
            <div class="progress-bar" role="progressbar" aria-valuenow="{{choice.votes}}" aria-valuemin="0" aria-valuemax="{{poll.total_votes}}" style="width: {{choice.votes_percentage}}%;">
                {{choice.votes}}
            </div>
        </div>
    </div>
</div>
{% endfor %}

<br />
<a class="btn btn-primary" href="/poll/{{poll.key}}">Vote again?</a>

{% endblock %}
```

## <a name="next-steps"></a>Další kroky

> [!Note]
> Pokud jste se potvrzení řešení sady Visual Studio do správy zdrojového kódu v rámci postupu v tomto kurzu, teď je vhodná doba udělat další potvrzení. Řešení by měl odpovídat kurz zdrojový kód na Githubu: [Microsoft nebo python – ukázka vs-learning-flask](https://github.com/Microsoft/python-sample-vs-learning-flask).

Nyní jste prozkoumali celého šablony "Prázdný webový projekt Flask", "Webový projekt Flask [/Jade]" a "Hlasovací webový projekt Flask [/Jade]" v sadě Visual Studio. Jste se naučili základy Flask, například pomocí zobrazení, šablony a směrování a viděli, jak použít zálohování dat úložišť. Teď by měla být moci začít pracovat na webovou aplikaci se všemi zobrazení a modelů, které budete potřebovat vlastní.

Spuštění webové aplikace ve svém vývojovém počítači je jedním krokem zpřístupnění aplikace k vašim zákazníkům. Další kroky může zahrnovat následující úlohy:

- Nasazení webové aplikace na produkčním serveru, například Azure App Service. V tématu [publikování do služby Azure App Service](publishing-python-web-applications-to-azure-from-visual-studio.md), což zahrnuje určité změny, které jsou potřebné pro aplikace, Flask.

- Přidání implementace úložiště, která používá jiného úložiště dat produkční úrovni jako je například PostgreSQL, MySQL a SQL Server (všechny z nich může být hostovaný v Azure). Můžete také [Azure SDK pro jazyk Python](azure-sdk-for-python.md) pro práci s služby Azure storage jako tabulky a objekty BLOB, jakož i Cosmos DB.

- Nastavte průběžnou integraci/průběžné kanál nasazení služby jako Visual Studio Team Services (služby VSTS). Kromě práce zdrojového kódu (na služby VSTS, GitHub nebo jinde), může mít služby VSTS automaticky spustit testy jednotky jako nezbytný předpoklad pro verzi a taky nakonfigurovat kanál pro nasazení na pracovní server pro další testy před nasazením produkční. Služby VSTS, navíc se integruje se službou sledování řešení, jako jsou aplikace přehledy a zavře celý cyklus se nástroje pro agilní plánování. Další informace naleznete v tématu:

  - [Vytvoření kanálu CI nebo CD pro jazyk Python s Azure DevOps projektu](/vsts/build-release/apps/cd/azure/azure-devops-project-python?view=vsts)
  - [Vývoj Python v Azure pomocí Visual Studio Team Services (video, 11m 21s)](https://azure.microsoft.com/resources/videos/connect-2017-python-development-in-azure-with-visual-studio-team-services/).
