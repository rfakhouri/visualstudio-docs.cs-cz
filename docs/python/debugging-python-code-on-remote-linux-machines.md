---
title: Ladění kódu jazyka Python na vzdálených počítačích systému Linux
description: Jak používat k ladění kódu Pythonu spuštěný na vzdálených počítačích systému Linux, včetně nezbytné konfigurační kroky, zabezpečení a řešení potíží s Visual Studio.
ms.date: 06/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: de32c1d0309d6b6510a914fe359193105e2febde
ms.sourcegitcommit: 0bf2aff6abe485e3fe940f5344a62a885ad7f44e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/27/2018
ms.locfileid: "37057382"
---
# <a name="remotely-debugging-python-code-on-linux"></a>Vzdálené ladění kódu jazyka Python v systému Linux

Visual Studio se můžou spouštět a ladění aplikací Python místně i vzdáleně na počítači se systémem Windows (viz [vzdálené ladění](../debugger/remote-debugging.md)). Ho můžete také ladit vzdáleně na jiný operační systém, zařízení nebo Python implementace než CPython pomocí [ptvsd knihovny](https://pypi.python.org/pypi/ptvsd).

Při použití ptvsd, kód Python laděné hostuje ladění serveru, na kterou můžete připojit Visual Studio. Tato hostování vyžaduje malé změny kódu pro import a povolení serveru a může vyžadovat sítě nebo brány firewall konfigurace na vzdáleném počítači povolit připojení TCP.

|   |   |
|---|---|
| ![Ikona filmové kamery pro video](../install/media/video-icon.png "Sledovat video") | Úvod do vzdáleného ladění, najdete v části [podrobné informace: vzdálené ladění napříč platformami](https://youtu.be/y1Qq7BrV6Cc) (webu youtube.com, 6m22s), který je použitelný pro Visual Studio 2015 a 2017. |

## <a name="setting-up-a-linux-computer"></a>Nastavení počítač se systémem Linux

Následující položky jsou potřeba provést tento postup:

- Vzdálený počítač se systémem Python v operačním systému jako Mac OSX nebo Linux.
- Port 5678 (příchozí) otevřen v bráně firewall na tento počítač, který je výchozí pro vzdálené ladění.

Můžete snadno vytvořit [virtuální počítače s Linuxem v Azure](/azure/virtual-machines/linux/creation-choices) a [přístup pomocí vzdálené plochy](/azure/virtual-machines/linux/use-remote-desktop) ze systému Windows. Je vhodné Ubuntu pro virtuální počítač, protože Python je nainstalována ve výchozím nastavení; jinak, najdete v seznamu na [nainstalovat překladač Pythonu zvoleného](installing-python-interpreters.md) pro další Python umístění pro stahování.

Podrobné informace o vytváření pravidla brány firewall pro virtuální počítač Azure, najdete v části [otevřít porty pro virtuální počítač v Azure pomocí webu Azure portal](/azure/virtual-machines/windows/nsg-quickstart-portal).

## <a name="preparing-the-script-for-debugging"></a>Příprava ladění skriptu

1. Na vzdáleném počítači, vytvořte soubor Python s názvem `guessing-game.py` následujícím kódem:

    ```python
    import random

    guesses_made = 0
    name = input('Hello! What is your name?\n')
    number = random.randint(1, 20)
    print('Well, {0}, I am thinking of a number between 1 and 20.'.format(name))

    while guesses_made < 6:
        guess = int(input('Take a guess: '))
        guesses_made += 1
        if guess < number:
            print('Your guess is too low.')
        if guess > number:
            print('Your guess is too high.')
        if guess == number:
            break
    if guess == number:
        print('Good job, {0}! You guessed my number in {1} guesses!'.format(name, guesses_made))
    else:
        print('Nope. The number I was thinking of was {0}'.format(number))
    ```

1. Nainstalujte `ptvsd` balíček do vašeho prostředí pomocí `pip3 install ptvsd`. (Poznámka: je vhodné záznam verze ptvsd, která je nainstalována v případě, že potřebujete pro řešení potíží; [ptvsd výpis](https://pypi.python.org/pypi/ptvsd) také ukazuje dostupné verze.)

1. Povolení vzdáleného ladění přidáním kódu níže na nejdřívější možné bod v `guessing-game.py`, před jiný kód. (I když přísné požadavky, není možné ladění vytvořený před všechny vlákna na pozadí `enable_attach` je volána funkce.)

   ```python
   import ptvsd
   ptvsd.enable_attach('my_secret')
   ```

   První argument předaný `enable_attach` (nazývané "tajný") omezuje přístup na spuštěné skript, a zadejte tento tajný klíč při připojení vzdáleného ladicího programu. (Když není doporučeno, můžete povolit všem uživatelům připojit, použijte `enable_attach(secret=None)`.)

1. Uložte soubor a spusťte `python3 guessing-game.py`. Volání `enable_attach` běží na pozadí a čeká příchozí připojení, protože jinak interakci s programem. V případě potřeby `wait_for_attach` funkce může být volána po `enable_attach` blokování programu, dokud připojí ladicí program.

> [!Tip]
> Kromě `enable_attach` a `wait_for_attach`, ptvsd také poskytuje pomocné funkce `break_into_debugger`, který slouží jako programový zarážek, pokud je připojen ladicí program. K dispozici je také `is_attached` funkci, která vrací `True` Pokud je připojen ladicí program (Všimněte si, že je není potřeba před všemi ostatními volání zkontrolujte tento výsledek `ptvsd` funkce).

## <a name="attaching-remotely-from-python-tools"></a>Vzdáleně připojuje z nástrojů Python

V následujícím postupu jsme zarážku jednoduché zastavit vzdálený proces.

1. Vytvoření kopie vzdáleného souboru v místním počítači a otevřete jej v sadě Visual Studio. Nezávisle na tom, kde je umístěn soubor, ale její název by měl odpovídat názvu skriptu na vzdáleném počítači.

1. (Volitelné) Pokud chcete, aby IntelliSense pro ptvsd v místním počítači, nainstalujte balíček ptvsd do prostředí Python.

1. Vyberte **ladění > připojit k procesu**.

1. V **připojit k procesu** nastavte dialogové okno, který se zobrazí **typ připojení** k **vzdáleného Python (ptvsd)**. (Na starší verze sady Visual Studio jsou pojmenované tyto příkazy **přenosu** a **Python vzdálené ladění**.)

1. V **cíl připojení** pole (**kvalifikátor** na starší verze), zadejte `tcp://<secret>@<ip_address>:5678` kde `<secret>` je předán řetězec `enable_attach` v kódu jazyka Python, `<ip_address>` je, že z vzdáleného počítače (který může být explicitní adresa nebo název jako myvm.cloudapp.net), a `:5678` je číslo portu vzdáleného ladění.

    > [!Warning]
    > Pokud chcete vytvořit připojení prostřednictvím veřejného Internetu, měli byste použít `tcps` místo a následujících instrukcí níže pro [zabezpečení ladicího programu připojení pomocí protokolu SSL](#securing-the-debugger-connection-with-ssl).

1. Stiskněte klávesu Enter k naplnění seznamu dostupných ptvsd procesy v tomto počítači:

    ![Zadání cíl připojení a výpisy procesů](media/remote-debugging-qualifier.png)

    Pokud je možné spustit jiný program na vzdáleném počítači po naplnění seznamu, vyberte **aktualizovat** tlačítko.

1. Vyberte proces k ladění a potom **Attach**, nebo dvakrát kliknout na proces.

1. Visual Studio dojde k přepnutí do režimu ladění, zatímco skript stále běží na vzdáleném počítači, poskytuje všechny obvyklé [ladění](debugging-python-in-visual-studio.md) možnosti. Například nastavit zarážky `if guess < number:` řádek, potom přepnout na vzdáleném počítači a zadejte jiné odhad. Po provedení, sady Visual Studio na místní počítač přestane u zarážky, ukazuje, místní proměnné a tak dále:

    ![Je dosaženo zarážek](media/remote-debugging-breakpoint-hit.png)

1. Když zastavíte ladění, Visual Studio odpojí programu, který pokračuje v činnosti na vzdáleném počítači. ptvsd taky dál naslouchá pro připojení ladicí programy, takže je můžete kdykoli znovu připojte k procesu.

### <a name="connection-troubleshooting"></a>Odstraňování problémů s připojením

1. Ujistěte se, že jste vybrali **vzdáleného Python (ptvsd)** pro **typ připojení** (**Python vzdálené ladění** pro **přenosu** s starší verze.)
1. Zkontrolujte, že tajný klíč v **cíl připojení** (nebo **kvalifikátor**) přesně odpovídá tajný klíč v vzdáleného kódu.
1. Zkontrolujte, že IP adresa v **cíl připojení** (nebo **kvalifikátor**) se shoduje s vzdáleného počítače.
1. Zkontrolujte, že jste otevřen port vzdáleného ladění na vzdáleném počítači a zda jste zadali příponou portu v cíl připojení, jako `:5678`.
    - Pokud budete muset použít jiný port, můžete ho zadat `enable_attach` volat pomocí `address` argument, jako v `ptvsd.enable_attach(secret = 'my_secret', address = ('0.0.0.0', 8080))`. V takovém případě otevřete určený port v bráně firewall.
1. Zkontrolujte, zda je verze ptvsd nainstalovaná na vzdáleném počítači, jak ho vrátila `pip3 list` se shoduje s používané verzi nástroje Python tools používáte v sadě Visual Studio v následující tabulce. V případě potřeby aktualizujte ptvsd na vzdáleném počítači.

    | Verze sady Visual Studio | Verze nástroje/ptvsd Python |
    | --- | --- |
    | 2017 15.3 | 3.2.0 |
    | 2017 15.2 | 3.1.0 |
    | 2017 15.0, 15.1 | 3.0.0 |
    | 2015 | 2.2.6 |
    | 2013 | 2.2.2 |
    | 2012, 2010 | 2.1 |

## <a name="securing-the-debugger-connection-with-ssl"></a>Zabezpečení ladicího programu připojení pomocí protokolu SSL

Ve výchozím nastavení zabezpečené připojení k serveru vzdáleného ladění ptvsd pouze tajný klíč a všechna data předávána ve formátu prostého textu. Pro lepší zabezpečení připojení podporuje ptvsd SSL, které můžete nastavit takto:

1. Na vzdáleném počítači generovat samostatný certifikát podepsaný svým držitelem a pomocí openssl soubory klíčů:

    ```command
    openssl req -new -x509 -days 365 -nodes -out cert.cer -keyout cert.key
    ```

    Pokud budete vyzváni, použijte název hostitele nebo IP adresu (podle toho, které používáte pro připojení) pro **běžný název** po zobrazení výzvy openssl.

    (Viz [certifikáty podepsané svým držitelem](http://docs.python.org/3/library/ssl.html#self-signed-certificates) v Python `ssl` modulu dokumentace pro další podrobnosti. Všimněte si, že příkaz do těchto dokumentů vygeneruje pouze jeden soubor kombinované.)

1. V kódu upravit volání `enable_attach` zahrnout `certfile` a `keyfile` argumenty pomocí názvy souborů jako hodnoty (těchto argumentů mají stejný význam jako u standardní `ssl.wrap_socket` funkce Python):

    ```python
    ptvsd.enable_attach(secret='my_secret', certfile='cert.cer', keyfile='cert.key')
    ```

    Můžete provést také stejné změny v souboru kódu na místním počítači, ale ve skutečnosti není spustit tento kód, proto není nezbytně nutné.

1. Restartujte program Python na vzdáleném počítači, což připravené pro ladění.

1. Zabezpečení kanálu přidáním certifikát důvěryhodné kořenové certifikační Autority na počítači s Windows pomocí sady Visual Studio:

    1. Zkopírujte soubor certifikátu ze vzdáleného počítače do místního počítače.
    1. Otevřete ovládací panely a přejděte do **nástroje pro správu > Správa certifikátů počítače**.
    1. V okně, které se zobrazí, rozbalte položku **důvěryhodné kořenové certifikační autority** na levé straně, klikněte pravým tlačítkem na **certifikáty**a vyberte **všechny úlohy > Import...** .
    1. Najděte a vyberte `.cer` soubor zkopírován ze vzdáleného počítače, pak klikněte na tlačítko prostřednictvím v dialogových oknech k dokončení importu.

1. Připojit proces opakovat v sadě Visual Studio jak bylo popsáno dříve, teď pomocí `tcps://` jako protokol pro **cíl připojení** (nebo **kvalifikátor**).

    ![Výběr vzdáleného ladění přenos pomocí protokolu SSL](media/remote-debugging-qualifier-ssl.png)

### <a name="warnings"></a>Upozornění

Visual Studio vyzve vás o možných problémech s certifikátem při připojení přes protokol SSL, jak je popsáno níže. Můžete ignorovat upozornění a pokračovat, i když je kanál dál šifrovat, ale před odposlechem může být otevřené pro útokům man-in-the-middle.

1. Pokud se zobrazí následující upozornění "Vzdálený certifikát není důvěryhodný", znamená to, že nebyla přidána správně certifikát k důvěryhodné kořenové certifikační Autority. Zkontrolujte tyto kroky a zkuste to znovu.

    ![Upozornění důvěryhodných certifikátů SSL](media/remote-debugging-ssl-warning.png)

1. Pokud se zobrazí následující upozornění "název vzdáleného certifikátu neodpovídá název hostitele", znamená to, jste nepoužili správný název hostitele nebo IP adresou, jako **běžný název** při vytváření certifikátu.

    ![Upozornění hostname certifikátu SSL](media/remote-debugging-ssl-warning2.png)

> [!Warning]
> V současné době Visual Studio 2017 přestane reagovat, když můžete tato upozornění ignorovat. Ujistěte se, že opravte všechny problémy. před pokusem o připojení.
