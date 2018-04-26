---
title: 'Rychlý úvod: použijte sadu Visual Studio k vytvoření webové aplikace Python'
description: V tento rychlý start vytvoříte pomocí sady Visual Studio a rozhraní Flask pro vytvoření jednoduché webové aplikace v Pythonu.
ms.date: 03/21/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: quickstart
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: 3c57dab3ac6ca4ee28b568a6fb8004f5559dfed2
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="quickstart-create-your-first-python-web-app-using-visual-studio"></a>Rychlý úvod: Vytvoření první webové aplikace Python pomocí sady Visual Studio

V této 5 až 10 minut Úvod k sadě Visual Studio jako Python IDE vytvoříte jednoduchou webovou aplikaci Python založené na rozhraní framework Flask. Vytvoření projektu prostřednictvím diskrétní kroky, které vám pomůžou získat informace o základních funkcích nástroje Visual Studio.

Pokud jste ještě nenainstalovali Visual Studio, přejděte na [Visual Studio stáhne](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs) instalaci zdarma. V instalačním programu, je nutné vybrat **vývoj Python** zatížení.

## <a name="create-the-project"></a>Vytvoření projektu

Následující postup vytvořit prázdný projekt, který slouží jako kontejner pro aplikaci:

1. Otevřete Visual Studio 2017.

1. V horní nabídce vyberte příkaz **soubor > Nový > projekt**.

1. V **nový projekt** dialogové okno pole zadejte "Python webového projektu" v poli vyhledávání v pravém horním rohu, zvolte **webového projektu** v seznamu střední projekt pojmenujte jako "HelloPython", a potom vyberte **OK**.

    ![Dialogové okno Nový projekt s vybraným webovým projektem Python](media/quickstart-python-00-web-project.png)

    Pokud nevidíte šablony projektů jazyka Python, zrušit mimo **nový projekt** dialogové okno a z panelu horní nabídce zvolte **nástroje > funkcí a nástrojů pro získání** otevřete **Visual Studio Instalační program**. Vyberte **vývoj Python** zatížení, zvolte **upravit**.

    ![Python vývoj zatížení v instalačním programu sady Visual Studio](../python/media/installation-python-workload.png)

1. Nový projekt se otevře v **Průzkumníku řešení** v pravém podokně. Projekt je v tomto okamžiku prázdná, protože neobsahuje žádné další soubory.

    ![Průzkumník řešení zobrazující nově vytvořený prázdný projekt](media/quickstart-python-01-empty-project.png)

**Otázka: Co je výhodou vytvoření projektu v sadě Visual Studio pro aplikaci Python?**

**Odpověď**: Python aplikace jsou obvykle definovány pomocí pouze složky a soubory, ale může stát tato jednoduchá struktura zátěží, jako aplikace, se zvětšit a případně zahrnují automaticky generovaný soubory JavaScript pro webové aplikace a tak dále. Projekt sady Visual Studio pomáhá spravovat Tato složitost. Projekt ( *.pyproj* souboru) identifikuje všechny zdroje a soubory obsahu přidružené k projektu, obsahuje informace o sestavení pro každý soubor, udržuje informace o integraci se systémy správy zdrojového kódu a pomáhá uspořádejte do logických součástí vaší aplikace.

**Otázka: Co je "řešení" zobrazeno v Průzkumníku řešení?**

**Odpověď**: řešení sady Visual Studio A je kontejner, který vám pomůže spravovat pro jeden nebo více souvisejících projekty jako skupina a ukládá nastavení konfigurace, které nejsou specifické pro projekt. Projekty v řešení můžete taky odkazovat navzájem, tak, aby spuštění jeden projektu (aplikace Python) automaticky vytvoří druhý projekt (například příponou C++ použít v aplikaci Python).

## <a name="install-the-flask-library"></a>Nainstaluje knihovny Flask

Webové aplikace v Pythonu téměř vždy použijte jeden z mnoha dostupných knihoven Python pro zpracování nízké úrovně podrobnosti, třeba směrování webových požadavků a odpovědí shaping. Pro tento účel Visual Studio poskytuje řadu šablon pro webové aplikace, z nichž jeden použijete později v tento rychlý start.

