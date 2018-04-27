---
title: Kurz – další Django v sadě Visual Studio, krok 1
description: Návod, základní informace o rozhraní Django v kontextu projektů sady Visual Studio, ukázka podpora Visual Studio poskytuje pro vývoj Django.
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
ms.openlocfilehash: 97f801d111f7fcb2aaeb207c3f3fcf1784a04f30
ms.sourcegitcommit: 928885ace538bef5b25961358d4f166d648f196a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/27/2018
---
# <a name="tutorial-step-1-get-started-with-the-django-web-framework-in-visual-studio"></a>Kurz – krok 1: Začínáme s webového rozhraní Django v sadě Visual Studio

[Django](https://www.djangoproject.com/) je určená pro vývoj webů rychlé, zabezpečené a škálovatelné vysoké úrovně rozhraní Python. V tomto kurzu prozkoumá rozhraní Django v kontextu projektu šablony, které poskytuje Visual Studio zjednodušují vytváření založené na rozhraní Django webové aplikace.

V tomto kurzu zjistíte, jak:

> [!div class="checklist"]
> - Vytvořit základní projekt Django v úložišti Git pomocí šablony "Prázdný webový projekt Django" (krok 1)
> - Vytvoření aplikace Django s jednu stránku a vykreslit tuto stránku pomocí šablony (krok 2)
> - Statické soubory, přidat stránky a používat šablonu dědičnosti (krok 3)
> - Webový projekt Django šablonu použít k vytvoření aplikace s více stránek a přizpůsobivý návrh (krok 4)
> - Ověřování uživatelů (krok 5)
> - Šablonu hlasovací webový projekt Django použít k vytvoření aplikace, která používá modely, migrace databáze a úpravy, aby rozhraní pro správu (krok 6)

## <a name="prerequisites"></a>Požadavky

- Visual Studio 2017 se zatížením Python, který je nainstalovaný. Pokyny najdete v tématu [instalaci Python podporují v sadě Visual Studio](installing-python-support-in-visual-studio.md).

Šablony projektů Django jsou také všechny starší verze nástrojů Python Tools pro sadu Visual Studio, i když podrobnosti se můžou lišit od co je popsané v tomto kurzu (zejména různých ve starších verzích rozhraní Django).

### <a name="visual-studio-projects-and-django-projects"></a>"Projektů sady visual Studio" a "Django projekty"

V terminologii Django "Django projektu" se skládá z několika soubory konfigurace na úrovni webu společně s jeden nebo více "aplikací" které nasadíte do webového hostitele k vytvoření úplné webové aplikace. Projekt Django může obsahovat více aplikací a té samé aplikace může být ve více projektech Django.

Projekt sady Visual Studio pro jeho součástí může obsahovat projekt Django společně s více aplikacemi. Z důvodu zjednodušení vždy, když v tomto kurzu odkazuje na právě "projektu," jej odkazuje na projekt Visual Studio. Odkazuje na část "Django projektu" webové aplikace, používá "Django projektu" konkrétně.

V průběhu tohoto kurzu vytvoříte jedné sady Visual Studio řešení, které obsahuje tři samostatné projekty Django, z nichž každý obsahuje jenom jedna aplikace Django. Udržováním projektů ve stejném řešení, můžete snadno přepínat přepínat mezi různé soubory pro porovnání.

## <a name="step-1-1-create-a-visual-studio-project-and-solution"></a>Krok 1-1: vytvoření projektu Visual Studia a řešení

Při práci s rozhraním Django z příkazového řádku, kdy obvykle začínáte projektu spuštěním `django-admin startproject <project_name>` příkaz. V sadě Visual Studio pomocí šablony "Prázdný webový projekt Django" poskytuje stejnou strukturu v rámci projektu sady Visual Studio a řešení.

1. V sadě Visual Studio, vyberte **soubor** > **nový** > **projektu**, vyhledejte "Django" a vyberte **prázdný webový projekt Django**  šablony. (Šablona je také najdete v části **Python** > **webové** v seznamu levé straně.)

    ![Dialogové okno Nový projekt v sadě Visual Studio pro prázdný webový projekt Django](media/django/step01-new-blank-project.png)

1. Do polí v dolní části dialogové okno, zadejte následující informace (jak je znázorněno na předchozím obrázku) a potom vyberte **OK**:

    - **Název**: nastavte na název projektu sady Visual Studio k "BasicProject". Tento název se taky používá pro projekt Django.
    - **Umístění**: určení umístění, ve kterém chcete vytvořit řešení sady Visual Studio a projekt.
    - **Řešení**: nechat tento ovládací prvek nastavena na možnost "Vytvořit nové řešení" výchozí.
    - **Název řešení**: nastavte na "LearningDjango", což je vhodné pro řešení jako kontejner pro více projektů v tomto kurzu.
    - **Vytvořte adresář pro řešení**: ponechejte nastavení (výchozí).
    - **Vytvoření nového úložiště Git**: tuto možnost vyberte (což je zrušte ve výchozím nastavení), aby Visual Studio vytvoří místní úložiště Git, když vytváří řešení.

1. Po chvíli, vyzve aplikace Visual Studio se dialogové okno s oznámením "Tento projekt vyžaduje externí balíčky" (zobrazené dole). Toto dialogové okno se zobrazí, protože obsahuje šablony `requirements.txt` souboru odkazující na nejnovější balíček 1.x Django. (Vyberte **zobrazit požadované balíčky** zobrazíte přesný závislosti.)

    ![Výzva o tom, že aby se projekt vyžaduje externí balíčky](media/django/step01-requirements-prompt-install-myself.png)

1. Vyberte možnost **I je nainstaluje sám**. Můžete vytvořit virtuální prostředí krátce a ujistěte se, že je vyloučen z řízení zdrojů. (V prostředí může být vytvořena vždy z `requirements.txt`.)

## <a name="step-1-2-examine-the-git-controls-and-publish-to-a-remote-repository"></a>Krok 1 – 2: Zkontrolujte ovládací prvky Git a publikovat do vzdáleného úložiště

Vzhledem k tomu, že jste vybrali **vytvoření nového úložiště Git** v **nový projekt** dialogu projekt již byla potvrzena ke správě místního zdrojového kódu po dokončení procesu vytváření. V tomto kroku je seznámit s ovládacími prvky Git sady Visual Studio a **Team Explorer** okno, ve kterém pracujete se správa zdrojového kódu.

1. Zkontrolujte Git ovládacích prvků v pravém dolním rohu hlavního okna Visual Studio. Tyto ovládací prvky zleva doprava zobrazit unpushed potvrzení, nepotvrzené změny, název úložiště a aktuální větev:

    ![Ovládací prvky Git v okně Visual Studio](media/django/step01-git-controls.png)

    > [!Note]
    > Pokud nevyberete **vytvoření nového úložiště Git** v **nový projekt** zobrazit dialogové okno, ovládací prvky Git pouze **přidat do správy zdrojového** příkaz, který vytvoří místní úložiště.
    >
    > ![Přidat do správy zdrojového kódu se zobrazí v sadě Visual Studio, pokud vytvořili není úložiště](media/django/step01-git-add-to-source-control.png)

1. Vyberte tlačítko změn a otevře se Visual Studio jeho **Team Explorer** okno na **změny** stránky. Protože nově vytvořený projekt již byla potvrzena jako zdroj ovládacího prvku automaticky, nevidíte všechny čekající změny.

    ![Okno Průzkumníka týmových na stránce změny](media/django/step01-team-explorer-changes.png)

1. Na stavovém řádku Visual Studio, vyberte tlačítko unpushed potvrzení (na šipku nahoru s "2") otevřete **synchronizace** stránky v **Team Explorer**. Protože máte pouze místní úložiště, stránce poskytuje snadno možnosti publikovat úložiště do jiné vzdálené úložiště.

    ![Team Explorer okno zobrazuje dostupné Git možnostech úložiště pro správy zdrojového kódu](media/django/step01-team-explorer.png)

    Můžete použít kteroukoli služby, které chcete použít pro vlastní projekty. Tento kurz ukazuje použití Githubu, kde dokončené ukázkový kód pro tento kurz se udržuje v [Microsoft nebo python – ukázka vs další django](https://github.com/Microsoft/python-sample-vs-learn-django) úložiště.

1. Při výběru některé z **publikovat** ovládací prvky, **Team Explorer** vás vyzve k zadání další informace. Například při publikování ukázky v tomto kurzu, úložiště, samotné bylo nutné vytvořit nejprve v takovém případě **Push do vzdáleného úložiště** možnost byl použit s adresou URL v úložišti.

    ![Okno Průzkumníka týmových pro vkládání do existující vzdáleného úložiště](media/django/step01-push-to-github.png)

    Pokud nemáte existující úložiště, **publikovat na webu GitHub** a **nabízená Visual Studio Team Services** možnosti umožňují vytvořit přímo v sadě Visual Studio.

1. Získáte jako absolvování tohoto kurzu, která podporují pravidelně použití ovládacích prvků v sadě Visual Studio pro potvrzení a posílejte nabízená oznámení změny. V tomto kurzu bude zobrazeno v příslušné body.

> [!Tip]
> Rychle přejděte v rámci **Team Explorer**, vyberte záhlaví (který čte "Změn" nebo "Push" v obrázcích výše) zobrazí automaticky otevírané okno nabídky stránky k dispozici.

### <a name="question-what-are-some-advantages-of-using-source-control-from-the-beginning-of-a-project"></a>Otázka: Co jsou některé výhody použití správy zdrojového kódu od začátku projektu?

Odpověď: První řadě pomocí správy zdrojového kódu od začátku, zejména pokud používáte vzdáleného úložiště, poskytuje regulární mimo pracoviště zálohy projektu. Na rozdíl od Údržba projektu jenom na místním systému souborů, správy zdrojového kódu poskytuje taky historie dokončení změn a snadno možnost vrátit jeden soubor nebo celý projekt do předchozího stavu. Který historie změn pomáhá určit příčinu regresí (selhání při testu). Kromě toho je nutné více uživatelů práci projektu, jako spravuje přepíše a poskytuje řešení konfliktů řízení zdrojů. Nakonec zdrojového kódu, což je zásadně způsob automatizace, nastaví je vhodné pro automatizaci sestavení, testování a správu verzí. Je ve skutečnosti prvním krokem při použití DevOps pro projekt, a protože překážky vstupu jsou tak nízké, skutečně neexistuje žádný důvod k není použití správy zdrojového kódu od začátku.

Další informace na zdrojového kódu jako automatizace, najdete v článku [zdroj pravdivosti: z úložiště Role v DevOps](https://msdn.microsoft.com/magazine/mt763232), článek v časopise MSDN napsané pro mobilní aplikace, který platí také pro webové aplikace.

### <a name="question-can-i-prevent-visual-studio-from-auto-committing-a-new-project"></a>Otázka: Můžete zabránit Visual Studio automaticky potvrzení nového projektu?

Odpověď: Ano. Chcete-li zakázat automatické potvrzení, přejděte na **nastavení** stránky v **Team Explorer**, vyberte **Git** > **globální nastavení**, zrušte možnost s názvem bez přípony **potvrzení změn ve výchozím nastavení po sloučení**, pak vyberte **aktualizace**.

## <a name="step-1-3-create-the-virtual-environment-and-exclude-it-from-source-control"></a>Krok 1 – 3: Vytvořte virtuální prostředí a vyloučit od správy zdrojového kódu

Nyní, když jste nakonfigurovali zdrojového kódu pro svůj projekt, můžete vytvořit virtuální prostředí potřebné balíčky Django, které vyžaduje projekt. Pak můžete použít **Team Explorer** vyloučit složky v prostředí od správy zdrojového kódu.

1. V **Průzkumníku řešení**, klikněte pravým tlačítkem myši **prostředí Python** uzel a vyberte možnost **Přidání virtuálního prostředí**.

    ![Přidat virtuální prostředí příkaz v Průzkumníku řešení](media/django/step01-add-virtual-environment-command.png)

1. **Přidání virtuálního prostředí** dialogové okno se zobrazí se zpráva, že "Zjistili jsme soubor requirements.txt." Tato zpráva znamená, že Visual Studio použije tento soubor ke konfiguraci virtuálního prostředí.

    ![Přidání virtuálního prostředí dialogové okno se zprávou requirements.txt](media/django/step01-add-virtual-environment-found-requirements.png)

1. Vyberte **vytvořit** přijměte výchozí hodnoty. (Můžete změnit název virtuálního prostředí Pokud chcete, který právě změní název její podsložce, ale `env` je standardní konvence.)

1. Souhlasit s oprávněními správce, pokud se zobrazí výzva, pak být pacienta několik minut, než Visual Studio stáhne a nainstaluje balíčky, takže pro Django rozšiřování několika tisíc souborů v o tolik podsložky! Zobrazí se průběh v sadě Visual Studio **výstup** okno. Během čekání, všechny oddíly otázky, které následují.

1. Na Visual Studio Git ovládacích prvků (na stavovém řádku), vyberte indikátor změn (který ukazuje "99 *"). otevře **změny** stránky v **Team Explorer**.

    Vytvoření virtuálního prostředí v změn uvést do režimu, ale nepotřebujete k zahrnutí všech z nich ve správě zdrojového kódu, protože vy (nebo každý, kdo jinak klonování projekt) můžete vždy znovu vytvořit prostředí z `requirements.txt`.

    Vyloučit virtuální prostředí, klikněte pravým tlačítkem myši `env` složky a vyberte **ignorovat tyto místní položky**.

    ![Ignoruje virtuálního prostředí v změny řízení zdrojů](media/django/step01-ignore-local-items.png)

1. Po vyloučení virtuální prostředí, jsou jenom zbývající změny do souboru projektu a `.gitignore`. `.gitignore` Soubor obsahuje položku přidané složky virtuálního prostředí. Poklepáním na soubor zobrazíte rozdíl

1. Zadejte zprávu o potvrzení a vyberte **potvrzení všechny** tlačítko, pak pokud chcete push potvrzení do vzdáleného úložiště.

### <a name="question-why-do-i-want-to-create-a-virtual-environment"></a>Otázka: Proč je vhodné vytvořit virtuální prostředí?

Odpověď: Virtuální prostředí je skvělým způsobem, jak izolovat přesný závislostí vaší aplikace. Takové izolace zabraňuje konflikty v rámci globální prostředí Python a pomůcky testování a spolupráci. V čase když budete vyvíjet aplikace, vždy přepnutím v libovolné číslo mnoho užitečné balíčků Python. Udržováním balíčků ve virtuálním prostředí specifické pro projekt, můžete snadno aktualizovat projektu `requirements.txt` soubor, který popisuje prostředí, který je součástí zdrojového kódu. Po zkopírování projektu jiných počítačích, včetně servery sestavení, nasazení serverů a dalších počítačů vývoj, je snadno znovu vytvořit prostředí pomocí pouze `requirements.txt` (což je proto prostředí nemusí být ve správě zdrojového kódu). Další informace najdete v tématu [pomocí virtuální prostředí](selecting-a-python-environment-for-a-project.md#using-virtual-environments).

### <a name="question-how-do-i-remove-a-virtual-environment-thats-already-committed-to-source-control"></a>Otázka: Jak odebrat virtuální prostředí, které je již potvrzen do správy zdrojového kódu?

Odpověď: První, upravit vaše `.gitignore` souborů k vyloučení složky: najděte část s komentářem na konci `# Python Tools for Visual Studio (PTVS)` a přidejte nový řádek pro složky, do virtuálního prostředí, například `/BasicProject/env`. (Vzhledem k tomu, že sada Visual Studio nezobrazuje souboru v **Průzkumníku řešení**, otevřete ho přímo pomocí **soubor** > **otevřete**  >   **Soubor** příkazu nabídky. Můžete také otevřít soubor z **Team Explorer**: na **nastavení** vyberte **nastavení úložiště**, přejděte na **Ignorovat & atributy souborů** části a pak vyberte **upravit** vedle `.gitignore`.)

Druhý, otevřete okno příkazového řádku, přejděte do složky, jako je `BasicProject` obsahující složce virtuální prostředí, jako `env`a spusťte `git rm -r env`. Potom tyto změny potvrdit z příkazového řádku (`git commit -m 'Remove venv'`) nebo potvrzení z **změny** stránka **Team Explorer**.

## <a name="step-1-4-examine-the-boilerplate-code"></a>Krok 1 – 4: Kontrola standardní kódu

Po vytvoření projektu dokončí, zkontrolujte často používaný kód projektu Django (což je znovu, stejně jako generované rozhraní příkazového řádku příkaz `django-admin startproject <project_name>`).

1. Ve vašem projektu kořenová je `manage.py`, Django nástroj příkazového řádku pro správu, Visual Studio automaticky nastaví jako spouštěcí soubor projektu. Spusťte nástroj na příkazovém řádku pomocí `python manage.py <command> [options]`. Pro běžné úlohy, Django Visual Studio poskytuje příkazy pohodlný nabídky. Klikněte pravým tlačítkem na projekt v **Průzkumníku řešení** a vyberte **Python** k najdete v seznamu. Některé z těchto příkazů v průběhu tohoto kurzu narazíte.

    ![Místní nabídky projektu Django příkazů na Python](media/django/step01-django-commands-menu.png)

1. Ve vašem projektu do složky se stejným názvem jako projekt. Obsahuje základní soubory projektu Django:

    - `__init.py`: prázdný soubor Python říká, že tato složka je balíček Python.
    - `wsgi.py`: vstupní bod pro webové servery kompatibilní s WSGI k obsluze projektu. Tento soubor jako obvykle necháte-jako poskytuje háky pro provozní webové servery.
    - `settings.py`: obsahuje nastavení pro projekt Django, který upravíte v průběhu vývoje webové aplikace.
    - `urls.py`: obsahuje obsah pro projekt Django, která můžete také upravit v průběhu vývoje.

    ![Soubory projektu Django v Průzkumníku řešení](media/django/step01-django-project-in-solution-explorer.png)

1. Jak již bylo uvedeno dříve, šablony sady Visual Studio také přidá `requirements.txt` souboru do projektu zadání závislost balíčku Django. Přítomnost tento soubor je co vyzve k vytvoření virtuálního prostředí, při prvním vytvoření projektu.

### <a name="question-can-visual-studio-generate-a-requirementstxt-file-from-a-virtual-environment-after-i-install-other-packages"></a>Otázka: Můžete sady Visual Studio generovat soubor requirements.txt z virtuálního prostředí po instalaci dalších balíčků?

Odpověď: Ano. Rozbalte **prostředí Python** uzel, klikněte pravým tlačítkem na virtuální prostředí a vyberte **generovat soubor requirements.txt** příkaz. Jeho dobré pravidelně použít tento příkaz jako můžete upravit prostředí a potvrzení změny `requirements.txt` do správy zdrojového kódu spolu s další změny kódu, které jsou závislé na tomto prostředí. Pokud jste nastavili průběžnou integraci na serveru, sestavení, měl generovat soubor a provést změny, vždy, když upravíte prostředí.

## <a name="step-1-5-run-the-empty-django-project"></a>Krok 1 – 5: Spusťte prázdný projekt Django

1. V sadě Visual Studio, vyberte **ladění** > **spustit ladění** (F5) nebo pomocí **Webový Server** tlačítka na panelu nástrojů (prohlížeč, najdete v části mohou lišit):

    ![Spustit webový server tlačítka panelu nástrojů v sadě Visual Studio](media/django/run-web-server-toolbar-button.png)

1. Spuštěný server znamená spuštěním příkazu `manage.py runserver <port>`, který spustí Django na předdefinované vývojový server. Pokud Visual Studio říká "Selhání spuštění ladicího programu" zpráva o nutnosti žádný soubor spuštění, klikněte pravým tlačítkem na `manage.py` v **Průzkumníku řešení** a vyberte **nastavit jako spouštěcí soubor**.

1. Při spuštění serveru se zobrazí okno konzoly otevřete to také zobrazí v protokolech serveru. Visual Studio automaticky otevře prohlížeč na `http://localhost:<port>`. Protože projekt Django nemá žádné aplikace, ale Django zobrazuje pouze výchozí stránku aby vzali na vědomí, že je nutné, pokud funguje bez problémů:

    ![Zobrazení výchozí projekt Django](media/django/step01-first-run-success.png)

1. Když jste hotovi, stop pro server ukončením okna konzoly, nebo pomocí **ladění** > **Zastavte ladění** příkazu v sadě Visual Studio.

### <a name="question-is-django-a-web-server-as-well-as-a-framework"></a>Otázka: Je Django webového serveru, jakož i rozhraní?

Odpověď: Ano a ne. Django mít integrovanou webový server, který se používá pro účely vývoje. Tento webový server je co získá použít při spuštění webové aplikace místně, jako např. kdy ladění v sadě Visual Studio. Když nasadíte hostitele webu, ale Django používá webový server hostitele místo. `wsgi.py` Modulu v projektu Django postará zapojování do provozních serverů.

### <a name="question-whats-the-difference-between-using-the-debug-menu-commands-and-the-server-commands-on-the-projects-python-submenu"></a>Otázka: Jaký je rozdíl mezi používat příkazy server a příkazy nabídky ladění z projektu Python podnabídky?

Odpověď: k **ladění** příkazy nabídek a tlačítka panelu nástrojů můžete spustit na serveru pomocí **Python** > **serverem** nebo **Python** > **spustit ladění serveru** příkazů v nabídce kontextu projektu. Oba příkazy otevřete okno konzoly, ve kterém se zobrazí místní adresa URL (localhost:port) serveru spuštěná. Ale musíte ručně otevře prohlížeč s tuto adresu URL a serverem ladění nespustí automaticky ladicího programu sady Visual Studio. Můžete připojit ladicí program na běžící proces později, pokud chcete, pomocí **ladění** > **připojit k procesu** příkaz.

## <a name="next-steps"></a>Další kroky

V tomto okamžiku základní projekt Django neobsahuje žádné aplikace. Vytvoření aplikace v dalším kroku. Vzhledem k tomu obvykle pracujete s více než projekt Django Django aplikace, nebude potřebujete vědět víc o souborech, často používaný v současné době.

> [!div class="nextstepaction"]
> [Vytvoření aplikace Django s zobrazení a šablony stránky](learn-django-in-visual-studio-step-02-create-an-app.md)

## <a name="going-deeper"></a>Budete hlubší

- Kód projektu Django: [zápis první aplikace Django, část 1](https://docs.djangoproject.com/en/2.0/intro/tutorial01/) (docs.djangoproject.com)
- Nástroj pro správu: [správce django a manage.py](https://docs.djangoproject.com/en/2.0/ref/django-admin/) (docs.djangoproject.com)
- Kurz zdrojového kódu na Githubu: [Microsoft nebo python – ukázka vs další django](https://github.com/Microsoft/python-sample-vs-learn-django)
