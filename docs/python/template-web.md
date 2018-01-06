---
title: "Webové šablony projektů pro jazyk Python v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 07/13/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: article
caps.latest.revision: "11"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload: python
ms.openlocfilehash: 67132298bd8c6cf61027f01dab795f57b302b108
ms.sourcegitcommit: 9357209350167e1eb7e50b483e44893735d90589
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/05/2018
---
# <a name="python-web-project-templates"></a>Šablony webových projektů jazyka Python

Python v sadě Visual Studio podporuje vývoj webové projekty v rozhraní Bottle, Flask a Django prostřednictvím šablony projektů a spuštění ladění, nakonfigurovaný pro zpracování různých architektury. Můžete také použít Obecné **webového projektu** šablona pro ostatní platformy, jako je například pyramidy.

Visual Studio nezahrnuje architektury sami. Rozhraní musíte nainstalovat samostatně kliknutím pravým tlačítkem na projekt a výběrem **Python > framework instalace nebo aktualizace...** .

Spuštění projektu vytvořené ze šablony (přístupné prostřednictvím **soubor > Nový > projekt...** ) spouští webový server s náhodně vybrané místního portu, otevře výchozí prohlížeč při ladění a umožňuje přímé publikování do služby Microsoft Azure.

![Nové šablony webových projektů](media/template-web-new-project.png)

