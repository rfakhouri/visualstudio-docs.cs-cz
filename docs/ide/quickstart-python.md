---
title: 'Rychlý start: vytvoření webové aplikace v Pythonu pomocí sady Visual Studio'
description: V tomto rychlém startu pomocí sady Visual Studio a rozhraní Flask k vytvoření jednoduché webové aplikace v Pythonu.
ms.date: 03/07/2019
ms.technology: vs-python
ms.topic: quickstart
author: JoshuaPartlow
ms.author: joshuapa
manager: jillfra
ms.workload:
- python
- data-science
ms.openlocfilehash: cbb06ac800fd21e2354b04fb2e7e46306da7ed72
ms.sourcegitcommit: 44e9b1d9230fcbbd081ee81be9d4be8a485d8502
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/30/2019
ms.locfileid: "70180352"
---
# <a name="quickstart-create-your-first-python-web-app-using-visual-studio"></a>Rychlý start: Vytvoření první webové aplikace v Pythonu pomocí sady Visual Studio

V tomto úvodu 5 až 10 minut do sady Visual Studio jako integrované vývojové prostředí Pythonu vytvoříte jednoduchou webovou aplikaci Python, který je založená na platformě Flask. Vytvoření projektu prostřednictvím diskrétní kroky, které vám pomůžou informace o základní funkce sady Visual Studio.

::: moniker range="vs-2017"

