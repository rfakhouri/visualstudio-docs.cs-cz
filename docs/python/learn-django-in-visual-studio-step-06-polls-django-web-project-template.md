---
title: Kurz – další Django v sadě Visual Studio, krok 6
description: Návod základní informace o rozhraní Django v kontextu projektů sady Visual Studio, konkrétně funkce šablony hlasovací webový projekt Django, například správu přizpůsobení.
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
ms.openlocfilehash: d88f1e258bf8aa9801555c256f825841fff9d476
ms.sourcegitcommit: e9d1018a01af62c3dc5aeb6b325faba7e20bd496
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/28/2018
ms.locfileid: "37089500"
---
# <a name="step-6-use-the-polls-django-web-project-template"></a>Krok 6: Použití šablony hlasovací webový projekt Django

**Předchozí krok: [ověřování uživatelů v Django](learn-django-in-visual-studio-step-05-django-authentication.md)**

Porozumění "Webový projekt Django" šablony sady Visual Studio můžete nyní prohlédnout třetí šablony Django "Hlasovací webový projekt Django", která staví na stejném základu kódu a ukazuje práci s databází.

V tomto kroku zjistíte, jak:

> [!div class="checklist"]
> - Vytvoření projektu ze šablony a inicializace databáze (krok 6 - 1)
> - Pochopení datových modelech (krok 6-2)
> - Použijte migrace (krok 6-3)
> - Porozumět zobrazení a šablony stránek vytvořených šablonou projektu (krok 6-4)
> - Vytvoření vlastní správu rozhraní (krok 6-5)

