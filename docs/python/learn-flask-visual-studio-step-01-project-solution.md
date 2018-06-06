---
title: Kurz – další Flask v sadě Visual Studio, krok 1
description: Návod Flask základy v kontextu projektů sady Visual Studio.
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
ms.openlocfilehash: 2420beaa7f200ca281e04189667c1534e2a0f991
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34752496"
---
# <a name="tutorial-step-1-get-started-with-the-flask-web-framework-in-visual-studio"></a>Kurz – krok 1: Začínáme s Flask webové rozhraní v sadě Visual Studio

[Flask](http://flask.pocoo.org/) je jednoduché rozhraní Python pro webové aplikace, která poskytuje základy pro směrování adres URL a vykreslování stránky.

Flask se nazývá "micro" rozhraní, protože ji přímo neposkytuje funkcí, jako je ověřování formuláře, databáze abstrakce, ověřování a tak dále. Místo toho poskytuje funkce, speciální balíčků Python Flask názvem *rozšíření*. Rozšíření umožňují snadnou integraci s Flask, aby se zobrazily, jako jsou součástí Flask sám sebe. Například Flask, samotné neposkytuje modul šablony stránky. Ukázka zajišťuje příponami Jinja a Jade, jak je ukázáno v tomto kurzu.

V tomto kurzu se naučíte:

> [!div class="checklist"]
> - Vytvořit základní projekt Flask v úložišti Git pomocí šablony "Prázdný webový projekt Flask" (krok 1)
> - Vytvoření aplikace Flask s jednu stránku a vykreslování této stránce pomocí šablony (krok 2)
> - Statické soubory, přidat stránky a používat šablonu dědičnosti (krok 3)
> - Webový projekt Flask šablonu použít k vytvoření aplikace s více stránek a přizpůsobivý návrh (krok 4)
> - Šablona webový projekt Flask hlasování slouží k vytvoření dotazování aplikaci, která používá celou řadu možností úložiště (úložiště Azure, MongoDB nebo paměť).

V průběhu těchto kroků vytvoříte jeden řešení sady Visual Studio, které obsahuje tři samostatné projekty. Vytvoření projektu pomocí různých šablon projektu Flask, které jsou součástí sady Visual Studio. Udržováním projektů ve stejném řešení, můžete snadno přepínat přepínat mezi různé soubory pro porovnání.

> [!Note]
> V tomto kurzu se liší od [rychlý start Flask](../ide/quickstart-python.md?context=visualstudio/python/default) v tom, že další informace o Flask a jak používat různé Flask šablony projektů, které poskytují rozsáhlejší počáteční bod pro vlastní projekty. Například šablony projektů automaticky nainstalovat balíček Flask při vytvoření projektu, namísto nutnosti k instalaci balíčku ručně, jak je znázorněno v rychlý start.

## <a name="prerequisites"></a>Požadavky

- Visual Studio 2017 v systému Windows se následující možnosti:
  - **Vývoj Python** zatížení (**zatížení** kartě v instalačním programu). Pokyny najdete v tématu [instalaci Python podporují v sadě Visual Studio](installing-python-support-in-visual-studio.md).
  - **Git pro Windows** a **Githubu rozšíření pro Visual Studio** na **jednotlivých součástí** v části **Code nástroje**.

Šablony projektů flask jsou všechny starší verze nástrojů Python Tools pro sadu Visual Studio, i když podrobnosti se můžou lišit od co je popsané v tomto kurzu.

Vývoj Python není podporována v současné době v sadě Visual Studio for Mac. Na Mac a Linux, použijte [rozšíření Python ve Visual Studio Code](https://code.visualstudio.com/docs/python/python-tutorial).

## <a name="step-1-1-create-a-visual-studio-project-and-solution"></a>Krok 1-1: vytvoření projektu Visual Studia a řešení

1. V sadě Visual Studio, vyberte **soubor** > **nový** > **projektu**, vyhledejte "Flask" a vyberte **prázdný webový projekt Flask**  šablony. (Šablona je také najdete v části **Python** > **webové** v seznamu levé straně.)

    ![Dialogové okno Nový projekt v sadě Visual Studio pro prázdný webový projekt Flask](media/flask/step01-new-blank-project.png)

1. Do polí v dolní části dialogové okno, zadejte následující informace (jak je znázorněno na předchozím obrázku) a potom vyberte **OK**:

    - **Název**: nastavte na název projektu sady Visual Studio k "BasicProject". Tento název se taky používá pro projekt Flask.
    - **Umístění**: určení umístění, ve kterém chcete vytvořit řešení sady Visual Studio a projekt.
    - **Název řešení**: nastavte na "LearningFlask", což je vhodné pro řešení jako kontejner pro více projektů v tomto kurzu.
    - **Vytvořte adresář pro řešení**: ponechejte nastavení (výchozí).
    - **Vytvoření nového úložiště Git**: tuto možnost vyberte (což je zrušte ve výchozím nastavení), aby Visual Studio vytvoří místní úložiště Git, když vytváří řešení. Pokud nevidíte tuto možnost, spusťte instalační program Visual Studio 2017 a přidejte Git pro Windows a GitHub rozšíření pro Visual Studio na **jednotlivých součástí** v části **Code nástroje**.

1. Po chvíli, vyzve aplikace Visual Studio se dialogové okno s oznámením "Tento projekt vyžaduje externí balíčky" (zobrazené dole). Toto dialogové okno se zobrazí, protože obsahuje šablony `requirements.txt` souboru odkazující na nejnovější balíček 1.x Flask. (Vyberte **zobrazit požadované balíčky** zobrazíte přesný závislosti.)

    ![Výzva o tom, že aby se projekt vyžaduje externí balíčky](media/tutorials-common/step01-requirements-prompt-install-myself.png)

1. Vyberte možnost **I je nainstaluje sám**. Můžete vytvořit virtuální prostředí krátce a ujistěte se, že je vyloučen z řízení zdrojů. (V prostředí může být vytvořena vždy z `requirements.txt`.)

## <a name="step-1-2-examine-the-git-controls-and-publish-to-a-remote-repository"></a>Krok 1 – 2: Zkontrolujte ovládací prvky Git a publikovat do vzdáleného úložiště

Vzhledem k tomu, že jste vybrali **vytvoření nového úložiště Git** v **nový projekt** dialogu projekt již byla potvrzena ke správě místního zdrojového kódu po dokončení procesu vytváření. V tomto kroku je seznámit s ovládacími prvky Git sady Visual Studio a **Team Explorer** okno, ve kterém pracujete se správa zdrojového kódu.

1. Zkontrolujte Git ovládacích prvků v pravém dolním rohu hlavního okna Visual Studio. Tyto ovládací prvky zleva doprava zobrazit unpushed potvrzení, nepotvrzené změny, název úložiště a aktuální větev:

    ![Ovládací prvky Git v okně Visual Studio](media/flask/step01-git-controls.png)

    > [!Note]
    > Pokud nevyberete **vytvoření nového úložiště Git** v **nový projekt** zobrazit dialogové okno, ovládací prvky Git pouze **přidat do správy zdrojového** příkaz, který vytvoří místní úložiště.
    >
    > ![Přidat do správy zdrojového kódu se zobrazí v sadě Visual Studio, pokud vytvořili není úložiště](media/tutorials-common/step01-git-add-to-source-control.png)

1. Vyberte tlačítko změn a otevře se Visual Studio jeho **Team Explorer** okno na **změny** stránky. Protože nově vytvořený projekt již byla potvrzena jako zdroj ovládacího prvku automaticky, nevidíte všechny čekající změny.

    ![Okno Průzkumníka týmových na stránce změny](media/flask/step01-team-explorer-changes.png)

1. Na stavovém řádku Visual Studio, vyberte tlačítko unpushed potvrzení (na šipku nahoru s "2") otevřete **synchronizace** stránky v **Team Explorer**. Protože máte pouze místní úložiště, stránce poskytuje snadno možnosti publikovat úložiště do jiné vzdálené úložiště.

    ![Team Explorer okno zobrazuje dostupné Git možnostech úložiště pro správy zdrojového kódu](media/flask/step01-team-explorer.png)

    Můžete použít kteroukoli služby, které chcete použít pro vlastní projekty. Tento kurz ukazuje použití Githubu, kde dokončené ukázkový kód pro tento kurz se udržuje v [Microsoft nebo python – ukázka vs-learning-flask](https://github.com/Microsoft/python-sample-vs-learning-flask) úložiště.

1. Při výběru některé z **publikovat** ovládací prvky, **Team Explorer** vás vyzve k zadání další informace. Například při publikování ukázky v tomto kurzu, úložiště, samotné bylo nutné vytvořit nejprve v takovém případě **Push do vzdáleného úložiště** možnost byl použit s adresou URL v úložišti.

    ![Okno Průzkumníka týmových pro vkládání do existující vzdáleného úložiště](media/flask/step01-push-to-github.png)

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

Nyní, když jste nakonfigurovali zdrojového kódu pro svůj projekt, můžete vytvořit virtuální prostředí potřebné balíčky Flask, které vyžaduje projekt. Pak můžete použít **Team Explorer** vyloučit složky v prostředí od správy zdrojového kódu.

1. V **Průzkumníku řešení**, klikněte pravým tlačítkem myši **prostředí Python** uzel a vyberte možnost **Přidání virtuálního prostředí**.

    ![Přidat virtuální prostředí příkaz v Průzkumníku řešení](media/flask/step01-add-virtual-environment-command.png)

1. **Přidání virtuálního prostředí** dialogové okno se zobrazí se zpráva, že "Zjistili jsme soubor requirements.txt." Tato zpráva znamená, že Visual Studio použije tento soubor ke konfiguraci virtuálního prostředí.

    ![Přidání virtuálního prostředí dialogové okno se zprávou requirements.txt](media/tutorials-common/step01-add-virtual-environment-found-requirements.png)

1. Vyberte **vytvořit** přijměte výchozí hodnoty. (Můžete změnit název virtuálního prostředí Pokud chcete, který právě změní název její podsložce, ale `env` je standardní konvence.)

1. Souhlas s oprávněními správce, pokud se zobrazí výzva, pak se pacienta několik minut, zatímco Visual Studio stáhne a nainstaluje balíčky, takže pro Flask a jeho závislosti rozšiřování o tisíce souborů ve více než 100 podsložky. Zobrazí se průběh v sadě Visual Studio **výstup** okno. Během čekání, všechny oddíly otázky, které následují. Popis závislosti na Flask můžete také zjistit na [Flask instalace](http://flask.pocoo.org/docs/1.0/installation/#installation) stránky (flask.pcocoo.org).

1. Na Visual Studio Git ovládacích prvků (na stavovém řádku), vyberte indikátor změn (který ukazuje "99\*"). otevře **změny** stránky v **Team Explorer**.

    Vytvoření virtuálního prostředí v stovky změny uvést do režimu, ale nepotřebujete k zahrnutí všech z nich ve správě zdrojového kódu, protože vy (nebo každý, kdo jinak klonování projekt) můžete vždy znovu vytvořit prostředí z `requirements.txt`.

    Vyloučit virtuální prostředí, klikněte pravým tlačítkem myši `env` složky a vyberte **ignorovat tyto místní položky**.

    ![Ignoruje virtuálního prostředí v změny řízení zdrojů](media/flask/step01-ignore-local-items.png)

1. Po vyloučení virtuální prostředí, jsou jenom zbývající změny do souboru projektu a `.gitignore`. `.gitignore` Soubor obsahuje položku přidané složky virtuálního prostředí. Poklepáním na soubor zobrazíte rozdíl

1. Zadejte zprávu o potvrzení a vyberte **potvrzení všechny** tlačítko, pak pokud chcete push potvrzení do vzdáleného úložiště.

### <a name="question-why-do-i-want-to-create-a-virtual-environment"></a>Otázka: Proč je vhodné vytvořit virtuální prostředí?

Odpověď: Virtuální prostředí je skvělým způsobem, jak izolovat přesný závislostí vaší aplikace. Takové izolace zabraňuje konflikty v rámci globální prostředí Python a pomůcky testování a spolupráci. V čase když budete vyvíjet aplikace, vždy přepnutím v libovolné číslo mnoho užitečné balíčků Python. Udržováním balíčků ve virtuálním prostředí specifické pro projekt, můžete snadno aktualizovat projektu `requirements.txt` soubor, který popisuje prostředí, který je součástí zdrojového kódu. Po zkopírování projektu jiných počítačích, včetně servery sestavení, nasazení serverů a dalších počítačů vývoj, je snadno znovu vytvořit prostředí pomocí pouze `requirements.txt` (což je proto prostředí nemusí být ve správě zdrojového kódu). Další informace najdete v tématu [pomocí virtuální prostředí](selecting-a-python-environment-for-a-project.md#using-virtual-environments).

### <a name="question-how-do-i-remove-a-virtual-environment-thats-already-committed-to-source-control"></a>Otázka: Jak odebrat virtuální prostředí, které je již potvrzen do správy zdrojového kódu?

Odpověď: První, upravit vaše `.gitignore` souborů k vyloučení složky: najděte část s komentářem na konci `# Python Tools for Visual Studio (PTVS)` a přidejte nový řádek pro složky, do virtuálního prostředí, například `/BasicProject/env`. (Vzhledem k tomu, že sada Visual Studio nezobrazuje souboru v **Průzkumníku řešení**, otevřete ho přímo pomocí **soubor** > **otevřete**  >   **Soubor** příkazu nabídky. Můžete také otevřít soubor z **Team Explorer**: na **nastavení** vyberte **nastavení úložiště**, přejděte na **Ignorovat & atributy souborů** části a pak vyberte **upravit** vedle `.gitignore`.)

Druhý, otevřete okno příkazového řádku, přejděte do složky, jako je `BasicProject` obsahující složce virtuální prostředí, jako `env`a spusťte `git rm -r env`. Potom tyto změny potvrdit z příkazového řádku (`git commit -m 'Remove venv'`) nebo potvrzení z **změny** stránka **Team Explorer**.

## <a name="step-1-4-examine-the-boilerplate-code"></a>Krok 1 – 4: Kontrola standardní kódu

1. Po vytvoření projektu dokončí, najdete v části řešení a projektu v **Průzkumníku řešení**, kde projekt obsahuje pouze dva soubory, `app.py` a `requirements.txt`:

    ![Prázdné soubory projektu Flask v Průzkumníku řešení](media/flask/step01-blank-flask-project-in-solution-explorer.png)

1. Jak již bylo uvedeno dříve, `requirements.txt` soubor určuje závislost balíčku Flask. Přítomnost tento soubor je co vyzve k vytvoření virtuálního prostředí, při prvním vytvoření projektu.

1. Jedné `app.py` soubor obsahuje tři části. Nejprve je `import` příkaz pro Flask, vytvoření instance `Flask` třída, která je přiřazená proměnná `app`a pak přiřazení `wsgi_app` proměnné (což je užitečné při nasazování hostitele webu, ale nepoužívá se v současné době):

    ```python
    from flask import Flask
    app = Flask(__name__)

    # Make the WSGI interface available at the top level so wfastcgi can get it.
    wsgi_app = app.wsgi_app
    ```

1. Druhá část na konci souboru, je bit volitelné kód, který spustí vývojový server Flask se konkrétního hostitele a portu hodnoty převzaty z proměnných prostředí (jako výchozí bude použit localhost:5555):

    ```python
    if __name__ == '__main__':
        import os
        HOST = os.environ.get('SERVER_HOST', 'localhost')
        try:
            PORT = int(os.environ.get('SERVER_PORT', '5555'))
        except ValueError:
            PORT = 5555
        app.run(HOST, PORT)
    ```

1. Je třetí krátké bit kódu, který přiřazuje funkce na adresu URL trasy, což znamená, že funkce poskytuje prostředků podle adresy URL. Definování tras pomocí na Flask `@app.route` dekoratéra, jehož argumentem je relativní adresu URL z kořenového adresáře webu. Jak můžete vidět v kódu, vrátí funkce tady jenom textový řetězec, který je dost pro webový prohlížeč k vykreslení. V krocích, které následují vykreslit bohatší stránky s jazykem HTML.

    ```python
    @app.route('/')
    def hello():
        """Renders a sample page."""
        return "Hello World!"
    ```

### <a name="question-what-is-the-purpose-of-the-name-argument-to-the-flask-class"></a>Otázka: co je účelem __název__ argumentu Flask třídy?

Odpověď: Argument je název modulu nebo balíček aplikace a udává Flask, kde má být vyhledán šablony, statické soubory a jiné prostředky, které patří do aplikace. Pro aplikace, které jsou obsažené v modulu single `__name__` je vždy správnou hodnotu. Je také důležité pro rozšíření, které je třeba ladicí informace. Další informace, a další argumenty, najdete v článku [Flask třída dokumentaci](http://flask.pocoo.org/docs/1.0/api/#flask.Flask) (flask.pocoo.org).

### <a name="question-can-a-function-have-more-than-one-route-decorator"></a>Otázka: může funkce mít více než jeden dekoratéra trasy?

Odpověď: Ano, můžete použít libovolný počet dekoratéry tak, jak chcete Pokud stejnou funkci obsluhuje víc tras. Chcete-li například použít `hello` funkce pro obě "/" a "/ hello", použijte následující kód:

```python
@app.route('/')
@app.route('/hello')
def hello():
    """Renders a sample page."""
    return "Hello World!"
```

<a name="qa-url-variables"></a>

### <a name="question-how-does-flask-work-with-variable-url-routes-and-query-parameters"></a>Otázka: jak Flask funguje s proměnné tras adresy URL a parametry dotazu?

Odpověď: V trasu, můžete označit žádné proměnné se `<variable_name>`, a Flask předá proměnná do funkce pomocí pojmenovaného argumentu. Proměnná může být část cesty URL, nebo v parametru dotazu. Například trasu ve formě `'/hello/<name>` generuje argument řetězce názvem `name` funkce a pomocí `?message=<msg>` v trasy, která analyzuje hodnota pro zadané "zpráva =" parametr dotazu a předává je pro funkci jako `msg`:

```python
@app.route('/hello/<name>?message=<msg>')
def hello(name, msg):
    return "Hello " + name + "! Message is " + msg + "."
```

Chcete-li změnit typ, předpony proměnnou s `int`, `float`, `path` (který přijímá lomítka od sebe odděluje názvy složek), a `uuid`. Podrobnosti najdete v tématu [pravidla proměnných](http://flask.pocoo.org/docs/1.0/quickstart/#variable-rules) v dokumentaci k Flask.

Parametry dotazu jsou také k dispozici prostřednictvím `request.args` vlastnost, konkrétně pomocí `request.args.get` metoda. Další informace najdete v tématu [žádost objekt](http://flask.pocoo.org/docs/1.0/quickstart/#the-request-object) v dokumentaci k Flask.

### <a name="question-can-visual-studio-generate-a-requirementstxt-file-from-a-virtual-environment-after-i-install-other-packages"></a>Otázka: Můžete sady Visual Studio generovat soubor requirements.txt z virtuálního prostředí po instalaci dalších balíčků?

Odpověď: Ano. Rozbalte **prostředí Python** uzel, klikněte pravým tlačítkem na virtuální prostředí a vyberte **generovat soubor requirements.txt** příkaz. Jeho dobré pravidelně použít tento příkaz jako můžete upravit prostředí a potvrzení změny `requirements.txt` do správy zdrojového kódu spolu s další změny kódu, které jsou závislé na tomto prostředí. Pokud jste nastavili průběžnou integraci na serveru, sestavení, měl generovat soubor a provést změny, vždy, když upravíte prostředí.

## <a name="step-1-5-run-the-project"></a>Krok 1 – 5: spusťte projekt

1. V sadě Visual Studio, vyberte **ladění** > **spustit ladění** (F5) nebo pomocí **Webový Server** tlačítka na panelu nástrojů (prohlížeč, najdete v části mohou lišit):

    ![Spustit webový server tlačítka panelu nástrojů v sadě Visual Studio](media/tutorials-common/run-web-server-toolbar-button.png)

1. Buď příkaz přiřadí proměnné prostředí PORT číslo náhodných portu a potom spustí `python app.py`. Kód spustí aplikace pomocí tento port v rámci vývojový server Flask společnosti. Pokud Visual Studio říká "Selhání spuštění ladicího programu" zpráva o nutnosti žádný soubor spuštění, klikněte pravým tlačítkem na `app.py` v **Průzkumníku řešení** a vyberte **nastavit jako spouštěcí soubor**.

1. Při spuštění serveru, najdete v okně konzoly otevřete tento zobrazí v protokolech serveru. Visual Studio pak automaticky otevře prohlížeč na `http://localhost:<port>`, kde se měla zobrazit zpráva pro vykreslení `hello` funkce:

    ![Zobrazení výchozí projekt flask](media/flask/step01-first-run-success.png)

1. Když jste hotovi, stop pro server ukončením okna konzoly, nebo pomocí **ladění** > **Zastavte ladění** příkazu v sadě Visual Studio.

### <a name="question-whats-the-difference-between-using-the-debug-menu-commands-and-the-server-commands-on-the-projects-python-submenu"></a>Otázka: Jaký je rozdíl mezi používat příkazy server a příkazy nabídky ladění z projektu Python podnabídky?

Odpověď: k **ladění** příkazy nabídek a tlačítka panelu nástrojů můžete spustit na serveru pomocí **Python** > **serverem** nebo **Python** > **spustit ladění serveru** příkazů v nabídce kontextu projektu. Oba příkazy otevřete okno konzoly, ve kterém se zobrazí místní adresa URL (localhost:port) serveru spuštěná. Ale musíte ručně otevře prohlížeč s tuto adresu URL a serverem ladění nespustí automaticky ladicího programu sady Visual Studio. Můžete připojit ladicí program na běžící proces později, pokud chcete, pomocí **ladění** > **připojit k procesu** příkaz.

## <a name="next-steps"></a>Další kroky

V tomto okamžiku základní projekt Flask obsahuje spuštění kódu a kódu stránky ve stejném souboru. Je nejvhodnější oddělit tyto dva problémy a také oddělit HTML a data pomocí šablony.

> [!div class="nextstepaction"]
> [Vytvoření aplikace Flask s zobrazení a šablony stránky](learn-flask-visual-studio-step-02-create-app.md)

## <a name="going-deeper"></a>Budete hlubší

- [Rychlý start flask](http://flask.pocoo.org/docs/1.0/quickstart/) (flask.pocoo.org)
- Kurz zdrojového kódu na Githubu: [Microsoft nebo python – ukázka vs-learning-flask](https://github.com/Microsoft/python-sample-vs-learning-flask)