Zde tyto kroky použijete k instalaci knihovny Flask do výchozí "globální prostředí" používaný pro tento projekt sady Visual Studio.

1. Rozbalte **prostředí Python** uzlu v projektu zobrazíte výchozí prostředí pro projekt.

    ![Průzkumník řešení zobrazující výchozí prostředí](media/quickstart-python-02-default-environment.png)

1. Klikněte pravým tlačítkem na prostředí a vyberte **instalovat balíček Python**. Tento příkaz otevře **prostředí Python** okno na **balíčky** kartě.

1. Do pole vyhledávání zadejte "flask" a vyberte **pip nainstalovat flask z úložiště PyPI**. Přijměte zobrazování výzev pro oprávnění správce a sledovat **výstup** okna v sadě Visual Studio pro průběh. (Výzva pro zvýšení oprávnění se stane, když se nachází v rámci chráněná oblast složce balíčků pro globální prostředí jako *C:\Program Files*.)

    ![Instalace Flask knihovny](media/quickstart-python-03-install-package.png)

1. Po instalaci, zobrazí se v prostředí v **Průzkumníku**, tzn., které můžete použít jeho použití v kódu jazyka Python.

    ![Knihovna flask nainstalován](media/quickstart-python-04-package-installed.png)

> [!Note]
> Místo instalace knihovny v globální prostředí, vývojáři obvykle vytvoříte "virtuální prostředí" do kterého chcete nainstalovat knihovny pro konkrétní projekt. Šablony sady Visual Studio obvykle nabízejí tuto možnost, jak je popsáno v [rychlý start - vytvořte projekt Python pomocí šablony](../python/quickstart-02-python-in-visual-studio-project-from-template.md).

**Otázka: Kde I Další informace o dalších dostupných balíčků Python?**

