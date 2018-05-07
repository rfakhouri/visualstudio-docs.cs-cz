---
title: Kurz – další Django v sadě Visual Studio, krok 2
description: Návod základní informace o rozhraní Django v kontextu projektů sady Visual Studio, konkrétně postup vytvoření aplikace a pomocí zobrazení a šablony.
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
ms.openlocfilehash: 4050694685302eb527b33d8810bc7f92974bc305
ms.sourcegitcommit: 56018fb1f52f17bf35ae2ce71c50c763486e6173
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/04/2018
---
# <a name="tutorial-step-2-create-a-django-app-with-views-and-page-templates"></a>Kurz – krok 2: vytvoření aplikace Django s zobrazení a stránka šablony

**Předchozí krok: [vytvoření projektu Visual Studia a řešení](learn-django-in-visual-studio-step-01-project-and-solution.md)**

Co je nutné, pokud v projektu sady Visual Studio jsou pouze úrovni webu součástí Django *projektu*, který můžete spustit jeden nebo více rozhraní Django *aplikace*. Dalším krokem je vytvoření první aplikace obsahující pouze jednu stránku.

V tomto kroku teď zjistíte, jak:

> [!div class="checklist"]
> - Vytvoření aplikace Django s na jedné stránce (krok 2 - 1)
> - Spusťte aplikaci z projektu Django (krok 2-2)
> - Vykreslení zobrazení pomocí HTML (krok 2 – 3)
> - Vykreslení zobrazení pomocí šablony stránky Django (krok 2 – 4)

## <a name="step-2-1-create-an-app-with-a-default-structure"></a>Krok 2 – 1: vytvoření aplikace pomocí výchozí struktury

Aplikace Django je samostatný balíček Python, který obsahuje sadu související soubory pro konkrétní účel. Projekt Django může obsahovat libovolný počet aplikací, které odráží fakt, že webový hostitel může obsluhovat libovolný počet bodů samostatný záznam z jeden název domény. Projekt Django pro domény třeba contoso.com může například obsahovat jednu aplikaci pro www.contoso.com, aplikace pro support.contoso.com na druhý a třetí aplikace pro docs.contoso.com. V takovém případě projekt Django zpracovává směrování adres URL a nastavení lokality úrovni (v jeho `urls.py` a `settings.py` soubory), zatímco každá aplikace má svou vlastní odlišné stylů a chování prostřednictvím jeho interního směrování a zobrazení, modely, statické soubory a pro správu rozhraní.

Aplikace Django obvykle začíná standardní sadu souborů. Visual Studio poskytuje šablony položek k chybě při inicializaci aplikace Django v rámci projektu Django, společně s pomocí integrované nabídky příkazu, který slouží ke stejnému účelu:

- Šablony: V **Průzkumníku řešení**, klikněte pravým tlačítkem na projekt a vyberte **přidat** > **novou položku**. V **přidat novou položku** zadejte název aplikace v dialogovém okně, vyberte možnost "Django 1.9 aplikace" šablony **název** pole a vyberte možnost **OK**.

- Příkaz integrované: V **Průzkumníku řešení**, klikněte pravým tlačítkem na projekt a vyberte **přidat** > **aplikace Django**. Tento příkaz vás vyzve k zadání názvu a vytvoří aplikaci Django 1.9.

    ![Příkaz nabídky pro přidání aplikace Django](media/django/step02-add-django-app-command.png)

Pomocí těchto metod, vytvořte aplikaci s názvem "HelloDjangoApp". Výsledkem je do složky ve vašem projektu s tímto názvem, který obsahuje položky, jak je popsáno v následující tabulce.

![Soubory aplikace Django v Průzkumníku řešení](media/django/step02-django-app-in-solution-explorer.png)

