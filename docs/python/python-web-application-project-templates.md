---
title: Šablony webové aplikace pro jazyk Python
description: Přehled šablony sady Visual Studio pro webové aplikace napsané v Pythonu pomocí rozhraní Bottle, Flask a Django, včetně ladění konfigurace a publikování do služby Azure App Service.
ms.date: 05/18/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: f975b726b8be76af1e3daeff59a06a18988644ab
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34752037"
---
# <a name="python-web-application-project-templates"></a>Šablony projektu webové aplikace Python

Python v sadě Visual Studio podporuje vývoj webové projekty v rozhraní Bottle, Flask a Django prostřednictvím šablony projektů a spuštění ladění, nakonfigurovaný pro zpracování různých architektury. Tyto šablony zahrnují `requirements.txt` souboru deklarovat potřebné závislosti. Při vytváření projektu z jednoho z těchto šablon, Visual Studio zobrazí výzvu k instalaci těchto balíčků (viz [instalaci požadavky projektu](#installing-project-requirements) dále v tomto článku).

Obecný "Webového projektu" šablonu můžete použít také pro ostatní rozhraní, jako je například pyramidy. V takovém případě žádné rozhraní jsou nainstalované pomocí šablony. Místo toho nainstaluje potřebné balíčky do prostředí, který používáte pro projekt (viz [prostředí Python Správa](managing-python-environments-in-visual-studio.md)).

## <a name="using-a-project-template"></a>Pomocí šablony projektu

Vytvoření projektu pomocí šablony **soubor** > **nový** > **projektu**. Pokud chcete zobrazit šablony pro webové projekty, vyberte **Python** > **webové** na levé straně dialogového okna. Potom vyberte šablonu podle vaší volby, poskytuje názvy pro projekt a řešení, nastavte možnosti pro úložiště Git a adresář řešení a vyberte **OK**.

![Dialogové okno Nový projekt pro webové aplikace](media/projects-new-project-dialog-web.png)

Obecný "Web" v šabloně projektů, již bylo zmíněno dříve, obsahuje pouze prázdný projekt sady Visual Studio s žádný kód a žádné předpoklady, než se projekt Python. Podrobnosti v šabloně "Cloudová služba Azure" najdete v tématu [projekty Azure cloudových služeb pro jazyk Python](python-azure-cloud-service-project-template.md).python-azure-cloud-service-project-template.md

Všechny šablony jsou založené na webového rozhraní Bottle, Flask a Django a spadají do tří skupin Obecné, jak je popsáno v následujících částech. Aplikace vytvoří jedním z těchto šablon obsahuje dostatečný kód ke spuštění a ladění aplikace místně. Každé z nich také poskytuje nezbytné [WSGI aplikace objekt](http://www.python.org/dev/peps/pep-3333/) (python.org) k [nasazení do Azure App Service](publishing-python-web-applications-to-azure-from-visual-studio.md).

### <a name="blank-group"></a>Prázdné skupiny

Všechny šablony "Prázdná (framework) webový projekt" Vytvoření projektu s více nebo méně minimální často používaný kód a potřebné závislosti, které jsou deklarované v `requirements.txt` souboru.

| Šablony | Popis |
| --- | --- |
| Prázdné Bottle webového projektu | Generuje minimální aplikace v `app.py` s domovskou stránku pro `/` a `/hello/<name>` stránky, která vrátí `<name>` pomocí šablony velmi krátké vložené stránky. |
| Prázdné Django webového projektu | Generuje projekt Django se strukturu základní Django lokality, ale žádné aplikace Django. Další informace najdete v tématu [Django šablony](python-django-web-application-project-template.md) a [Learning Django kroku 1](learn-django-in-visual-studio-step-01-project-and-solution.md). |
| Webový projekt Flask prázdné | Generuje minimální aplikace pomocí jedné "Hello, World!" stránka pro `/`. Tato aplikace je podobná výsledek podrobné kroků v [rychlý start: použití Visual Studio k vytvoření první webové aplikace Python](../ide/quickstart-python.md?context=visualstudio/python/default). Viz také [Learning Flask kroku 1](learn-flask-visual-studio-step-01-project-solution.md).

### <a name="web-group"></a>Skupina webových

Všechny šablony "(Framework) webového projektu" vytvořte úvodní webovou aplikaci s stejné konstrukční bez ohledu na zvolené framework. Aplikace má Domů, o a kontaktní stránky, spolu s navigačního panelu a rychlý návrh pomocí Bootstrap. Každá aplikace je správně nakonfigurovaný pro statické soubory serveru (šablon stylů CSS, JavaScript a písma) a používá mechanismus šablony stránce vhodné pro rozhraní.

| Šablony | Popis |
| --- | --- |
| Bottle webového projektu | Generuje aplikace, jejichž statické soubory jsou součástí `static` složky a zpracovává prostřednictvím kódu v `app.py`. Směrování pro jednotlivé stránky je součástí `routes.py`a `views` složka obsahuje šablony stránky.|
| Django webového projektu | Generuje projekt Django a aplikace Django s tři stránky, podpora ověřování a databáze SQLite (ale žádné modely dat). Další informace najdete v tématu [Django šablony](python-django-web-application-project-template.md) a [Learning Django krok 4](learn-django-in-visual-studio-step-04-full-django-project-template.md). |
| Webový projekt flask | Generuje aplikace, jejichž statické soubory jsou součástí `static` složky. Kód na `views.py` zpracovává směrování s stránky šablony pomocí modulu Jinja součástí `templates` složky. `runserver.py` Soubor poskytuje spuštění kódu. V tématu [učení Flask krok 4](learn-flask-visual-studio-step-04-full-flask-project-template.md). |
| Webový projekt flask/Jade | Generuje stejná aplikace jako s "Webový projekt Flask" šablony ale pro modul ukázka Jinja pomocí Jade rozšíření. |

### <a name="polls-group"></a>Hlasování skupiny

"Hlasování (framework) webového projektu" šablony vytvořit úvodní webovou aplikaci, pomocí kterého můžete hlasovat uživatele na různých dotazování otázky. Každá aplikace je založen na strukturu šablony projektů "Web" používat ke správě hlasování a odpovědi uživatele databáze. Zahrnout příslušné datové modely aplikace a aplikace na zvláštní stránce (/ počáteční hodnoty), načte hlasování z `samples.json` souboru.

| Šablony | Popis |
| --- | --- |
| Hlasování Bottle webového projektu | Generuje aplikaci, která se dají spouštět i proti databázi v paměti, MongoDB nebo Azure Table Storage, který je konfigurován pomocí `REPOSITORY_NAME` proměnné prostředí. Datové modely a data store kód jsou součástí `models` složku a `settings.py` soubor obsahuje kód, určit, jaké úložiště dat se používá. |
| Hlasování Django webového projektu | Generuje projekt Django a aplikace Django s tři stránky a databáze SQLite. Zahrnuje přizpůsobení rozhraní pro správu Django povolit ověřené správce k vytváření a správě hlasování. Další informace najdete v tématu [Django šablony](python-django-web-application-project-template.md) a [Learning Django krok 6](learn-django-in-visual-studio-step-06-polls-django-web-project-template.md). |
| Webový projekt Flask hlasování | Generuje aplikaci, která se dají spouštět i proti databázi v paměti, MongoDB nebo Azure Table Storage, který je konfigurován pomocí `REPOSITORY_NAME` proměnné prostředí. Datové modely a data store kód jsou součástí `models` složku a `settings.py` soubor obsahuje kód, určit, jaké úložiště dat se používá. Aplikace používá modul Jinja pro stránku šablony. V tématu [učení Flask krok 5](learn-flask-visual-studio-step-05-polls-flask-web-project-template.md). |
| Webový projekt Flask/Jade hlasování | Generuje stejná aplikace jako s "Hlasovací webový projekt Flask" šablony ale pro modul ukázka Jinja pomocí Jade rozšíření. |

## <a name="installing-project-requirements"></a>Požadavky na instalaci projektu

Při vytváření projektu ze šablony konkrétní rozhraní, zobrazí se dialogové okno můžete nainstaluje potřebné balíčky pomocí nástroje pip. Doporučujeme také používat [virtuální prostředí](selecting-a-python-environment-for-a-project.md#using-virtual-environments) pro webové projekty tak, aby se správnými závislostmi jsou zahrnuty při publikování webu:

![Dialog, který nainstaluje potřebné balíčky pro šablony projektu](media/template-web-requirements-txt-wizard.png)

Pokud používáte zdrojového kódu, je obvykle vynechat složky pak virtuální prostředí jako prostředí můžete znovu vytvořit pomocí pouze `requirements.txt`. Nejlepší způsob, jak vyloučit složku, je nejprve vybrat **I je nainstaluje sám** v řádku uvedené výše, potom zakázat automatické potvrzení před vytvořením virtuálního prostředí. Podrobnosti najdete v tématu [kurz Django učení - kroky 1 – 2 a 1 – 3](learn-django-in-visual-studio-step-01-project-and-solution.md#step-1-2-examine-the-git-controls-and-publish-to-a-remote-repository) a [kurz Flask učení - kroky 1 – 2 a 1 – 3](learn-flask-visual-studio-step-01-project-solution.md#step-1-2-examine-the-git-controls-and-publish-to-a-remote-repository)

Pokud nasazujete do služby Microsoft Azure App Service, vyberte verzi jazyka Python jako [lokality rozšíření](https://aka.ms/PythonOnAppService) a ručně nainstalujte balíčky. Navíc vzhledem k tomu, že nemá Azure App Service **není** automaticky instalovat balíčky z `requirements.txt` souboru při nasazení ze sady Visual Studio, postupujte podle podrobností konfigurace na [aka.ms/PythonOnAppService](https://aka.ms/PythonOnAppService).

Microsoft Azure Cloud Services *nemá* podporu `requirements.txt` souboru. V tématu [projekty Azure cloudových služeb](python-azure-cloud-service-project-template.md) podrobnosti.

## <a name="debugging"></a>Ladění

Při spuštění webového projektu pro ladění, Visual Studio spustí místní webový server na náhodných portu a otevře výchozí prohlížeč tak, že adresa a port. Chcete-li určit další možnosti, klikněte pravým tlačítkem na projekt, vyberte možnost **vlastnosti**a vyberte **Spouštěč webových** karty:

![Vlastnosti Spouštěč webových obecné webové šablony](media/template-web-launcher-properties.png)

V **ladění** skupiny:

- **Cesty hledání**, **argumenty skriptu**, **překladač argumenty**, a **překladač cesta**: tyto možnosti jsou stejné jako u [normální ladění](debugging-python-in-visual-studio.md)
- **Spustit adresu URL**: Určuje adresu URL, který se otevře v prohlížeči. Výchozí hodnota `localhost`.
- **Číslo portu**: port, který se použijte, pokud v adrese URL (vybere Visual Studio jeden automaticky ve výchozím nastavení) není zadaný žádný. Toto nastavení umožňuje potlačit výchozí hodnota `SERVER_PORT` proměnné prostředí, který je používán šablony ke konfiguraci místní ladění server naslouchá na portu.

Vlastnosti v **spustit příkaz serveru** a **ladění serveru příkaz** skupiny (k tomu je nižší než co je zobrazit v bitové kopii) určují, jak se spustí webový server. Protože mnoho architektur vyžadují použití skriptu mimo aktuální projekt, zde mohou být konfigurovány skriptu a název modulu spuštění lze předat jako parametr.

- **Příkaz**: může být skript v jazyce Python (`*.py` soubor), název modulu (jako v `python.exe -m module_name`), nebo jeden řádek kódu (jako v `python.exe -c "code"`). Hodnotu v rozevíracím seznamu určuje, které z těchto typů je určeno.
- **Argumenty**: tyto argumenty jsou předány na příkazovém řádku následující příkaz.
- **Prostředí**: obsahuje nový řádek oddělený seznam `NAME=VALUE` páry zadávání proměnných prostředí. Po všechny vlastnosti, které mohou upravit prostředí, například port číslo a hledání cesty a proto může přepsat tyto hodnoty jsou nastaveny tyto proměnné.

Všechny projektu vlastnost nebo prostředí může být zadána proměnná se syntaxí MSBuild, například: `$(StartupFile) --port $(SERVER_PORT)`.
`$(StartupFile)` je relativní cesta k souboru spuštění a `{StartupModule}` je importovatelné název souboru spuštění. `$(SERVER_HOST)` a `$(SERVER_PORT)` jsou proměnné normální prostředí, které se nastavují **spustit adresu URL** a **číslo portu** vlastnosti, automaticky, nebo **prostředí** vlastnost.

> [!Note]
> Hodnoty v **spustit příkaz serveru** se používají s **ladění > spustit Server** příkaz nebo Ctrl + F5; hodnoty ve **ladění příkaz serveru** skupiny se používají s **Ladění > Spustit ladění serveru** příkaz nebo F5.

### <a name="sample-bottle-configuration"></a>Ukázková konfigurace Bottle

**Bottle webového projektu** Šablona zahrnuje často používaný kód, který nemá nezbytné konfigurace. Importované bottle aplikace nesmí obsahovat tento kód, ale v takovém případě spusťte následující nastavení aplikace pomocí nainstalovaného `bottle` modul:

- **Spusťte příkaz serveru** skupiny:
  - **Příkaz**: `bottle` (modulu)
  - **Argumenty**: `--bind=%SERVER_HOST%:%SERVER_PORT% {StartupModule}:app`

- **Ladění serveru příkaz** skupiny:
  - **Příkaz**: `bottle` (modulu)
  - **Argumenty** `--debug --bind=%SERVER_HOST%:%SERVER_PORT% {StartupModule}:app`

`--reload` Možnost se nedoporučuje, když pomocí sady Visual Studio pro ladění.

### <a name="sample-pyramid-configuration"></a>Ukázková konfigurace pyramidy

Jehlanový aplikací jsou aktuálně nejlépe vytvořené pomocí `pcreate` nástroj příkazového řádku. Po vytvoření aplikace, může být importován pomocí [z existující Python code](managing-python-projects-in-visual-studio.md#creating-a-project-from-existing-files) šablony. Až to uděláte, vyberte **obecné webového projektu** přizpůsobení nakonfigurovat možnosti. Tato nastavení předpokládá nainstalovanou Pyramid do virtuálního prostředí v `..\env`.

- **Ladění** skupiny:
  - **Port serveru**: 6543 (nebo ať je nakonfigurovaný v souborech .ini)

- **Spusťte příkaz serveru** skupiny:
  - Příkaz: `..\env\scripts\pserve-script.py` (skript)
  - Argumenty: `Production.ini`

- **Ladění serveru příkaz** skupiny:
  - Příkaz: `..\env\scripts\pserve-script.py` (skript)
  - Argumenty: `Development.ini`

> [!Tip]
> Pravděpodobně budete muset nakonfigurovat **pracovní adresář** vlastnost projektu protože Pyramid aplikace jsou obvykle jednu složku pod kořenovým adresářem projektu.

### <a name="other-configurations"></a>Další konfigurace

Pokud máte nastavení pro jiná rozhraní, které chcete sdílet, nebo pokud chcete požádat o nastavení pro jinou architekturu, otevřete [problém na Githubu](https://github.com/Microsoft/PTVS/issues).

## <a name="convert-a-project-to-azure-cloud-service"></a>Převedení projektu Azure Cloud Service

**Převést na projekt cloudové služby Microsoft Azure** příkaz (viz obrázek níže) přidá projekt cloudové služby pro vaše řešení. Tento projekt obsahuje nastavení nasazení a konfigurace pro virtuální počítače a služby, který se má použít. Použití **publikovat** v projektu cloudové nasazení do cloudové služby; **publikovat** příkaz na projekt Python stále nasadí na webové servery. Další informace najdete v tématu [Azure cloud service projekty](python-azure-cloud-service-project-template.md).

![Převést na Microsoft Azure cloud service projekt – příkaz](media/template-web-convert-menu.png)

## <a name="see-also"></a>Viz také:

- [Referenční příručka šablon položek Python](python-item-templates.md)
- [Publikování do služby Azure App Service](publishing-python-web-applications-to-azure-from-visual-studio.md)