Projekt vytvořené pomocí této šablony je podobná získáte pomocí následujících [zápis první aplikace Django](https://docs.djangoproject.com/en/2.0/intro/tutorial01/) kurz v dokumentaci rozhraní Django. Webové aplikace se skládá z veřejného webu, umožňující uživatelům zobrazit hlasování a Hlasujte v nich, spolu s vlastní rozhraní pro správu, pomocí kterého můžete spravovat hlasování. Používá stejný systém ověřování jako šablonu "Webový projekt Django" a provede další použití databáze implementací rozhraní Django modely jako prozkoumané v následujících částech.

## <a name="step-6-1-create-the-project-and-initialize-the-database"></a>Krok 6 – 1: vytvoření projektu a inicializace databáze

1. V sadě Visual Studio, přejděte na **Průzkumníku řešení**, klikněte pravým tlačítkem na řešení "LearningDjango" v tomto kurzu vytvořili a vyberte **přidat** > **nový projekt**. (Případně, pokud chcete používat nové řešení, vyberte **soubor** > **nový** > **projektu** místo.)

1. V dialogovém okně Nový projekt, vyhledejte a vyberte šablonu, "Hlasovací webový projekt Django", volání "DjangoPolls" projekt a vyberte **OK**.

1. Jako další šablony projektů v sadě Visual Studio "Hlasovací webový projekt Django" Šablona obsahuje `requirements.txt` souboru výzvy Visual Studio zobrazí dotaz, kde k instalaci těchto závislostí. Zvolte možnost **nainstalovat do virtuálního prostředí**a v **Přidání virtuálního prostředí** dialogovém okně vyberte **vytvořit** přijměte výchozí hodnoty.

1. Po dokončení nastavení virtuální prostředí Python, postupujte podle pokynů v zobrazené `readme.html` k inicializaci databáze a vytvořit Django superuživatele (který je správcem). Kroky jsou nejprve kliknete pravým tlačítkem na projekt "DjangoPolls" v **Průzkumníku řešení**, vyberte **Python** > **Django migrovat** příkaz pak znovu klikněte pravým tlačítkem na projekt, vyberte **Python** > **vytvoření superuživatele Django** příkazů a postupujte podle pokynů. (Pokud se pokusíte vytvořit superuživatele nejprve, zobrazí chybu protože databáze nebyla inicializována.)

1. Nastavte projekt "DjangoPolls", který má být výchozí nastavení pro řešení sady Visual Studio tak, že kliknete pravým tlačítkem na takový projekt v **Průzkumníku řešení** a výběrem **nastavit jako spouštěný projekt**. Spouštěný projekt, který se zobrazí v tučné písmo, je co běží při spuštění ladicího programu.

1. Vyberte **ladění > Spustit ladění** (F5) nebo pomocí **Webový Server** tlačítka na panelu nástrojů ke spuštění serveru:

    ![Spustit webový server tlačítka panelu nástrojů v sadě Visual Studio](media/django/run-web-server-toolbar-button.png)

1. Aplikace vytvořené pomocí šablony má tři stránky, domů, o a kontaktovat, což je přecházet mezi použití horního navigačního panelu. Trvat minutu nebo dvě prozkoumat různé části aplikace (o a obraťte se na stránky jsou velmi podobné "Webový projekt Django" a nejsou popsané dál).

    ![Zobrazit v prohlížeči úplné aplikace hlasovací webový projekt Django](media/django/step06-full-app-view.png)

1. Také vyberte **správy** ověřený odkaz v navigačního panelu, který se zobrazí obrazovka pro přihlášení k předvedení toho, že je rozhraní pro správu oprávnění pouze správci. Použijte pověření superuživatele a se směruje na "/ správce" stránka, která je ve výchozím nastavení povolené, při použití této šablony projektu.

    ![Správce zobrazení aplikace hlasovací webový projekt Django](media/django/step06-polls-administrative-interface.png)

1. Můžete nechat aplikaci spuštěnou pro oddíly, které následují.

    Pokud budete chtít aplikaci zastavit a [potvrzení změn do správy zdrojového kódu](learn-django-in-visual-studio-step-02-create-an-app.md#commit-to-source-control), poprvé otevřete **změny** stránky v **Team Explorer**, klikněte pravým tlačítkem na složku (virtuálního prostředí pravděpodobně `env`) a vyberte **ignorovat tyto místní položky**.

### <a name="examine-the-project-contents"></a>Zkontrolujte obsah projektu

Jak jsme uvedli před. velká část Co je v projektu vytvořené z šablony "Hlasovací webový projekt Django" by měla být obeznámeni, pokud jste prozkoumali jiné šablony projektů v sadě Visual Studio. Další kroky v tomto článku shrnují více významné změny a dodatky, a to datové modely a další zobrazení.

### <a name="question-what-does-the-django-migrate-command-do"></a>Otázka: co provede příkaz Django migrovat?

Odpověď: **Django migrovat** příkaz konkrétně spustí `manage.py migrate` příkaz, který spustí všechny skripty v `app/migrations` složky, který nebyl dříve spuštěn. V takovém případě bude příkaz spuštěn `0001_initial.py` skript v této složce nastavit potřebné schématu v databázi.

Samotný skript pro migraci vytvoří `manage.py makemigrations` příkaz, který kontroluje aplikace `models.py` souboru, porovná ho na aktuální stav databáze a poté generuje nezbytné skripty pro migraci schématu databáze tak, aby odpovídala aktuální modelů. Tato funkce Django je velmi výkonný, jak je aktualizovat a změnit modely v čase. Generování a spuštění migrace, můžete synchronizujte modely a databáze s minimálními obtížemi.

Pracujete s migrace v kroku 6-3 později v tomto článku.

## <a name="step-6-2-understand-data-models"></a>Krok 6 – 2: pochopit datové modely

Modely pro aplikaci s názvem dotazování a výběru, jsou definovány v `app/models.py`. Každý je Python třída odvozená z `django.db.models.Model` a používá metody `models` třídy jako `CharField` a `IntegerField` k definování pole v modelu, který je mapovat sloupců databáze.

```python
from django.db import models
from django.db.models import Sum

class Poll(models.Model):
    """A poll object for use in the application views and repository."""
    text = models.CharField(max_length=200)
    pub_date = models.DateTimeField('date published')

    def total_votes(self):
        """Calculates the total number of votes for this poll."""
        return self.choice_set.aggregate(Sum('votes'))['votes__sum']

    def __unicode__(self):
        """Returns a string representation of a poll."""
        return self.text

class Choice(models.Model):
    """A poll choice object for use in the application views and repository."""
    poll = models.ForeignKey(Poll)
    text = models.CharField(max_length=200)
    votes = models.IntegerField(default=0)

    def votes_percentage(self):
        """Calculates the percentage of votes for this choice."""
        total = self.poll.total_votes()
        return self.votes / float(total) * 100 if total > 0 else 0

    def __unicode__(self):
        """Returns a string representation of a choice."""
        return self.text
```

Jak vidíte, hlasování udržuje popis v jeho `text` pole a publikaci datum v `pub_date`. Tato pole jsou pouze ty, které existují pro dané dotazování v databázi. `total_votes` pole se vypočítává za běhu.

Výběr má vztah k dotazování prostřednictvím `poll` pole, obsahuje popis v `text`a udržuje počet pro jejich výběr v `votes`. `votes_percentage` Pole se vypočítává za běhu a nebyl nalezen v databázi.

Úplný seznam typů polí je `CharField` (omezeným text) `TextField` (neomezená text), `EmailField`, `URLField`, `DateTimeField`, `IntegerField`, `DecimalField`, `BooleanField`, `ForeignKey`, a `ManyToMany`. Každé pole trvá některé atributy, jako je `max_length`. `blank=True` Atribut znamená pole je volitelné; `null=true` znamená, že hodnota je volitelná. K dispozici je také `choices` atribut, který omezuje hodnoty na hodnoty v poli data hodnotu nebo zobrazení hodnota řazené kolekce členů. (Viz [modelu referenční dokumentace polí](https://docs.djangoproject.com/en/2.0/ref/models/fields/) v dokumentaci k rozhraní Django.)

Můžete potvrdit, přesně co je uložena v databázi tak, že prověří `db.sqlite3` v projektu pomocí nástroje, například [SQLite prohlížeče](http://sqlitebrowser.org/). V databázi, uvidíte, že pole cizího klíče jako `poll` při výběru modelu je uloženo jako `poll_id`; Django zpracovává mapování automaticky.

Obecně platí práci s vaší databáze v Django znamená práce výhradně prostřednictvím modely tak, aby Django můžete spravovat základní databáze vaším jménem.

### <a name="seed-the-database-from-samplesjson"></a>Počáteční hodnoty databázi z samples.json

Na začátku databáze obsahuje žádné hlasování. Můžete použít rozhraní pro správu na "/ správce" adresa URL pro přidání dotazování ručně, a můžete také navštívit stránku "/ osivo" na webu spuštěná přidat počáteční hodnoty databázi s hlasování definované v dané aplikaci `samples.json` souboru.

Projekt Django `urls.py` má přidané vzor adresy URL, `url(r'^seed$', app.views.seed, name='seed'),`. `seed` Zobrazit v `app/views.py` načte `samples.json` souboru a vytvoří objekty nezbytné modelu. Django pak automaticky vytvoří odpovídající záznamy v podkladové databázi.

Všimněte si použití `@login_required` dekoratéra, které označuje úroveň ověřování pro zobrazení.

```python
@login_required
def seed(request):
    """Seeds the database with sample polls."""
    samples_path = path.join(path.dirname(__file__), 'samples.json')
    with open(samples_path, 'r') as samples_file:
        samples_polls = json.load(samples_file)

    for sample_poll in samples_polls:
        poll = Poll()
        poll.text = sample_poll['text']
        poll.pub_date = timezone.now()
        poll.save()

        for sample_choice in sample_poll['choices']:
            choice = Choice()
            choice.poll = poll
            choice.text = sample_choice
            choice.votes = 0
            choice.save()

    return HttpResponseRedirect(reverse('app:home'))
```

Pokud chcete vidět, spusťte aplikaci nejprve vidět žádné hlasování ještě neexistuje. Přejdete na adresu URL "/ osivo", a když se aplikace vrátí na domovskou stránku byste měli vidět, že máte k dispozici hlasování. Znovu, klidně si zkontrolujte nezpracovaná `db.sqlite3` soubor s nástroje, jako [SQLite prohlížeče](http://sqlitebrowser.org/).

![Hlasovací webový projekt Django aplikace pomocí dosazená databáze](media/django/step06-app-with-seeded-database.png)

### <a name="question-is-it-possible-to-initialize-the-database-using-the-django-administrative-utility"></a>Otázka: je možné k chybě při inicializaci databáze pomocí nástroje pro správu Django?

Odpověď: Ano, použít [správce django loaddata příkaz](https://docs.djangoproject.com/en/1.9/ref/django-admin/#loaddata) provést stejný úkol jako synchronizace replik indexů stránky v aplikaci. Při práci na úplné webovou aplikaci, můžete použít kombinaci těchto dvou metod: Inicializace databáze z příkazového řádku a následně je převést na počáteční hodnoty stránku sem do rozhraní API, do kterého můžete odeslat další libovolné JSON spíše než předávající v souboru s pevně zakódovaným.

## <a name="step-6-3-use-migrations"></a>Krok 6 – 3: použijte migrace

Pokud jste spustili `manage.py makemigrations` příkazu (pomocí místní nabídky v sadě Visual Studio) po vytvoření projektu, Django vytvořil soubor `app/migrations/0001_initial.py` souboru. Tento soubor obsahuje skript, který vytvoří počáteční databázových tabulek.

Vzhledem k tomu, že budete nevyhnutelnou provedete změny modely v čase, Django usnadňuje aktuálnost základní schéma databáze pomocí těchto modelů. Obecný postup je následující:

1. Změnit modely v vaší `models.py` souboru.
1. V sadě Visual Studio, klikněte pravým tlačítkem na projekt v **Průzkumníku řešení** a vyberte **Python** > **migrace zkontrolujte Django** příkaz. Jak je popsáno výše, tento příkaz generuje skripty v `app/migrations` migrace databáze z aktuálního stavu do nového stavu.
1. Chcete-li použít skripty pro skutečné databáze, znovu klikněte pravým tlačítkem na projekt a vyberte **Python** > **Django migrovat**.

Django sleduje migrace, které byly použity všechny danou databázi tak, aby při spuštění příkazu migrací Django platí, podle toho, která migrace je potřeba. Pokud vytvoříte novou prázdnou databázi, například spuštění příkazu migrací přináší aktualizován s vaší aktuální modely použitím každý skript pro migraci. Podobně pokud provedete více změn modelu a vygenerujte migrace na vývojovém počítači, lze následně použít kumulativní migrace do provozní databáze spuštěním příkazu migrací na provozním serveru. Django znovu použije jenom migrace skripty, které byly generovány od posledního přenosu provozní databáze.

Projevily změny modelu, zkuste následující kroky:

1. Přidat pole author volitelné do modelu dotazování v `app/models.py` přidáním následujícího řádku po `pub_date` pole, které chcete přidat volitelný `author` pole:

    ```python
    author = models.CharField(max_length=100, blank=True)
    ```

1. Uložte soubor a potom klikněte pravým tlačítkem na projekt "DjangoPolls" **Průzkumníku řešení** a vyberte **Python** > **migrace zkontrolujte Django** příkaz.
1. Vyberte **projektu** > **zobrazit všechny soubory** příkazu zobrazte nově vygenerovaný skriptu `migrations` složky, jejichž název začíná `002_auto_`. Klikněte pravým tlačítkem, která soubor a vyberte **zahrnout do projektu**. Pak můžete vybrat **projektu** > **zobrazit všechny soubory** znovu k obnovení původního zobrazení. (Viz druhou otázku níže podrobnosti na tomto kroku.)
1. V případě potřeby otevřete daný soubor a zkontrolujte, jak Django skriptů změnu z předchozího stavu modelu do nového stavu.
1. Klikněte pravým tlačítkem na projekt Visual Studio znovu a vyberte **Python** > **Django migrovat** pro použití změn do databáze.
1. V případě potřeby otevřete databázi v příslušný prohlížeč pro potvrzení změny.

Funkce migrace Django na celkové, znamená, potřebovat nikdy spravovat svého schématu databáze ručně. Stačí provést změny vašeho modely, generování skriptů pro migraci a aplikovat pomocí příkazu migrací.

### <a name="question-what-happens-if-i-forget-to-run-the-migrate-command-after-making-changes-to-models"></a>Otázka: co se stane, když I zapomněli spustit příkaz migrací po provedení změn modely?

Odpověď: Pokud modely neshodují, co je v databázi, Django při běhu selže s příslušné výjimky. Například pokud zapomenete pro migraci uvedené v předchozí části změn modelu, zobrazí chybu "žádný takový sloupec: app_poll.author":

![Chyba zobrazí, když nebyla migrována změnu modelu](media/django/step06-exception-when-forgetting-to-migrate.png).

### <a name="question-why-doesnt-solution-explorer-show-newly-generated-scripts-after-running-django-make-migrations"></a>Otázka: Proč nepodporuje skripty zobrazit nově vygenerované Průzkumník řešení po spuštění migrace zkontrolujte Django?

Odpověď: I když nově generovaných skriptů existovat v `app/migrations` složky a použity při spuštění **Django migrovat** příkaz, se nezobrazí automaticky v **Průzkumníku řešení** protože není byli přidáni do projektu sady Visual Studio. Je zpřístupněte, vyberte nejdřív **projektu** > **zobrazit všechny soubory** příkazu nabídky nebo tlačítka panelu nástrojů uvedených v následující obrázek. Tento příkaz způsobí, že **Průzkumníku řešení** chcete zobrazit všechny soubory ve složce projektu pomocí tečkové outline ikonu pro položky, které nebyly přidány do projektu sám sebe. Klikněte pravým tlačítkem na soubory, které chcete přidat a vyberte **zahrnout do projektu**, což je také zahrnuje ve správě zdrojového kódu s vaší další potvrzení.

![Zahrnout do projekt v Průzkumníku řešení – příkaz](media/django/step06-include-migrations-script-in-project.png)

### <a name="question-can-i-see-what-migrations-would-be-applied-before-running-the-migrate-command"></a>Otázka: je možné zobrazit jaké migrace by bylo možné provést před spuštěním příkazu migrací?

Odpověď: Ano, používat [správce django showmigrations příkaz](https://docs.djangoproject.com/en/2.0/ref/django-admin/#showmigrations).

## <a name="step-6-4-understand-the-views-and-page-templates-created-by-the-project-template"></a>Krok 6 – 4: pochopení zobrazení a stránka šablony vytvořené v šabloně projektů

Většina zobrazení vygenerované šablony "Hlasovací webový projekt Django", například zobrazení pro o a obraťte se na stránky, jsou velmi podobné zobrazením vytvořených šablonou "Webový projekt Django" práce s dříve v tomto kurzu. Co se liší v hlasování aplikace je, že jeho Domovská stránka využívá modely, jako proveďte několik přidat stránky pro hlasování a zobrazení výsledků dotazování.

První řádek v projektu Django `urlpatterns` pole v `urls.py` soubor je více než jen jednoduchý směrování zobrazení aplikace. Místo toho vrátí v aplikaci na vlastní `urls.py` souboru:

```python
from django.conf.urls import url, include
import app.views

urlpatterns = [
    url(r'^', include('app.urls', namespace="app")),
    # ..
]
```

`app/urls.py` Soubor pak obsahuje některé zajímavějšího směrování kódu (vysvětlující poznámky přidané):

```python
urlpatterns = [
    # Home page routing
    url(r'^$',
        app.views.PollListView.as_view(
            queryset=Poll.objects.order_by('-pub_date')[:5],
            context_object_name='latest_poll_list',
            template_name='app/index.html',),
        name='home'),

    # Routing for a poll page, which use URLs in the form <poll_id>/,
    # where the id number is captured as a group named "pk".
    url(r'^(?P<pk>\d+)/$',
        app.views.PollDetailView.as_view(
            template_name='app/details.html'),
        name='detail'),

    # Routing for <poll_id>/results pages, again using a capture group
    # named pk.
    url(r'^(?P<pk>\d+)/results/$',
        app.views.PollResultsView.as_view(
            template_name='app/results.html'),
        name='results'),

    # Routing for <poll_id>/vote pages, with the capture group named
    # poll_id this time, which becomes an argument passed to the view.
    url(r'^(?P<poll_id>\d+)/vote/$', app.views.vote, name='vote'),
]
```

Pokud si nejste obeznámeni s složitější regulární výrazy použít se zde, můžete vložit výraz do [regex101.com](https://regex101.com/) vysvětlení v prostý jazyk. (Budete potřebovat, abyste se vyhnuli lomítka `/` přidáním zpětným lomítkem, `\` před sebou; uvozovací znaky není nutné v Pythonu z důvodu `r` předponu na řetězec, což znamená "nezpracovaných").

V Django, syntaxe `?P<name>pattern` vytvoří skupinu s názvem `name`, která bude předána do zobrazení v pořadí, které se objeví jako argumenty. V následující kód dříve `PollsDetailView` a `PollsResultsView` přijímat argument s názvem `pk` a `app.views.vote` obdrží argument s názvem `poll_id`.

Můžete také zjistit, že většina zobrazení, které nejsou právě přímé odkazy na funkce zobrazení v `app/views.py`. Místo toho většina odkazovat na třídy této stejného souboru, který je odvozen od `django.views.generic.ListView` nebo `django.views.generic.DetailView`. Zadejte základní třídy `as_view` metody, které trvat `template_name` argument k identifikaci šablony. `ListView` Základní třídy, jako použít pro domovskou stránku, také očekává `queryset` vlastnost obsahující data a `context_object_name` vlastnost s názvem proměnné, podle kterého chcete data v šabloně, najdete v tomto případě `latest_poll_list`.

Teď můžete zkontrolovat `PollListView` pro domovskou stránku, který je definován následujícím způsobem v `app/views.py`:

```python
class PollListView(ListView):
    """Renders the home page, with a list of all polls."""
    model = Poll

    def get_context_data(self, **kwargs):
        context = super(PollListView, self).get_context_data(**kwargs)
        context['title'] = 'Polls'
        context['year'] = datetime.now().year
        return context
```

Vše, který má na jednom místě je určit model, který zobrazení pracuje (dotazování) a přepíše `get_context_data` metody přidat `title` a `year` hodnoty do kontextu.

Základní šablony (`templates/app/index.html`) je následující:

```html
{% if latest_poll_list %}
<table class="table table-hover">
    <tbody>
        {% for poll in latest_poll_list %}
        <tr>
            <td>
                <a href="{% url 'app:detail' poll.id %}">{{poll.text}}</a>
            </td>
        </tr>
        {% endfor %}
    </tbody>
</table>
{% else %}
<!-- ... other content omitted ... -->
{% endif %}
```

Jednoduše PUT, šablony obdrží seznam objektů dotazování v `latest_poll_list`a pak iteruje v rámci tohoto seznamu můžete vytvořit řádek tabulky, který obsahuje odkaz na každý dotazování pomocí dané dotazování `text` hodnotu. V `{% url %}` štítku "app:detail" odkazuje na vzor adresy url v `app/urls.py` s názvem "podrobností" pomocí `poll.id` jako argument. Důsledkem tohoto je, že se vytvoří adresa URL pomocí odpovídající vzoru Django a použije tento odkazu. Tento bit budoucna znamená, že můžete změnit tento vzor adresy URL v kdykoli a odkazy na generovaný automaticky aktualizovat tak, aby odpovídaly.

`PollDetailView` a `PollResultsView` třídy v `app/views.py` (není tady zobrazené) vypadat téměř shodné s `PollListView` s tím rozdílem, že jsou odvozeny od `DetailView` místo. Jejich příslušné šablony `app/templates/details.html` a `app/templates/results.html` pak umístit na odpovídající pole z modelů v rámci různých ovládacích prvků HTML. Jeden jedinečný část v `details.html` je, že volby hlasování jsou obsažena ve formuláři HTML, který při odeslání nepodporuje metodu POST SMĚŘUJÍCÍ na adresu URL /vote. Jak je vidět dříve, tento vzor adresy URL se směruje na `app.views.vote`, které je implementováno takto (Poznámka: `poll_id` argument, který je pojmenovaná skupina v regulárním výrazu používá v směrování pro toto zobrazení znovu):

```python
def vote(request, poll_id):
    """Handles voting. Validates input and updates the repository."""
    poll = get_object_or_404(Poll, pk=poll_id)
    try:
        selected_choice = poll.choice_set.get(pk=request.POST['choice'])
    except (KeyError, Choice.DoesNotExist):
        return render(request, 'app/details.html', {
            'title': 'Poll',
            'year': datetime.now().year,
            'poll': poll,
            'error_message': "Please make a selection.",
    })
    else:
        selected_choice.votes += 1
        selected_choice.save()
        return HttpResponseRedirect(reverse('app:results', args=(poll.id,)))
```

V tomto zobrazení nemá vlastní šablony odpovídající jako dalších stránek. Místo toho ověří vybrané dotazování, zobrazující 404, pokud hlasování neexistuje (jen v případě, že uživatel zadá adresu URL podobnou "hlas/1a2b3c"). Pak je zajištěno, že voted volba je platný pro dané dotazování. Pokud ne, `except` bloku právě vykreslí stránku podrobností znovu s chybovou zprávou. Pokud volba je platný, zobrazení sečte hlasování a přesměruje na stránku výsledků.

## <a name="step-6-5-create-a-custom-administration-interface"></a>Krok 6 – 5: vytvoření vlastní správu rozhraní

Poslední šablony "Hlasovací webový projekt Django" jsou vlastní rozšíření výchozí rozhraní správce Django, jak je uvedené výše v tomto článku v části Krok 6-1. Poskytuje výchozí rozhraní pro uživatele a skupiny správy, ale nic Další. Šablona projektu hlasování přidá funkce, které vám umožní spravovat také hlasování.

První řadě vzory adresu URL v projektu Django `urls.py` má `url(r'^admin/', include(admin.site.urls)),` zahrnuté ve výchozím nastavení; vzoru "správce/doc" jsou také obsaženy ve označeno jako komentář.

Aplikace pak obsahuje soubor `admin.py`, který Django spustí automaticky při návštěvě rozhraní pro správu díky zahrnutí `django.contrib.admin` v `INSTALLED_APPS` pole `settings.py`. Kód v tomto souboru, v souladu s šablonou projektu, vypadá takto:

```python
from django.contrib import admin
from app.models import Choice, Poll

class ChoiceInline(admin.TabularInline):
    """Choice objects can be edited inline in the Poll editor."""
    model = Choice
    extra = 3

class PollAdmin(admin.ModelAdmin):
    """Definition of the Poll editor."""
    fieldsets = [
        (None, {'fields': ['text']}),
        ('Date information', {'fields': ['pub_date']}),
    ]
    inlines = [ChoiceInline]
    list_display = ('text', 'pub_date')
    list_filter = ['pub_date']
    search_fields = ['text']
    date_hierarchy = 'pub_date'

admin.site.register(Poll, PollAdmin)
```

Jak je vidět `PollAdmin` třída odvozená z `django.contrib.admin.ModelAdmin` a k přizpůsobení číslo pole pomocí názvů z tohoto `Poll` model, který spravuje. Tato pole jsou popsané na [ModelAdmin možnosti](https://docs.djangoproject.com/en/2.0/ref/contrib/admin/#modeladmin-options) v dokumentaci k rozhraní Django.

Volání `admin.site.register` pak připojí k modelu třídy (`Poll`) a zahrnuje v rozhraní správce. Celkový výsledek je zobrazena níže:

![Správce zobrazení aplikace hlasovací webový projekt Django](media/django/step06-polls-administrative-interface.png)

## <a name="next-steps"></a>Další kroky

> [!Note]
> Pokud jste se potvrzení řešení sady Visual Studio do správy zdrojového kódu v rámci postupu v tomto kurzu, teď je vhodná doba udělat další potvrzení. Řešení by měl odpovídat kurz zdrojový kód na Githubu: [Microsoft nebo python – ukázka vs-learning-django](https://github.com/Microsoft/python-sample-vs-learning-django).

Nyní jste prozkoumali celého šablony "Prázdný webový projekt Django", "Webový projekt Django" a "Hlasovací webový projekt Django" v sadě Visual Studio. Jste se naučili základy Django, například pomocí zobrazení a šablony a jste prozkoumali směrování, ověřování a použití modelů databáze. Teď by měla být moci vytvořit webovou aplikaci vlastní veškeré zobrazení a modelů, které potřebujete.

Spuštění webové aplikace ve svém vývojovém počítači je jedním krokem zpřístupnění aplikace k vašim zákazníkům. Další kroky může zahrnovat následující úlohy:

- Nasazení webové aplikace na produkčním serveru, například Azure App Service. V tématu [publikování do služby Azure App Service](publishing-python-web-applications-to-azure-from-visual-studio.md), což zahrnuje určité změny, které jsou potřeba pro aplikace Django.

- Přizpůsobení stránce 404 vytvořením šablony s názvem `templates/404.html`. Pokud jsou k dispozici, Django Tato šablona používá namísto jeho výchozí nastavení. Další informace najdete v tématu [zobrazení chyby](https://docs.djangoproject.com/en/2.0/ref/views/#error-views) v dokumentaci k rozhraní Django.

- Zápis testů jednotek `tests.py`; šablony projektů Visual Studio poskytují výchozí bod pro tyto a další informace naleznete na [zápis první aplikace Django, část 5 – testování](https://docs.djangoproject.com/en/2.0/intro/tutorial05/) a [testování v Django](https://docs.djangoproject.com/en/2.0/topics/testing/) v dokumentaci k rozhraní Django.

- Aplikace můžete změňte z SQLite k úložišti dat produkční úrovni jako je například PostgreSQL, MySQL a SQL Server (všechny z nich může být hostovaný v Azure). Jak je popsáno na [kdy použít SQLite](https://www.sqlite.org/whentouse.html) (sqlite.org), SQLite funguje bez problémů pro s nízkou až střední provoz lokality s méně než 100 tisíc přístupů za den, ale nedoporučuje se používat pro vyšší svazky. Je také omezena na jednom počítači, takže ji nelze použít v žádném scénáři více serverů, jako je například Vyrovnávání zatížení a geografická replikace. Informace o podpoře na Django pro jiné databáze najdete v tématu [nastavení databáze](https://docs.djangoproject.com/en/2.0/intro/tutorial02/#database-setup). Můžete také [Azure SDK pro jazyk Python](azure-sdk-for-python.md) pro práci s služby Azure storage jako tabulky a objekty BLOB.

- Nastavte průběžnou integraci/průběžné kanál nasazení služby jako Visual Studio Team Services (služby VSTS). Kromě práce zdrojového kódu (na služby VSTS, GitHub nebo jinde), může mít služby VSTS automaticky spustit testy jednotky jako nezbytný předpoklad pro verzi a taky nakonfigurovat kanál pro nasazení na pracovní server pro další testy před nasazením produkční. Služby VSTS, navíc se integruje se službou sledování řešení, jako jsou aplikace přehledy a zavře celý cyklus se nástroje pro agilní plánování. Další informace naleznete v tématu:

  - [Vytvoření kanálu CI nebo CD pro jazyk Python s Azure DevOps projektu](/vsts/build-release/apps/cd/azure/azure-devops-project-python?view=vsts)
  - [Vývoj Python v Azure pomocí Visual Studio Team Services (video, 11m 21s)](https://azure.microsoft.com/resources/videos/connect-2017-python-development-in-azure-with-visual-studio-team-services/).