| Položka | Popis |
| --- | --- |
| `__init.py__` | Soubor, který identifikuje jako balíček aplikace. |
| `migrations` | Složka, ve kterém Django ukládá skripty, které jsou zarovnané s změny modely má databáze aktualizovat. Nástroje pro migraci na rozhraní Django následně použít potřebné změny všechny předchozí verze databáze tak, aby odpovídala aktuální modelů. Pomocí migrace, zachovat fokus na modely a nechat Django zpracování základní schématu databáze. Migrace jsou popsané v kroku 6; Prozatím se jednoduše složka obsahuje `__init.py__` souboru (což znamená, že složka definuje vlastní balíček Python). |
| `templates` | Složku pro Django stránky šablon, které obsahují jeden soubor `index.html`. Šablony jsou bloky HTML, do kterého zobrazení můžete přidat informace, které dynamicky vykreslení stránky. Například stránka šablony "proměnné," `{{ content }}` v `index.html`, jsou zástupné symboly pro dynamické hodnoty, jak je popsáno dále v tomto článku (krok 2). Obvykle aplikace Django vytvořit obor názvů pro jejich šablony tak, že je do podsložky, která odpovídá názvu aplikace. |
| `admin.py` | Je soubor Python, ve kterém můžete rozšířit aplikace pro správu rozhraní (viz krok 6), který se používá ke zjištění a úpravy dat v databázi. Na začátku tento soubor obsahuje pouze příkaz `from django.contrib import admin`. Ve výchozím nastavení, rozhraní Django obsahuje standardní rozhraní pro správu prostřednictvím položky v projektu Django `settings.py` souboru, který můžete zapnout pomocí uncommenting existující položky v `urls.py`. |
| `apps.py` | Soubor Python, která definuje třídu konfigurace pro aplikaci (viz níže za touto tabulkou). |
| `models.py` | Modely jsou datové objekty, identifikuje funkce, pomocí kterých zobrazení interakci s základní databáze aplikace (viz krok 6). Django zajišťuje vrstvu připojení databáze, tak, aby aplikace nemusíte sami se týkají s těmito podrobnostmi. `models.py` Soubor je výchozí místo, ve kterém chcete-li vytvořit modely a nejprve obsahuje pouze příkaz `from django.db import models`. |
| `tests.py` | Soubor Python, který obsahuje základní struktury sady testů jednotek. |
| `views.py` | Zobrazení jsou, co si obvykle představit jako webových stránek, které trvat požadavku HTTP a vrátí odpověď HTTP. Zobrazení vykreslení obvykle ve formátu HTML, který webových prohlížečů vědět, jak zobrazit, ale zobrazení nemusí nutně být viditelné (jako jsou formuláře zprostředkující). Zobrazení je definována funkce Python jehož úkolem je k vykreslení HTML k odeslání do prohlížeče. `views.py` Soubor je výchozí místo, ve kterém můžete vytvořit zobrazení a nejprve obsahuje pouze příkaz `from django.shortcuts import render`. |

Obsah `app.py` při použití názvu "HelloDjangoApp" vypadat takto:

```python
from django.apps import AppConfig

class HelloDjangoAppConfig(AppConfig):
    name = 'HelloDjango'
```

### <a name="question-is-creating-a-django-app-in-visual-studio-any-different-from-creating-an-app-on-the-command-line"></a>Otázka: Je vytváření aplikace Django v sadě Visual Studio všechny liší od vytvoření aplikace na příkazovém řádku?

Odpověď: Spuštění **přidat** > **aplikace Django** příkaz nebo pomocí **přidat** > **nová položka** s aplikace Django Šablona vytváří stejné soubory, které jako příkaz Django `manage.py startapp <app_name>`. Výhody vytváření aplikace v sadě Visual Studio je složce aplikace a všechny jeho soubory se automaticky integrují do projektu. Příkaz stejné sady Visual Studio můžete vytvořit libovolný počet aplikací ve vašem projektu.

## <a name="step-2-2-run-the-app-from-the-django-project"></a>Krok 2 – 2: spuštění aplikace z projektu Django

V tomto bodu, pokud znovu spusťte projekt v sadě Visual Studio (pomocí tlačítka panelu nástrojů nebo **ladění** > **spustit ladění**), stále vidět výchozí stránky. Žádný obsah aplikace se zobrazí, protože je třeba definovat stránku konkrétní aplikace a přidat do projektu Django aplikaci:

1. V `HelloDjangoApp` složku, upravit `views.py` tak, aby odpovídaly kód níže, který definuje zobrazení s názvem "index":

    ```python
    from django.shortcuts import render
    from django.http import HttpResponse

    def index(request):
        return HttpResponse("Hello, Django!")
    ```

1. V `BasicProject` složky (vytvořený v kroku 1), upravte `urls.py` tak, aby odpovídaly alespoň následující kód (Pokud chcete je můžete zachovat významné komentáře):

    ```python
    from django.conf.urls import include, url
    import HelloDjangoApp.views

    # Django processes URL patterns in the order they appear in the array
    urlpatterns = [
        url(r'^$', HelloDjangoApp.views.index, name='index'),
        url(r'^home$', HelloDjangoApp.views.index, name='home'),
    ]
    ```

    Každý vzor adresy URL popisuje zobrazení, které Django směruje konkrétní adresy URL relativní webu (to znamená, část, která následuje "https://www.domain.com/"). V první položce v `urlPatterns` , které začíná regulární výraz `^$` je směrování pro kořenového webu, "/". Druhá položka `^home$` konkrétně tras "/ home". Může mít libovolný počet postupů do stejné zobrazení.