Šablony Bottle, Flask a Django zahrnují výchozí web s některými stránky a statické soubory. Tento kód stačí ke spuštění a ladění serveru místně (kdy některé nastavení je potřeba získat z prostředí) a nasazení do Microsoft Azure (kde [WSGI aplikace](http://www.python.org/dev/peps/pep-3333/) objekt musí být zadán).

Při vytváření projektu ze šablony konkrétní rozhraní, zobrazí se dialogové okno můžete nainstaluje potřebné balíčky pomocí nástroje pip. Doporučujeme také používat [virtuální prostředí](python-environments.md#virtual-environments) pro webové projekty tak, aby se správnými závislostmi jsou zahrnuty při publikování webu:

![Dialog, který nainstaluje potřebné balíčky pro šablony projektu](media/template-web-requirements-txt-wizard.png)

Pokud nasazujete do služby Microsoft Azure App Service, vyberte verzi jazyka Python jako [lokality rozšíření](https://aka.ms/PythonOnAppService) a ručně nainstalujte balíčky. Navíc vzhledem k tomu, že nemá Azure App Service **není** automaticky instalovat balíčky z `requirements.txt` souboru při nasazení ze sady Visual Studio, postupujte podle podrobností konfigurace na [aka.ms/PythonOnAppService](https://aka.ms/PythonOnAppService).

Microsoft Azure Cloud Services *nemá* podporu `requirements.txt` souboru. [Azure cloud service projekty](template-azure-cloud-service.md) podrobnosti.

## <a name="debugging"></a>Ladění

Při spuštění webového projektu pro ladění, Visual Studio spustí místní webový server a otevře výchozí prohlížeč tak, že adresa a port. Chcete-li určit další možnosti, klikněte pravým tlačítkem na projekt, vyberte možnost **vlastnosti**a vyberte **Spouštěč webových** karty:

  ![Vlastnosti Spouštěč webových obecné webové šablony](media/template-web-launcher-properties.png)

V **ladění** skupiny:

- **Cesty hledání**, **argumenty skriptu**, **překladač argumenty**, a **překladač cesta**: tyto možnosti jsou stejné jako u [normální ladění](debugging.md)
- **Spustit adresu URL**: Určuje adresu URL, který se otevře v prohlížeči. Výchozí hodnota `localhost`.
- **Číslo portu**: port, který se použijte, pokud v adrese URL (vybere Visual Studio jeden automaticky ve výchozím nastavení) není zadaný žádný. Toto nastavení umožňuje potlačit výchozí hodnota `SERVER_PORT` proměnné prostředí, který je používán šablony ke konfiguraci místní ladění server naslouchá na portu.

Vlastnosti v **spustit příkaz serveru** a **ladění serveru příkaz** skupiny (k tomu je nižší než co je zobrazit v bitové kopii) určují, jak se spustí webový server. Protože mnoho architektur vyžadují použití skriptu mimo aktuální projekt, zde mohou být konfigurovány skriptu a název modulu spuštění lze předat jako parametr.

- **Příkaz**: může být skript v jazyce Python (`*.py` soubor), název modulu (jako v `python.exe -m module_name`), nebo jeden řádek kódu (jako v `python.exe -c "code"`). Hodnota v rozevírací nabídce udává, které z těchto typů je určeno.
- **Argumenty**: tyto argumenty jsou předány na příkazovém řádku následující příkaz.
- **Prostředí**: obsahuje nový řádek oddělený seznam `NAME=VALUE` páry zadávání proměnných prostředí. Po všechny vlastnosti, které mohou upravit prostředí, například port číslo a hledání cesty a proto může přepsat tyto hodnoty jsou nastaveny tyto proměnné.

Všechny projektu vlastnost nebo prostředí může být zadána proměnná se syntaxí MSBuild, například: `$(StartupFile) --port $(SERVER_PORT)`.
`$(StartupFile)`je relativní cesta k souboru spuštění a `{StartupModule}` je importovatelné název souboru spuštění. `$(SERVER_HOST)`a `$(SERVER_PORT)` jsou proměnné normální prostředí, které se nastavují **spustit adresu URL** a **číslo portu** vlastnosti, automaticky, nebo **prostředí** Vlastnost.

> [!Note]
> Hodnoty v **spustit příkaz serveru** se používají s **ladění > spustit Server** příkaz nebo Ctrl + F5; hodnoty ve **ladění příkaz serveru** skupiny se používají s **Ladění > Spustit ladění serveru** příkaz nebo F5.

### <a name="sample-bottle-configuration"></a>Ukázková konfigurace Bottle

**Bottle webového projektu** Šablona zahrnuje často používaný kód, který nemá nezbytné konfigurace. Importované bottle aplikace nesmí obsahovat tento kód, ale v takovém případě spusťte následující nastavení aplikace pomocí nainstalovaného `bottle` modul:

- **Spusťte příkaz serveru** skupiny:
  - **Příkaz**: `bottle` (modulu)
  - **Argumenty**:`--bind=%SERVER_HOST%:%SERVER_PORT% {StartupModule}:app`

- **Ladění serveru příkaz** skupiny:
  - **Příkaz**: `bottle` (modulu)
  - **Argumenty**`--debug --bind=%SERVER_HOST%:%SERVER_PORT% {StartupModule}:app`

`--reload` Možnost se nedoporučuje, když pomocí sady Visual Studio pro ladění.

### <a name="sample-pyramid-configuration"></a>Ukázková konfigurace pyramidy

Jehlanový aplikací jsou aktuálně nejlépe vytvořené pomocí `pcreate` nástroj příkazového řádku. Po vytvoření aplikace, může být importován pomocí [z existující Python code](python-projects.md#creating-a-project-from-existing-files) šablony. Až to uděláte, vyberte **obecné webového projektu** přizpůsobení nakonfigurovat možnosti. Tato nastavení předpokládá nainstalovanou Pyramid do virtuálního prostředí v `..\env`.

- **Ladění** skupiny:
  - **Port serveru**: 6543 (nebo ať je nakonfigurovaný v souborech .ini)

- **Spusťte příkaz serveru** skupiny:
  - Příkaz: `..\env\scripts\pserve-script.py` (skript)
  - Argumenty:`Production.ini`

- **Ladění serveru příkaz** skupiny:
    - Příkaz: `..\env\scripts\pserve-script.py` (skript)
    - Argumenty:`Development.ini`

> [!Tip]
> Pravděpodobně budete muset nakonfigurovat **pracovní adresář** vlastnost projektu protože Pyramid aplikace jsou větší, než horní části stromu zdroje na úrovni obvykle jeden adresář.

### <a name="other-configurations"></a>Další konfigurace

Pokud máte nastavení pro jiná rozhraní, které chcete sdílet, nebo pokud chcete požádat o nastavení pro jinou architekturu, otevřete [problém na Githubu](https://github.com/Microsoft/PTVS/issues).

## <a name="publishing-to-azure-app-service"></a>Publikování do služby Azure App Service

Existují dva způsoby primární k publikování do služby Azure App Service. Nejprve nasazení od správy zdrojového kódu můžete použít stejným způsobem jako u jiných jazyků, jak je popsáno v [dokumentace k Azure](http://azure.microsoft.com/en-us/documentation/articles/web-sites-publish-source-control/). Pokud chcete publikovat přímo ze sady Visual Studio, klikněte pravým tlačítkem na projekt a vyberte **publikovat**:

![Publikování příkaz na místní nabídku projektu](media/template-web-publish-command.png)

Po výběru příkazu, Průvodce vás provede procesem vytvoření webu nebo import publikovat změnit nastavení, zobrazení náhledu soubory a publikování na vzdálený server.

Když vytvoříte lokalitu v App Service, musíte nainstalovat Python a všechny balíčky, které vaší lokality závisí na. Nejprve publikování webu, ale nespustí, dokud ji Python.

K instalaci Pythonu na aplikační služby, doporučujeme používat [lokality rozšíření](http://www.siteextensions.net/packages?q=Tags%3A%22python%22) (siteextensions.net). Tato rozšíření jsou kopie [oficiálního vydání](https://www.python.org) jazyka Python, Optimalizovaná a vytvořen nový balíček pro službu Azure App Service.

Rozšíření lokality můžou být nasazené prostřednictvím [portál Azure](https://portal.azure.com/). Vyberte **nástroje pro vývoj > rozšíření** okně App Service, vyberte **přidat**a posuňte se v seznamu k nalezení položek Python:

![Přidat rozšíření lokality na portálu Azure](media/template-web-site-extensions.png)

Pokud používáte JSON šablony nasazení, můžete určit rozšíření lokality jako prostředek vaší lokality:

```json
{
    "resources": [
    {
        "apiVersion": "2015-08-01",
        "name": "[parameters('siteName')]",
        "type": "Microsoft.Web/sites",
        ...
    },
    "resources": [
    {
        "apiVersion": "2015-08-01",
        "name": "python352x64",
        "type": "siteextensions",
        "properties": { },
        "dependsOn": [
            "[resourceId('Microsoft.Web/sites', parameters('siteName'))]"
        ]
    },
    ...
}
```

Nakonec se můžete přihlásit pomocí [vývoj konzoly](https://github.com/projectkudu/kudu/wiki/Kudu-console) a instalace rozšíření lokality z ní.

V současné době doporučený způsob instalace balíčků je po instalaci rozšíření lokality a provádění pip přímo použít konzolu pro vývoj. Pomocí úplnou cestu k Python je důležité, nebo může spustit špatný a obecně je potřeba použít virtuální prostředí. Příklad:

```command
c:\Python35\python.exe -m pip install -r D:\home\site\wwwroot\requirements.txt

c:\Python27\python.exe -m pip install -r D:\home\site\wwwroot\requirements.txt
```

Když se nasadí do služby Azure App Service, vaše lokalita používá za Microsoft IIS. Chcete-li váš web pro práci se službou IIS, je nutné přidat alespoň `web.config` souboru. Kliknutím pravým tlačítkem na projekt a výběrem možnosti jsou dostupné pro některé běžné cíle nasazení k dispozici šablony **Přidat > novou položku...**  (viz níže v dialogovém okně), a tyto konfigurace lze snadno upravit pro jiné účely. Najdete v článku [odkaz Konfigurace služby IIS](https://www.iis.net/configreference) informace o nastavení konfigurace k dispozici.

![Šablony Azure položek](media/template-web-azure-items.png)

Dostupné položky patří:

- Azure web.config (FastCGI): Přidá `web.config` souboru kdy aplikace poskytuje [WSGI](https://wsgi.readthedocs.io/en/latest/) objekt pro zpracování příchozích připojení.
- Azure web.config (HttpPlatformHandler): Přidá `web.config` při aplikace naslouchá na soket pro příchozí připojení v souboru.
- Azure statické soubory web.config: Pokud máte jeden z výše uvedených `web.config` soubory, soubor přidat do podadresáři vyloučíte z zpracovanou aplikaci.
- Azure vzdáleného ladění web.config: přidá soubory potřebné pro vzdálené ladění pomocí technologie WebSockets.
- Soubory podpory aplikace webové Role: obsahuje výchozí skripty nasazení pro cloudové služby webové role.
- Soubory podpory Role pracovního procesu: obsahuje výchozí nasazení a spouštět skripty pro role pracovního procesu cloudové služby.

Pokud přidáte ladění `web.config` šablona projektu a plánujete používat vzdálené ladění Python, musíte publikovat webu v konfiguraci "Debug". Toto nastavení je oddělená od aktuální konfigurace aktivního řešení a vždy použije jako výchozí "Verze". Pokud chcete ho změnit, otevřete **nastavení** kartě a použít **konfigurace** – pole se seznamem v Průvodci publikovat (najdete v části [dokumentace k Azure](https://azure.microsoft.com/develop/python/) Další informace o vytváření a nasazení do Azure Web Apps):

![Změna konfigurace publikování](media/template-web-publish-config.png)

**Převést na projekt cloudové služby Microsoft Azure** příkaz (viz obrázek níže) přidá projekt cloudové služby pro vaše řešení. Tento projekt obsahuje nastavení nasazení a konfigurace pro virtuální počítače a služby, který se má použít. Použití **publikovat** v projektu cloudové nasazení do cloudové služby; **publikovat** příkaz na projekt Python stále nasadí na webové servery. V tématu [Azure cloud service projekty](template-azure-cloud-service.md) další podrobnosti.

![Převést na Microsoft Azure cloud service projekt – příkaz](media/template-web-convert-menu.png)