Pokud jste ještě nenainstalovali aplikaci Visual Studio, přejděte [soubory ke stažení Visual Studio](https://visualstudio.microsoft.com/vs/older-downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=vs+2017+download) stránku a nainstalovat zdarma. V instalačním programu, je nutné vybrat **vývoj v jazyce Python** pracovního vytížení.

::: moniker-end

::: moniker range=">=vs-2019"

Pokud jste ještě nenainstalovali aplikaci Visual Studio, přejděte [soubory ke stažení Visual Studio](https://visualstudio.microsoft.com/downloads) stránku a nainstalovat zdarma. V instalačním programu, je nutné vybrat **vývoj v jazyce Python** pracovního vytížení.

::: moniker-end

## <a name="create-the-project"></a>Vytvoření projektu

Následujícím postupem se vytvoří prázdný projekt, který slouží jako kontejner pro aplikace:

::: moniker range="vs-2017"
1. Otevřete Visual Studio 2017.

2. V horní nabídce zvolte **soubor > Nový > projekt**.

3. V **nový projekt** dialogové okno pole, zadejte "Python webový projekt" do vyhledávacího pole v pravém horním rohu, zvolte **webový projekt** v seznamu v prostředním projekt pojmenujte například "HelloPython" a pak zvolte **OK**.

    ![Dialogové okno nového projektu s vybraným webovým projektem Python](media/quickstart-python-00-web-project.png)

    Pokud nevidíte šablony projektů Pythonu, spusťte **instalační program pro Visual Studio**, vyberte možnost **Další** > **Úpravy**, vyberte úlohu **vývoje** v jazyce Python a pak zvolte možnost **Upravit**.

    ![Úloha vývoj v jazyce Python v instalačním programu sady Visual Studio](../python/media/installation-python-workload.png)

4. Otevře se nový projekt v **Průzkumníka řešení** v pravém podokně. Projekt je v tuto chvíli prázdná, protože neobsahuje žádné soubory.

    ![Průzkumník řešení zobrazující nově vytvořený prázdný projekt](media/quickstart-python-01-empty-project.png)
::: moniker-end

::: moniker range=">=vs-2019"
1. Otevřete Visual Studio 2019.
2. Na úvodní obrazovce vyberte **vytvořit nový projekt**.
3. V dialogovém okně **vytvořit nový projekt** zadejte do pole Hledat v horní části text "Python web", v rozevíracím seznamu zvolte **webový projekt** a potom vyberte **Další**:

    ![Vytvořit novou obrazovku projektu s vybraným webovým projektem v Pythonu](media/quickstart-python-00-web-project-2019a.png)

    Pokud nevidíte šablony projektů Pythonu, spusťte **instalační program pro Visual Studio**, vyberte možnost **Další** > **Úpravy**, vyberte úlohu **vývoje** v jazyce Python a pak zvolte možnost **Upravit**.

    ![Úloha vývoj v jazyce Python v instalačním programu sady Visual Studio](../python/media/installation-python-workload.png)

4. V následujícím dialogovém okně **Konfigurace nového projektu** zadejte "HelloPython" pro **název projektu**, zadejte umístění a vyberte **vytvořit**. ( **Název řešení** se automaticky nastaví tak, aby odpovídal **názvu projektu**.)

    ![Dialogové okno Konfigurovat nový projekt](media/quickstart-python-00-web-project-2019b.png)

5. Otevře se nový projekt v **Průzkumníka řešení** v pravém podokně. Projekt je v tuto chvíli prázdná, protože neobsahuje žádné soubory.

    ![Průzkumník řešení zobrazující nově vytvořený prázdný projekt](media/quickstart-python-01-empty-project-2019.png)
::: moniker-end

**Daná Jaké jsou výhody vytvoření projektu v aplikaci Visual Studio pro aplikaci Python?**

**Odpověď**: Aplikace Pythonu se obvykle definují jenom pomocí složek a souborů, ale tato jednoduchá struktura se může zastarat, protože aplikace se stanou větší a možná budou zahrnovat automaticky generované soubory, JavaScript pro webové aplikace atd. Projekt sady Visual Studio pomáhá spravovat Tato složitost. Projekt ( *.pyproj* souboru) identifikuje všechny zdroje a soubory obsahu přidružené k projektu, obsahuje informace o sestavení pro každý soubor, udržuje informace o integraci se systémy správy zdrojového kódu a pomáhá Uspořádejte aplikace do logické součásti.

**Daná Co je "řešení" zobrazené v Průzkumník řešení?**

**Odpověď**: Řešení sady Visual Studio je kontejner, který pomáhá spravovat jeden nebo více souvisejících projektů jako skupinu a ukládá nastavení konfigurace, která nejsou specifická pro projekt. Projekty v řešení lze také odkazovat navzájem, tak, že běží jeden projekt (aplikace v Pythonu) automaticky vytvoří druhý projektu (například rozšíření C++ v aplikaci Python).

## <a name="install-the-flask-library"></a>Nainstalujte knihovnu Flask

Webové aplikace v Pythonu téměř vždy používat jeden z mnoha dostupných knihoven Pythonu ke zpracování podrobnosti nižší úrovně, jako je směrování webových požadavků a tvarování odpovědi. Pro tento účel Visual Studio poskytuje celou řadu šablon pro službu web apps, z nichž jeden použijete později v tomto rychlém startu.

Tady můžete následujícím postupem ji nainstalovat do výchozí "globálního prostředí", který používá Visual Studio pro tento projekt Flask.

::: moniker range="vs-2017"
1. Rozbalte **prostředí Pythonu** uzlu projektu zobrazíte výchozí prostředí pro projekt.

    ![Průzkumník řešení zobrazující výchozího prostředí](media/quickstart-python-02-default-environment.png)

2. Klikněte pravým tlačítkem na prostředí a vyberte **instalovat balíček Pythonu**. Tento příkaz otevře **prostředí Pythonu** na okno **balíčky** kartu.

3. Do vyhledávacího pole zadejte "flask" a vyberte **flask instalace pip z PyPI**. Přijměte všechny vyzve k zadání oprávnění správce a podívejte se **výstup** okna v sadě Visual Studio pro průběh. (Výzva pro zvýšení oprávnění se stane, když se nachází v rámci chráněnou oblast složce balíčků pro globální prostředí, jako jsou *C:\Program Files*.)

    ![Instalace knihovny Flask pomocí pip install](media/quickstart-python-03-install-package.png)
::: moniker-end
::: moniker range=">=vs-2019"
1. Rozbalte **prostředí Pythonu** uzlu projektu zobrazíte výchozí prostředí pro projekt.

    ![Průzkumník řešení zobrazující výchozího prostředí](media/quickstart-python-02-default-environment-2019.png)

2. Klikněte pravým tlačítkem na prostředí a vyberte **Spravovat balíčky Pythonu...** . Tento příkaz otevře okno **prostředí Pythonu** na kartě **Packages (PyPi)** .

3. Do vyhledávacího pole zadejte "baněk". Pokud se objeví baňka pod vyhledávacím polem, můžete tento krok přeskočit. V opačném případě vyberte **Spustit příkaz: Instalační baňka PIP**. Přijměte všechny vyzve k zadání oprávnění správce a podívejte se **výstup** okna v sadě Visual Studio pro průběh. (Výzva pro zvýšení oprávnění se stane, když se nachází v rámci chráněnou oblast složce balíčků pro globální prostředí, jako jsou *C:\Program Files*.)

    ![Instalace knihovny Flask pomocí pip install](media/quickstart-python-03-install-package-2019.png)
::: moniker-end

4. Po instalaci, zobrazí se v prostředí v knihovně **Průzkumníka řešení**, což znamená, že, které lze využít v kódu Pythonu.

    ::: moniker range="vs-2017"
    ![Nainstalovanou knihovnu Flask a zobrazení v Průzkumníku řešení](media/quickstart-python-04-package-installed.png)
    ::: moniker-end
    ::: moniker range=">=vs-2019"
    ![Nainstalovanou knihovnu Flask a zobrazení v Průzkumníku řešení](media/quickstart-python-04-package-installed-2019.png)
    ::: moniker-end

> [!Note]
> Místo instalace knihovny do globálního prostředí, vývojáři obvykle "virtuální prostředí vytvořte" ve kterém k instalaci knihoven pro konkrétní projekt. Šablony sady Visual Studio obvykle nabízejí tuto možnost, jak je popsáno v [rychlý start – vytvoření projektu Pythonu pomocí šablony](../python/quickstart-02-python-in-visual-studio-project-from-template.md).

**Daná Kde se dozvím Další informace o dalších dostupných balíčcích Pythonu?**

**Odpověď**: Přejděte na [Rejstřík balíčku Pythonu](https://pypi.org/).

## <a name="add-a-code-file"></a>Přidání souboru kódu

Nyní jste připraveni přidat bitového kódu implementovat minimální webové aplikace v Pythonu.

1. Klikněte pravým tlačítkem na projekt v **Průzkumníka řešení** a vyberte **Přidat > Nová položka**.

1. V zobrazeném dialogu vyberte **prázdný soubor Python**, pojmenujte ho *app.py*a vyberte **přidat**. Visual Studio automaticky otevře soubor v okně editoru.

1. Zkopírujte následující kód a vložte ho do *app.py*:

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

1. Mohli jste si všimnout, který **Přidat > Nová položka** mnoho dalších typů souborů, které můžete přidat do projektu Pythonu, včetně třída Pythonu, balíček Pythonu, test jednotky Pythonu, zobrazí se dialogové *web.config* soubory a další. Obecně tyto šablony položky, jako jsou volány, jsou skvělý způsob, jak rychle vytvořit soubory s užitečné často používaný kód.

**Daná Kde se mohu dozvědět více o baňce?**

**Odpověď**: Přečtěte si dokumentaci k baňce počínaje rychlým [startem baňky](https://flask.palletsprojects.com/en/1.1.x/quickstart/#quickstart).

## <a name="run-the-application"></a>Spuštění aplikace

1. Klikněte pravým tlačítkem na *app.py* v **Průzkumníka řešení** a vyberte **nastavit jako spouštěcí soubor**. Tento příkaz určuje soubor kód ke spuštění pythonu při spuštění aplikace.

    ::: moniker range="vs-2017"
    ![Nastavení spouštěcího souboru pro projekt v Průzkumníku řešení](media/quickstart-python-05-set-as-startup-file.png)
    ::: moniker-end
    ::: moniker range=">=vs-2019"
    ![Nastavení spouštěcího souboru pro projekt v Průzkumníku řešení](media/quickstart-python-05-set-as-startup-file-2019.png)
    ::: moniker-end

2. Klikněte pravým tlačítkem na projekt v **Průzkumníka řešení** a vyberte **vlastnosti**. Vyberte **ladění** kartu a nastavit **číslo portu** vlastnost `4449`. Tento krok zajistí, že Visual Studio spustí prohlížeč s `localhost:4449` tak, aby odpovídaly `app.run` argumenty v kódu.

3. Vyberte **ladit > Spustit bez ladění** (**Ctrl**+**F5**), který uloží změny do souborů aplikace a spustí se.

4. Zobrazí se okno příkazového řádku se zprávou "* používané <https://localhost:4449/>", a mělo by se otevřít okno prohlížeče `localhost:4449` tam, kde se zobrazí zpráva "Hello, Python!" Požadavek na získání se zobrazí také v příkazovém okně se stavem 200.

    Pokud se prohlížeč nespustí automaticky, spustit libovolný prohlížeč a přejděte do `localhost:4449`.

    Pokud se zobrazí pouze Python interaktivního prostředí v příkazovém okně nebo na obrazovce stručně bliká tohoto okna, ujistěte se, že jste nastavili *app.py* jako spouštěcí soubor v kroku 1 výše.

5. Přejděte do `localhost:4449/hello` otestujte, jestli dekoratér pro `/hello` prostředku taky funguje. Požadavek na získání znovu, zobrazí se v příkazovém okně se stavem 200. Nebojte se pokusí zjistit, že v příkazovém okně zobrazí stavový kód 404 některé další také adresu URL.

6. Zavřete příkazové okno a zastavte tak aplikace a potom zavřete okno prohlížeče.

**Daná Jaký je rozdíl mezi příkazem Start bez ladění a spuštěním ladění?**

**Odpověď**: Pomocí možnosti **Spustit ladění** spustíte aplikaci v kontextu [ladicího programu sady Visual Studio](../python/debugging-python-in-visual-studio.md), což vám umožní nastavovat zarážky, kontrolovat proměnné a krokovat kód podle řádku. Aplikace mohou běžet pomaleji v ladicím programu z důvodu různých háky, které usnadňují ladění je to možné. **Spustit bez ladění**, naproti tomu přímo spustí aplikaci, jako kdyby jste spustili z příkazového řádku pomocí žádný kontext ladění a také automaticky spustí prohlížeč a přejde na adresu URL zadanou ve vlastnostech projektu  **Ladění** kartu.

## <a name="next-steps"></a>Další kroky

Blahopřejeme vám k spuštění vaší první aplikace v Pythonu v sadě Visual Studio, v kterých jste se naučili o něco o používání sady Visual Studio jako integrované vývojové prostředí Pythonu.

> [!div class="nextstepaction"]
> [Nasaďte aplikaci do služby Azure App Service](../python/publishing-python-web-applications-to-azure-from-visual-studio.md)

Protože jsou poměrně obecné kroky, které jste udělali v rámci tohoto rychlého startu, jste pravděpodobně uhodnout, můžete a by mělo být automatické. Tato automatizace je role šablony projektů Visual Studio. Projděte si [rychlý start – vytvoření projektu Pythonu pomocí šablony](../python/quickstart-02-python-in-visual-studio-project-from-template.md) ukázku, která vytvoří webovou aplikaci, podobně jako jste vytvořili v tomto článku, ale s použitím méně kroků.

Pokud chcete pokračovat v úplném kurzu na Pythonu v aplikaci Visual Studio, včetně použití interaktivního okna, ladění, vizualizace dat a práce s Git, [Projděte si kurz: Začněte s Pythonem v aplikaci Visual](../python/tutorial-working-with-python-in-visual-studio-step-01-create-project.md)Studio.

Teď prozkoumáme i další, má Visual Studio nabízí, vyberte níže uvedených odkazů.

- Další informace o [webová aplikace šablony v sadě Visual Studio v Pythonu](../python/python-web-application-project-templates.md).
- Další informace o [ladění Pythonu](../python/debugging-python-in-visual-studio.md)
- Další informace o [Visual Studio IDE](../get-started/visual-studio-ide.md) obecně.