1. Spusťte projekt znovu zobrazíte zprávu "Hello, Django!" podle definice zobrazení. Po dokončení zastavení serveru.

### <a name="commit-to-source-control"></a>Zapsat do správy zdrojového kódu

Protože jste udělali změny kódu a jejich otestovali úspěšně, teď je nejvhodnější doba ke kontrole a uložte provedené změny do správy zdrojového kódu. Pozdější kroky v tomto kurzu vám připomene příslušná doba potvrzení znovu do správy zdrojového kódu a odkazovat zpět do této části.

1. Vyberte tlačítko změn ve spodní části sady Visual Studio (kroužky níže), která přejde na **Team Explorer**.

    ![Tlačítko změny zdroj ovládacího prvku na stavovém řádku Visual Studio](media/django/step02-source-control-changes-button.png)

1. V **Team Explorer**, zadejte zprávu o potvrzení, jako jsou "Vytvořit počáteční aplikace Django" a vyberte **potvrzení všechny**. Po dokončení potvrzení se zobrazí zpráva "potvrzení <hash> vytvoří místně. Synchronizace sdílet vaše změny se serverem." Pokud chcete doručte změny do vzdáleného úložiště, vyberte **synchronizace**, pak vyberte **nabízené** pod **odchozí potvrzení**. Můžete také obdržíte více místní potvrzení před odesláním vzdálené.

    ![Nabízená vzdálené v Team Exploreru potvrzení](media/django/step02-source-control-push-to-remote.png)

### <a name="question-what-is-the-r-prefix-before-the-routing-strings-for"></a>Otázka: co je předpona "r" před směrování řetězce pro?

Odpověď: 'R' předponu na řetězec v Pythonu znamená "raw," která nastaví Python není řídicí znaky v rámci řetězce. Protože regulární výrazy použít mnoho speciální znaky, pomocí předpony 'r' usnadňuje tyto řetězce mnohem čtení než pokud obsaženy řadu '\' řídicí znaky.

### <a name="question-what-do-the--and--characters-mean-in-the-url-routing-entries"></a>Otázka: co dělat ^ a znaky $ znamenat v rámci adresy URL směrování položek?

Odpověď: V regulárních výrazech, které definují vzorů adresy URL ^ znamená "začátek řádku" a znamená $ "-endu řádku, kde znovu adresy URL je relativní vůči kořenovému adresáři webu (část, která následuje `https://www.domain.com/`). Regulární výraz `^$` efektivně znamená "blank" a proto odpovídá úplnou adresu URL `https://www.domain.com/` (nic přidat do kořenovému adresáři webu). Vzor `^home$` přesně odpovídá `https://www.domain.com/home/`. (Django nepoužívá koncové / v porovnávání vzorů.)

Pokud nepoužijete koncovou v regulárním výrazu, stejně jako u `^home`, pak vzor adresy URL odpovídá *žádné* adresu URL, který začíná "home", například "home", "úkolu", "věci odvál čas" a "home192837".

