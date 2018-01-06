---
title: "Rychlý úvod: použijte sadu Visual Studio k vytvoření první webové aplikace Python | Microsoft Docs"
ms.custom: 
ms.date: 12/1/2017"
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
ms.workload: python
ms.openlocfilehash: bf0a6e187a98a03d3beed33537fe5244ecd5d35d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="quickstart-use-visual-studio-to-create-your-first-python-web-app"></a>Rychlý úvod: použijte sadu Visual Studio k vytvoření první webové aplikace Python

V tento úvod 5 až 10 minut v sadě Visual Studio integrované vývojové prostředí (IDE) vytvoříte jednoduchou webovou aplikaci Python. Pokud jste ještě nenainstalovali Visual Studio, nainstalovat zdarma [zde](http://www.visualstudio.com).

## <a name="create-the-project"></a>Vytvoření projektu

1. Otevřete Visual Studio 2017.

1. Z panelu horní nabídce zvolte **soubor > Nový > projekt...** .

1. V **nový projekt** dialogové okno, v levém podokně rozbalte **jiné jazyky**, pak vyberte **Python**. V prostředním podokně vyberte **webového projektu**, projekt pojmenujte jako "HelloPython", a potom vyberte **OK**.

    Pokud nevidíte šablony projektů jazyka Python, zrušit mimo **nový projekt** dialogové okno a z panelu horní nabídce zvolte **nástroje > funkcí a nástrojů pro získání...**  Chcete-li spustit instalační program Visual Studio. Vyberte **vývoj Python** zatížení, zvolte **upravit**.

    ![Python vývoj zatížení v instalačním programu sady Visual Studio](../python/media/installation-python-workload.png)

1. Nový projekt se otevře v **Průzkumníku řešení** v pravém podokně. Projekt je v tomto okamžiku prázdná, protože neobsahuje žádné další soubory.

    ![Průzkumník řešení zobrazující nově vytvořený prázdný projekt](media/quickstart-python-01-empty-project.png)

## <a name="install-the-falcon-library"></a>Nainstaluje Falcon knihovny

Webové aplikace v Pythonu téměř vždy použijte jeden z mnoha dostupných knihoven Python pro zpracování nízké úrovně podrobnosti, třeba směrování webových požadavků a odpovědí shaping. Zatížení Python vývoj v sadě Visual Studio poskytuje [různých šablon pro webové aplikace](../python/template-web.md) vytvořených na základě knihovny Bottle, Flask a Django.

V tento rychlý start, ale použít jinou knihovnou, [Falcon](https://falconframework.org/), aby prostředí proces instalaci balíčku a vytváření webové aplikace od začátku. Následující kroky pro jednoduchost, nainstalujte Falcon do výchozího globálního prostředí.

1. Rozbalte **prostředí Python** uzlu v projektu zobrazíte výchozí prostředí pro projekt.

    ![Průzkumník řešení zobrazující výchozí prostředí](media/quickstart-python-02-default-environment.png)

1. Klikněte pravým tlačítkem na prostředí a vyberte **instalovat balíček Python...** . Tento příkaz otevře **prostředí Python** okno na **balíčky** kartě. Do pole vyhledávání zadejte "falcon" a vyberte **"pip nainstalovat falcon" z úložiště PyPI**. Přijměte zobrazování výzev pro oprávnění správce a sledovat **výstup** okna v sadě Visual Studio pro průběh.

    ![Instalace Falcon knihovny](media/quickstart-python-03-install-package.png)

1. Po instalaci, zobrazí se v prostředí v **Průzkumníku**, tzn., které můžete použít jeho použití v kódu jazyka Python.

    ![Knihovna falcon nainstalován](media/quickstart-python-04-package-installed.png)

Všimněte si, že místo instalace knihovny v globální prostředí, vývojáři obvykle vytvoříte "virtuální prostředí" do kterého chcete nainstalovat knihovny pro konkrétní projekt. Zahrnout mnoho Python šablony projektů v sadě Visual Studio `requirements.txt` soubor, který obsahuje seznam knihoven, na kterých závisí šabloně. Vytváření projektů z jednoho z těchto šablon aktivuje vytvoření virtuálního prostředí, do které jsou nainstalovány knihovny. Další informace najdete v tématu [prostředí Python - virtuální prostředí](../python/python-environments.md#virtual-environments).

## <a name="add-a-code-file"></a>Přidání souboru kódu

Nyní jste připraveni přidat kousek kód Python implementovat minimální webové aplikace.

1. Klikněte pravým tlačítkem na projekt v **Průzkumníku řešení** a vyberte **Přidat > novou položku...** . V dialogovém okně se zobrazí, vyberte **prázdný soubor Python**, pojmenujte ji `hello.py`a zvolte **OK**. Visual Studio automaticky otevře soubor v okně editoru. (Obecně **Přidat > novou položku...**  příkaz je skvělý způsob, jak přidat do projektu různé druhy soubory jako šablony položek často poskytují užitečné často používaný kód.)

1. Kopírování vložení nebo zadejte následující kód do `hello.py`:

    ```python
    import falcon
    api = falcon.API()

    # In Falcon, define a class for each resource; the on_get 
    # method then handles any GET requests.

    class HelloResource:
        def on_get(self, req, resp):
            resp.status = falcon.HTTP_200  # 200 is the default
            resp.body = "Hello, Python!"

    # Resources are represented by long-lived class instances
    hello = HelloResource()

    # Instruct Falcon to route / and /hello to the HelloResource
    api.add_route('/', hello)
    api.add_route('/hello', hello)

    if __name__ == "__main__":
        from wsgiref.simple_server import make_server

        # Run the web server on localhost:8080
        print("Starting web app server")
        srv = make_server('localhost', 8080, api)
        srv.serve_forever()
    ```

Další informace o Falcon, najdete v článku [rychlý start Falcon](https://falcon.readthedocs.io/en/stable/user/quickstart.html) (falcon.readthedocs.io).

## <a name="run-the-application"></a>Spuštění aplikace

1. Klikněte pravým tlačítkem na `hello.py` v **Průzkumníku řešení** a vyberte **nastavit jako spouštěcí soubor**. Příkaz identifikuje soubor kód ke spuštění v Pythonu při spuštění aplikace.

1. Klikněte pravým tlačítkem na projekt "Hello Python" **Průzkumníku řešení** a vyberte **vlastnosti**. Vyberte **ladění** kartě a nastavte **číslo portu** vlastnost `8080`. Tento krok zajistí, že Visual Studio spustí prohlížeč s `localhost:8080` místo pomocí náhodný port.

1. Vyberte **ladění > Spustit bez ladění** (Ctrl + F5) a ukládat změny souborů a spuštění aplikace.

1. Zobrazí se okno příkazového řádku se zprávou "Počáteční webové aplikace server" a pak otevře okno prohlížeče `localhost:8080` tam, kde se zobrazí zpráva "Hello, Python!" Požadavek GET zobrazí také v příkazovém okně. (Pokud se zobrazí pouze Python interaktivní prostředí v příkazovém okně nebo pokud toto okno bliká na obrazovce stručně, ujistěte se, že jste nastavili `hello.py` jako spouštěcí soubor v kroku 1 výše.)

1. Zavřete okno příkaz k zastavení aplikace.

## <a name="next-steps"></a>Další kroky

Blahopřejeme k dokončení tento rychlý start, ve kterém Seznámili jste se trochu Visual Studio IDE s Python. Chcete-li pokračovat s úplnější kurz Python v sadě Visual Studio, včetně použití interaktivních okna, ladění, vizualizace dat a práce s Gitem, vyberte níže uvedené tlačítko.

> [!div class="nextstepaction"]
> [Kurz: Začínáme s Pythonem v sadě Visual Studio](../python/vs-tutorial-01-01.md).

- Další informace o [Python webové šablony aplikace v sadě Visual Studio](../python/template-web.md)
- Další informace o [Visual Studio IDE](../ide/visual-studio-ide.md)
- Další informace o použití [ladicího programu sady Visual Studio](../debugger/debugger-feature-tour.md)