**Odpověď**: přejděte [indexu balíčků Pythonu](https://pypi.python.org/pypi).

## <a name="add-a-code-file"></a>Přidání souboru kódu

Nyní jste připraveni přidat kousek kód Python implementovat minimální webové aplikace.

1. Klikněte pravým tlačítkem na projekt v **Průzkumníku řešení** a vyberte **Přidat > Nová položka**.

1. V dialogovém okně se zobrazí, vyberte **prázdný soubor Python**, pojmenujte ji *app.py*a vyberte **přidat**. Visual Studio automaticky otevře soubor v okně editoru.

1. Zkopírujte následující kód a vložte ji do *app.py*:

    ```python
    from flask import Flask

    # Create an instance of the Flask class that is the WSGI application.
    # The first argument is the name of the application module or package,
    # typically __name__ when using a single module.
    app = Flask(__name__)

    # Flask route decorators map / and /hello to the hello function.
    # To add other resources, create functions that generate the page contents
    # and add decorators to define the appropriate resource locators for them.

    @app.route('/')
    @app.route('/hello')
    def hello():
        # Render the page
        return "Hello Python!"

    if __name__ == '__main__':
        # Run the app server on localhost:4449
        app.run('localhost', 4449)
    ```

1. Jste si všimli, **Přidat > Nová položka** dialogové okno zobrazí mnoho dalších typů souborů, které můžete přidat do projektu Python, včetně třídu Python, balíček Python, testování částí Python, *web.config* soubory a další. Tyto šablony položky, jako nazývají, jsou obecně skvělý způsob, jak rychle vytvořit soubory s užitečné často používaný kód.

**Otázka: Kde I Další informace o Flask?**

**Odpověď**: naleznete v dokumentaci Flask, počínaje [rychlý start Flask](http://flask.pocoo.org/docs/0.12/quickstart/#quickstart).

## <a name="run-the-application"></a>Spuštění aplikace

1. Klikněte pravým tlačítkem na *app.py* v **Průzkumníku řešení** a vyberte **nastavit jako spouštěcí soubor**. Tento příkaz identifikuje soubor kód ke spuštění v Pythonu při spuštění aplikace.

    ![Nastavení spuštění souboru pro projekt v Průzkumníku řešení](media/quickstart-python-05-set-as-startup-file.png)

1. Klikněte pravým tlačítkem na projekt v **Průzkumníku řešení** a vyberte **vlastnosti**. Vyberte **ladění** kartě a nastavte **číslo portu** vlastnost `4449`. Tento krok zajistí, že Visual Studio spustí prohlížeč s `localhost:4449` tak, aby odpovídala `app.run` argumenty v kódu.

1. Vyberte **ladění > Spustit bez ladění** (**Ctrl**+**F5**), který uloží změny do soubory a spustí aplikace.

1. Zobrazí se okno příkazového řádku se zprávou "* spuštěné v https://localhost:4449/", a otevřít okno prohlížeče na `localhost:4449` tam, kde se zobrazí zpráva, "Hello, Python!" Požadavek GET se zobrazí také v příkazovém okně se stavem 200.

    Pokud prohlížeč nespustí automaticky, spustit prohlížeč a přejděte do `localhost:4449`.

    Pokud se zobrazí pouze Python interaktivní prostředí v příkazovém okně nebo pokud toto okno bliká na obrazovce stručně, ujistěte se, že jste nastavili *app.py* jako spouštěcí soubor v kroku 1 výše.

1. Přejděte na `localhost:4449/hello` otestujte, jestli dekoratéra pro `/hello` prostředku taky funguje. Požadavek GET zobrazí znovu, se v příkazovém okně se stavem 200. Nebojte se, že některé jiné také adresu URL pokusí zjistěte, zda zobrazují 404 stavové kódy v příkazovém okně.

1. Zavřete okno příkaz k zastavení aplikace a pak zavřete okno prohlížeče.

**Otázka: Jaký je rozdíl mezi příkaz Spustit bez ladění a spustit ladění?**

**Odpověď**: použijete **spustit ladění** a spusťte aplikaci v kontextu [ladicího programu sady Visual Studio](../python/debugging-python-in-visual-studio.md), umožňuje nastavit zarážky, zkontrolujte proměnné a krokovat kód řádek po řádku. Aplikace může pomaleji v ladicím programu z důvodu různých háky, které umožňují, ladění. **Spustit bez ladění**, naproti tomu spustí aplikaci přímo jako v případě, že jste spustili z příkazového řádku, bez ladění kontextu a také automaticky spustí prohlížeč a přejde na adresu URL zadanou ve vlastnostech projektu  **Ladění** kartě.

## <a name="next-steps"></a>Další kroky

Blahopřejeme k spuštění vaší první aplikace Python ze sady Visual Studio, ve které jste se naučili o něco o pomocí sady Visual Studio jako Python IDE!

Protože jsou poměrně obecné kroky, které jste udělali v tento rychlý start, jste pravděpodobně uhádnout, můžete a dobré automatizovat. Tato automatizace je role šablony projektů Visual Studio. Vyberte tlačítko pro ukázku, která vytvoří webovou aplikaci podobnou té, kterou jste vytvořili v tomto článku, ale s méně kroků.

> [!div class="nextstepaction"]
> [Rychlý start - vytvořte projekt Python pomocí šablony](../python/quickstart-02-python-in-visual-studio-project-from-template.md)

Chcete-li pokračovat s úplnější kurz Python v sadě Visual Studio, včetně použití interaktivních okna, ladění, vizualizace dat a práce s Gitem, vyberte níže uvedené tlačítko.

> [!div class="nextstepaction"]
> [Kurz: Začínáme s Pythonem v sadě Visual Studio](../python/tutorial-working-with-python-in-visual-studio-step-01-create-project.md)

Chcete-li prozkoumat více, že nabídka má Visual Studio, vyberte odkazy níže.

- Další informace o [Python webové šablony aplikace v sadě Visual Studio](../python/python-web-application-project-templates.md).
- Další informace o [Python ladění](../python/debugging-python-in-visual-studio.md)
- Další informace o [Visual Studio IDE](../ide/visual-studio-ide.md) obecně.