A experimentovat s jiný regulární výrazy, zkuste nástroje online [regex101.com](https://regex101.com) v [pythex.org](http://www.pythex.org).

## <a name="step-2-3-render-a-view-using-html"></a>Krok 2 – 3: vykreslení zobrazení pomocí HTML

`index` Funkce, která máte, pokud v `views.py` nic jiného než prostého textu odpovědi HTTP pro stránku generuje. Většina reálného webové stránky, samozřejmě odpovědět s bohatou stránky HTML, které často začlenit dynamická data. Hlavním důvodem k definování zobrazení pomocí funkce je ve skutečnosti, že obsah může být generována dynamicky.

Protože argument `HttpResponse` je právě řetězec, můžete vytvořit až všechny HTML, který chcete v rámci řetězce. Jako jednoduchý příklad, nahraďte `index` funkce následujícím kódem (zachovat stávající `from` příkazy), který generuje odpovědi HTML pomocí dynamický obsah, který se aktualizuje pokaždé, když obnovíte stránku:

```python
from datetime import datetime

def index(request):
    now = datetime.now()

    html_content = "<html><head><title>Hello, Django</title></head><body>"
    html_content += "<strong>Hello Django!</strong> on " + now.strftime("%A, %d %B, %Y at %X")
    html_content += "</body></html>"

    return HttpResponse(html_content)
```

Spusťte projekt znovu a zobrazí zpráva podobná "**Hello Django!** v pondělí, 16 duben, 2018 na 16:28:10 ". Aktualizujte stránku a aktualizujte čas a potvrďte, že obsah má být vygenerován spolu s každou žádostí. Po dokončení zastavení serveru.

> [!Tip]
> Zástupce zastavením a restartováním projektu se má používat **ladění** > **restartujte** příkaz nabídky (Ctrl + Shift + F5) nebo na tlačítko Restartovat na ladění nástrojů:
>
> ![Restartujte na ladění nástrojů v sadě Visual Studio](media/debugging-restart-toolbar-button.png)

## <a name="step-2-4-render-a-view-using-a-page-template"></a>Krok 2 – 4: vykreslení zobrazení pomocí šablony stránky

Generování HTML v kódu funguje bez problémů pro velmi malé stránky, ale jako stránky získat sofistikovanější obvykle chcete zachovat statické HTML částí stránek (spolu s odkazy na soubory šablon stylů CSS a JavaScript) jako "stránka šablony", do kterých je pak vložit dynamické, generovaný kód obsah. V předchozí části, datum a čas z `now.strftime` volání je dynamický, což znamená, že veškerý obsah mohou být umístěny v šabloně stránky.

Šablona stránky Django je blok HTML, která může obsahovat libovolný počet nahrazení tokeny nazývané "proměnné", které jsou vymezeny hranatými `{{` a `}}`jako v `{{ content }}`. Django je ukázka modulu pak nahradí proměnné dynamický obsah, který zadáte v kódu.

Následující kroky ukazují použití šablon stránky:

1. V části `BasicProject` složky, která obsahuje Django projektu, otevřete `settings.py` souboru a název aplikace, "HelloDjangoApp", přidejte do `INSTALLED_APPS` seznamu. Přidání aplikace do seznamu informuje projekt Django, že je složka s tímto názvem, který obsahuje aplikace:

    ```python
    INSTALLED_APPS = [
        'HelloDjangoApp',
        # Other entries...
    ]
    ```

1. Také v `settings.py`, zajistěte, aby `TEMPLATES` objekt obsahuje následující řádek (zahrnuté ve výchozím nastavení), která nastaví Django a hledat šablony v nainstalovanou aplikaci `templates` složky:

    ```json
    'APP_DIRS': True,
    ```

1. V `HelloDjangoApp` složku, otevřete `templates/index.html` soubor šablony stránky, abyste viděli, že obsahuje jednu proměnnou `{{ content }}`:

    ```html
    <html>
    <head><title></title></head>

    <body>

    {{ content }}

    </body>
    </html>
    ```

1. V `HelloDjangoApp` složku, otevřete `views.py` a nahraďte `index` funkce s následujícím kódem, který používá `django.shortcuts.render` pomocné funkce. `render` Pomocník poskytuje zjednodušené rozhraní pro práci se šablonami stránky. Ujistěte se, aby všechny existující `from` příkazy.

    ```python
    from django.shortcuts import render   # Added for this step

    def index(request):
        now = datetime.now()

        return render(
            request,
            "index.html",  # Relative path from the 'templates' folder to the template file
            {
                'content': "<strong>Hello Django!</strong> on " + now.strftime("%A, %d %B, %Y at %X")
            }
        )
    ```

    První argument `render`, jak můžete vidět, je objekt žádosti a relativní cesty k souboru šablony v rámci aplikace `templates` složky. Soubor šablony jmenuje pro zobrazení je podporuje, pokud je to vhodné. Třetí argument `render` je pak slovník proměnných, které odkazuje šablona. Může zahrnovat objekty ve slovníku, v takovém případě proměnné v šabloně, které mohou odkazovat na `{{ object.property }}`.

1. Spusťte projekt a sledovat výstup. Měli byste vidět podobná zpráva k této zaznamenané kroku 2-2, což indikuje, že šablona funguje.

    Sledovat, ale, že HTML, můžete používat ve `content` vlastnost vykreslí pouze jako prostý text, protože `render` funkce automaticky řídicí sekvence této HTML. I když můžete získat kolem uvozovací znaky, v ideálním případě byste neměli používat vložené HTML na prvním místě. Formátování a styly se nejlépe uchovává se v šabloně stránky není v kódu, a je jednoduché, chcete-li vytvořit další proměnné tam, kde je potřeba.

    Můžete například změnit `templates/index.html` tak, aby odpovídala následující kód, který přidá název stránky a udržuje všechny formátování v šabloně stránky:

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

    Zapište `index` zobrazení funkce následujícím způsobem, zadejte hodnoty pro všechny proměnné v šabloně stránky:

    ```python
    def index(request):
        now = datetime.now()

        return render(
            request,
            "index.html",  # Relative path from the 'templates' folder to the template file
            {
                'title' : "Hello Django",
                'message' : "Hello Django!",
                'content' : " on " + now.strftime("%A, %d %B, %Y at %X")
            }
        )
    ```

1. Zastavení serveru a restartujte projektu a pozorovat, že stránka nyní vykreslí správně:

    ![Spuštěné aplikaci pomocí šablony](media/django/step02-result.png)

1. <a name="template-namespacing"></a>V posledním kroku přesuňte vaše šablony do podsložky se stejným názvem jako aplikace, která vytvoří obor názvů a zabraňuje možným konfliktům s jinými aplikacemi, které přidáte do projektu. To znamená, vytvořit podsložky v `templates` s názvem `HelloDjangoApp`, přesunout `index.html` do této podsložky a upravovat `index` zobrazit funkce k odkazování na novou cestu šablony, `HelloDjangoApp/index.html`. Spusťte projekt, ověřte, že stránka vykreslí správně a zastavení serveru.

1. Potvrdit změny pro zdroj ovládacího prvku a aktualizujte vzdálené úložiště, v případě potřeby, jak je popsáno v části [krok 2-2](#commit-to-source-control).

### <a name="question-do-page-templates-have-to-be-in-a-separate-file"></a>Otázka: stránky šablony musí být v samostatném souboru?

Odpověď: I když šablony jsou obvykle zachován v samostatné soubory HTML, můžete taky šablonu vložené. Použít samostatné soubory se doporučuje, ale k udržování čisté oddělení mezi značek a kódu.

### <a name="question-must-templates-use-the-html-file-extension"></a>Otázka: musí být šablony používat příponu souboru .html?

Odpověď: `.html` přípony souborů, šablona stránky je zcela volitelný, protože je vždy určit přesnou relativní cesta k souboru v druhý argument `render` funkce. Však Visual Studio (a dalšími editory) obvykle poskytují funkce, například kód dokončení a syntaxe zabarvení s `.html` soubory, které převáží skutečnost, že stránka šablony nejsou nezbytně HTML.

Ve skutečnosti při práci s projektem Django, Visual Studio automaticky rozpozná, pokud je ve skutečnosti šablonu Django soubor HTML, který upravujete a poskytuje určité funkce automatického dokončování. Například když začnete psát komentář šablony stránky Django, `{#`, Visual Studio automaticky vám dává ukončovací `#}` znaků. **Výběru jako komentáře** a **zrušte komentář u výběru** příkazy (na **upravit** > **Upřesnit** nabídky a na panelu nástrojů) komentáře k šabloně používají taky místo komentáře HTML.

### <a name="question-when-i-run-the-project-i-see-an-error-that-the-template-cannot-be-found-whats-wrong"></a>Otázka: Při spuštění projektu, zobrazuje chybu, která šablona nebyla nalezena. Co je?

Odpověď: Pokud se zobrazí chyby, které nelze nalézt šablonu, ujistěte se, přidání aplikace do projektu Django `settings.py` v `INSTALLED_APPS` seznamu. Bez této položky Django Nepozná k prohledání aplikace `templates` složky.

### <a name="question-why-is-template-namespacing-important"></a>Otázka: Proč se šablony namespacing důležité?

Odpověď: Když Django hledá šablonu podle `render` funkce, používá libovolnou souboru nejprve najde, která odpovídá relativní cestu. Pokud máte více aplikace Django ve stejném projektu, které používají stejné struktury složek pro šablony, je pravděpodobné, že jeden aplikace bude používat neúmyslně šablonu z jiné aplikace. Aby se zabránilo takové chyby, vždy vytvořit podsložku aplikace `templates` složky, která odpovídá názvu aplikace předejdete duplikace veškeré.

## <a name="next-steps"></a>Další kroky

> [!div class="nextstepaction"]
> [Statické soubory, přidat stránky a používat šablonu dědičnosti](learn-django-in-visual-studio-step-03-serve-static-files-and-add-pages.md)

## <a name="going-deeper"></a>Budete hlubší

- [Zápis první aplikace Django, část 1 - zobrazení](https://docs.djangoproject.com/en/2.0/intro/tutorial01/#write-your-first-view) (docs.djangoproject.com)
- Další možnosti Django šablony, například zahrnuje a dědičnosti, najdete v části [jazyk šablony Django](https://docs.djangoproject.com/en/2.0/ref/templates/language/) (docs.djangoproject.com)
- [Regulární výraz školení na inLearning](https://www.linkedin.com/learning/topics/regular-expressions) (LinkedIn)
- Kurz zdrojového kódu na Githubu: [Microsoft nebo python – ukázka vs-learning-django](https://github.com/Microsoft/python-sample-vs-learning-django)