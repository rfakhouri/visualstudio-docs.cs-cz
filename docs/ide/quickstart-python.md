---
title: "Rychlý úvod: použijte sadu Visual Studio k vytvoření první webové aplikace Python | Microsoft Docs"
description: "Krátký úvod k použití v sadě Visual Studio, který sestaví jednoduché webové aplikace pomocí rozhraní Falcon Python."
ms.custom: 
ms.date: 01/08/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-acquisition
ms.tgt_pltfrm: 
ms.topic: quickstart
ms.devlang: python
author: kraigb
ms.author: kraigb
manager: ghogen
dev_langs: python
ms.workload:
- python
- data-science
ms.openlocfilehash: 684cbe21a7f6454549d2e014682533697306152b
ms.sourcegitcommit: 11740fed01cc602252ef698aaa11c07987b00570
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/12/2018
---
# <a name="quickstart-use-visual-studio-to-create-your-first-python-web-app"></a>Rychlý úvod: použijte sadu Visual Studio k vytvoření první webové aplikace Python

V tento úvod 5 až 10 minut v sadě Visual Studio integrované vývojové prostředí (IDE) vytvoříte jednoduchou webovou aplikaci Python. Pokud jste ještě nenainstalovali Visual Studio, nainstalovat zdarma [zde](http://www.visualstudio.com).

## <a name="create-the-project"></a>Vytvoření projektu

1. Otevřete Visual Studio 2017.

1. Z panelu horní nabídce zvolte **soubor > Nový > projekt...** .

1. V **nový projekt** dialogové okno, v levém podokně rozbalte **nainstalovaná**, pak vyberte **Python**.

1. V prostředním podokně vyberte **webového projektu**, projekt pojmenujte jako "HelloPython", a potom vyberte **OK**.

    ![Dialogové okno Nový projekt s vybraným webovým projektem Python](media/quickstart-python-00-web-project.png)

    Pokud nevidíte šablony projektů jazyka Python, zrušit mimo **nový projekt** dialogové okno a z panelu horní nabídce zvolte **nástroje > funkcí a nástrojů pro získání...**  Chcete-li spustit instalační program Visual Studio. Vyberte **vývoj Python** zatížení, zvolte **upravit**.

    ![Python vývoj zatížení v instalačním programu sady Visual Studio](../python/media/installation-python-workload.png)

1. Nový projekt se otevře v **Průzkumníku řešení** v pravém podokně. Projekt je v tomto okamžiku prázdná, protože neobsahuje žádné další soubory.

    ![Průzkumník řešení zobrazující nově vytvořený prázdný projekt](media/quickstart-python-01-empty-project.png)

**Otázka, na co je výhodou vytvoření projektu v sadě Visual Studio pro aplikaci Python?**

Odpověď: Python aplikace jsou obvykle definovány pomocí pouze složky a soubory, ale může být tato struktura složitá, jak je aplikace, se zvětšit a případně zahrnují automaticky generovaný soubory JavaScript pro webové aplikace a tak dále. Projekt sady Visual Studio pomáhá spravovat Tato složitost. Projekt ( `.pyproj` souboru) identifikuje všechny zdroje a soubory obsahu přidružené k projektu, obsahuje informace o sestavení pro každý soubor, udržuje informace o integraci se systémy správy zdrojového kódu a pomáhá uspořádat vaší aplikace do logické součásti.

## <a name="install-the-falcon-library"></a>Nainstaluje Falcon knihovny

Webové aplikace v Pythonu téměř vždy použijte jeden z mnoha dostupných knihoven Python pro zpracování nízké úrovně podrobnosti, třeba směrování webových požadavků a odpovědí shaping. Pro tento účel Visual Studio poskytuje řadu šablon pro webové aplikace pomocí rozhraní Bottle, Flask a Django.

V tento rychlý start ale, pomocí knihovny Falcon prostředí proces instalaci balíčku a vytváření webové aplikace od začátku. (Visual Studio v současné době nezahrnuje Falcon konkrétní šablony.) Následující kroky pro jednoduchost, nainstalujte Falcon do výchozího globálního prostředí.

1. Rozbalte **prostředí Python** uzlu v projektu zobrazíte výchozí prostředí pro projekt.

    ![Průzkumník řešení zobrazující výchozí prostředí](media/quickstart-python-02-default-environment.png)

1. Klikněte pravým tlačítkem na prostředí a vyberte **instalovat balíček Python...** . Tento příkaz otevře **prostředí Python** okno na **balíčky** kartě. Do pole vyhledávání zadejte "falcon" a vyberte **"pip nainstalovat falcon" z úložiště PyPI**. Přijměte zobrazování výzev pro oprávnění správce a sledovat **výstup** okna v sadě Visual Studio pro průběh. (Výzva pro zvýšení oprávnění se stane, když se nachází v rámci chráněná oblast složce balíčků pro globální prostředí jako `c:\program files`.)

    ![Instalace Falcon knihovny](media/quickstart-python-03-install-package.png)

1. Po instalaci, zobrazí se v prostředí v **Průzkumníku**, tzn., které můžete použít jeho použití v kódu jazyka Python.

    ![Knihovna falcon nainstalován](media/quickstart-python-04-package-installed.png)

Další informace o Falcon, navštivte [falconframework.org](https://falconframework.org/).

Všimněte si, že místo instalace knihovny v globální prostředí, vývojáři obvykle vytvoříte "virtuální prostředí" do kterého chcete nainstalovat knihovny pro konkrétní projekt. Zahrnout mnoho Python šablony projektů v sadě Visual Studio `requirements.txt` soubor, který obsahuje seznam knihoven, na kterých závisí šabloně. Vytváření projektů z jednoho z těchto šablon aktivuje vytvoření virtuálního prostředí, do které jsou nainstalovány knihovny. Další informace najdete v tématu [prostředí Python - virtuální prostředí](../python/python-environments.md#creating-virtual-environments).

## <a name="add-a-code-file"></a>Přidání souboru kódu

Nyní jste připraveni přidat kousek kód Python implementovat minimální webové aplikace.

1. Klikněte pravým tlačítkem na projekt v **Průzkumníku řešení** a vyberte **Přidat > novou položku...** .

1. V dialogovém okně se zobrazí, vyberte **prázdný soubor Python**, pojmenujte ji `hello.py`a vyberte **přidat**. Visual Studio automaticky otevře soubor v okně editoru. (Obecně **Přidat > novou položku...**  příkaz je skvělý způsob, jak přidat do projektu různé druhy soubory jako šablony položek často poskytují užitečné často používaný kód.)

1. Zkopírujte následující kód a vložte ji do `hello.py`:

    ```python
    import falcon

    # In Falcon, define a class for each resource and define on_* methods
    # where * is any standard HTTP methods in lowercase, such as on_get.

    class HelloResource:
        # In this application, the single HelloResource responds to only GET
        # requests, so it has only an on_get method.

        def on_get(self, req, resp):
            resp.status = falcon.HTTP_200  # 200 is the default
            resp.body = "Hello, Python!"

    # Resources are represented by long-lived class instances
    hello = HelloResource()

    # Instruct Falcon to route / and /hello to HelloResource. If you add
    # other resources, use api.add_route to define the desired
    # resource locators for them.
    api = falcon.API()
    api.add_route('/', hello)
    api.add_route('/hello', hello)

    if __name__ == "__main__":
        # Use Python's built-in WSGI reference implementation to run
        # a web server for the application.
        from wsgiref.simple_server import make_server

        # Run the web server on localhost:8080
        print("Starting web app server")
        srv = make_server('localhost', 8080, api)
        srv.serve_forever()
    ```

1. Po vložení tohoto kódu, Visual Studio může zobrazit vlnovku pod `falcon` na prvním řádku a také pod `wsgiref.simple.server` na řádku 20. Když Visual Studio je stále vytváření databáze IntelliSense pro tyto moduly, zobrazí se tyto ukazatele.

Další informace o Falcon, najdete v článku [rychlý start Falcon](https://falcon.readthedocs.io/en/stable/user/quickstart.html) (falcon.readthedocs.io).

## <a name="run-the-application"></a>Spuštění aplikace

1. Klikněte pravým tlačítkem na `hello.py` v **Průzkumníku řešení** a vyberte **nastavit jako spouštěcí soubor**. Příkaz identifikuje soubor kód ke spuštění v Pythonu při spuštění aplikace.

    ![Nastavení spuštění souboru pro projekt v Průzkumníku řešení](media/quickstart-python-05-set-as-startup-file.png)

1. Klikněte pravým tlačítkem na projekt "Hello Python" **Průzkumníku řešení** a vyberte **vlastnosti**. Vyberte **ladění** kartě a nastavte **číslo portu** vlastnost `8080`. Tento krok zajistí, že Visual Studio spustí prohlížeč s `localhost:8080` místo pomocí náhodný port.

1. Vyberte **ladění > Spustit bez ladění** (Ctrl + F5) a ukládat změny souborů a spuštění aplikace.

1. Příkazové okno se zobrazí zpráva "Server počáteční webové aplikace", pak by měla otevřít okno prohlížeče na `localhost:8080` tam, kde se zobrazí zpráva "Hello, Python!" Požadavek GET zobrazí také v příkazovém okně.

    Pokud prohlížeč nespustí automaticky, spustit prohlížeč a přejděte do `localhost:8080`.)

    Pokud se zobrazí pouze Python interaktivní prostředí v příkazovém okně nebo pokud toto okno bliká na obrazovce stručně, ujistěte se, že jste nastavili `hello.py` jako spouštěcí soubor v kroku 1 výše.

1. Zavřete okno příkaz k zastavení aplikace a pak zavřete okno prohlížeče.

## <a name="next-steps"></a>Další kroky

Blahopřejeme k dokončení tento rychlý start, ve kterém Seznámili jste se trochu Visual Studio IDE s Python. Chcete-li pokračovat s úplnější kurz Python v sadě Visual Studio, včetně použití interaktivních okna, ladění, vizualizace dat a práce s Gitem, vyberte níže uvedené tlačítko.

> [!div class="nextstepaction"]
> [Kurz: Začínáme s Pythonem v sadě Visual Studio](../python/vs-tutorial-01-01.md).

- Další informace o [Python webové šablony aplikace v sadě Visual Studio](../python/template-web.md)
- Další informace o [Python ladění](../python/debugging.md)
- Další informace o [Visual Studio IDE](../ide/visual-studio-ide.md)
