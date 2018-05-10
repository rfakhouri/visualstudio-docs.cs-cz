---
title: Konfigurace Python v Azure App Service
description: Postup instalace překladač Pythonu a knihovny v Azure App Service a konfiguraci webové aplikace správně odkazovat na tento překladač.
ms.date: 09/13/2017
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
- azure
ms.openlocfilehash: 9a71ea2210bfc6c56a235f194354c3279c8e7370
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/07/2018
---
# <a name="how-to-set-up-a-python-environment-on-azure-app-service"></a>Jak nastavit prostředí Python ve službě Azure App Service

[Aplikační služba Azure](https://azure.microsoft.com/services/app-service/) je nabídku platforma jako služba pro webové aplikace, jestli jsou weby přístupných prostřednictvím prohlížeče, REST API, které používají vlastní klienti nebo událost aktivuje zpracování. App Service plně podporuje použití Python k implementaci aplikace.

Přizpůsobitelné podpora Python ve službě Azure App Service je k dispozici jako sada App Service *lokality rozšíření* , každý obsahovat na konkrétní verzi modulu runtime jazyka Python. Můžete nainstalovat všechny požadované balíčky přímo do prostředí, jak je popsáno v tomto článku. Přizpůsobením prostředí v samotné aplikaci služby nemusíte udržovat balíčků ve vašich projektů webové aplikace nebo odešlete kódem aplikace.

> [!Tip]
> I když služby App Service ve výchozím nastavení má Python 2.7 a Python 3.4 nainstalované v kořenové složky na serveru, nelze upravit ani instalovat balíčky v těchto prostředích, ani by měl záviset na jejich přítomnosti. Se místo toho spoléhají na rozšíření lokality, kterou řídíte, jak je popsáno v tomto článku.

> [!Important]
> Postupů popsaných v tomto poli se mohou změnit a to především při zlepšování. Odesílány zpět změny [Python Engineering v blogu Microsoft](https://blogs.msdn.microsoft.com/pythonengineering/).

## <a name="choosing-a-python-version-through-the-azure-portal"></a>Výběr verze Python prostřednictvím portálu Azure

1. Vytvoření služby aplikací pro webovou aplikaci na portálu Azure.
1. Na stránce služby App Service, přejděte k položce **nástroje pro vývoj** vyberte **rozšíření**, pak vyberte **+ přidat**.
1. Přejděte dolů v seznamu rozšíření, který obsahuje verzi jazyka Python, které chcete:

    ![Rozšíření portálu Azure znázorňující Python](media/python-on-azure-extensions.png)

    > [!Tip]
    > Pokud potřebujete starší verzi jazyka Python a nezobrazí uvedené v rozšíření lokality, můžete nadále instalovat ho prostřednictvím Správce Azure Resource Manager podle popisu v další části.

1. Vyberte požadované rozšíření, přijměte právní podmínky a pak vyberte **OK**.
1. Po dokončení instalace, zobrazí se upozornění na portálu.

## <a name="choosing-a-python-version-through-the-azure-resource-manager"></a>Výběr verze Python prostřednictvím Správce Azure Resource Manager

Pokud nasazujete aplikační službu pomocí šablony Azure Resource Manager, přidejte rozšíření lokality jako prostředek. Konkrétně rozšíření se zobrazí jako vnořeného prostředku ( `resources` objektu v části `resources`) s typem `siteextensions` a názvem z [siteextensions.net](https://www.siteextensions.net/packages?q=Tags%3A%22python%22).

Například po přidání odkazu na `python361x64` (Python 3.6.1 x 64), může vaše šablona vypadat třeba takto (vynechání některé vlastnosti):

```json
"resources": [
  {
    "apiVersion": "2015-08-01",
    "name": "[parameters('siteName')]",
    "type": "Microsoft.Web/sites",

    // ...

    "resources": [
      {
        "apiVersion": "2015-08-01",
        "name": "python361x64",
        "type": "siteextensions",
        "properties": { },
        "dependsOn": [
          "[resourceId('Microsoft.Web/sites', parameters('siteName'))]"
        ]
      },
      // ...
    ]
  }
```

## <a name="setting-webconfig-to-point-to-the-python-interpreter"></a>Nastavení web.config tak, aby odkazoval na překladač Pythonu

Po instalaci rozšíření lokality (prostřednictvím portálu nebo šablonu Azure Resource Manager), vaše aplikace další bod `web.config` soubor překladač Pythonu. `web.config` Souboru dá pokyn běžící na App Service o tom, jak ho by měl zpracování požadavků Python prostřednictvím FastCGI nebo HttpPlatform webovém serveru IIS (7 +).

Začněte tím, že hledání úplnou cestu k rozšíření lokality `python.exe`, vytvořte a upravte příslušné `web.config` souboru.

### <a name="finding-the-path-to-pythonexe"></a>Cesta k python.exe hledání

Rozšíření webu Python je nainstalována na serveru v části `d:\home` ve složce odpovídající verzi jazyka Python a architektura (kromě několik starší verze). Například Python 3.6.1 x64 je nainstalován v `d:\home\python361x64`. Úplná cesta k překladač Pythonu je pak `d:\home\python361x64\python.exe`.

Pokud chcete zobrazit konkrétní cestu na App Service, vyberte **rozšíření** na stránce služby App Service zvolte rozšíření v seznamu.

![Seznam přípon v Azure App Service](media/python-on-azure-extension-list.png)

Tím se otevře stránka popis rozšíření, která obsahuje cestu:

![Podrobnosti o rozšíření v Azure App Service](media/python-on-azure-extension-detail.png)

Pokud máte potíže s zobrazuje cestu pro rozšíření, můžete najít ručně pomocí konzoly:

1. Na stránce služby App Service, vyberte **nástroje pro vývoj > konzole**.
1. Zadejte příkaz `ls ../home` nebo `dir ..\home` zobrazíte nejvyšší úrovně rozšíření složek, jako například `Python361x64`.
1. Zadejte příkaz jako `ls ../home/python361x64` nebo `dir ..\home\python361x64` k ověření, že obsahuje `python.exe` a další soubory překladač.

### <a name="configuring-the-fastcgi-handler"></a>Konfigurace obslužná rutina FastCGI

FastCGI je rozhraní, které funguje na úrovni požadavku. Služba IIS obdrží příchozí připojení a předává každý požadavek do WSGI aplikace spuštěná v jednom nebo více trvalé Python zpracovává. [Wfastcgi balíček](https://pypi.io/project/wfastcgi) předem nainstalován a nakonfigurován s každé rozšíření lokality Python, takže je můžete snadno povolit zahrnutím kód v `web.config` jako pro webové aplikace založené na rozhraní Bottle co jsou uvedeny níže. Všimněte si, že úplné cesty k `python.exe` a `wfastcgi.py` jsou umístěny v `PythonHandler` klíč:

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <appSettings>
    <add key="PYTHONPATH" value="D:\home\site\wwwroot"/>
    <!-- The handler here is specific to Bottle; other frameworks vary. -->
    <add key="WSGI_HANDLER" value="app.wsgi_app()"/>
    <add key="WSGI_LOG" value="D:\home\LogFiles\wfastcgi.log"/>
  </appSettings>
  <system.webServer>
    <handlers>
      <add name="PythonHandler" path="*" verb="*" modules="FastCgiModule"
           scriptProcessor="D:\home\Python361x64\python.exe|D:\home\Python361x64\wfastcgi.py"
           resourceType="Unspecified" requireAccess="Script"/>
    </handlers>
  </system.webServer>
</configuration>
```

`<appSettings>` Definované tady jsou k dispozici pro vaše aplikace jako proměnné prostředí:

- Hodnota `PYTHONPATH` volně rozšířeno, ale musí obsahovat kořenu vaší aplikace.
- `WSGI_HANDLER` musí odkazovat na importovatelné WSGI aplikaci z vaší aplikace.
- `WSGI_LOG` je volitelné, ale doporučené pro ladění aplikace. 

V tématu [publikování v Azure](publishing-python-web-applications-to-azure-from-visual-studio.md) další podrobnosti o `web.config` obsah pro Bottle, Flask a Django webové aplikace.

### <a name="configuring-the-httpplatform-handler"></a>Konfigurace HttpPlatform obslužné rutiny

Modul HttpPlatform předá připojení soketu přímo na samostatný proces Python. Tato průchozí můžete spustit kterýkoli webový server jako, ale vyžaduje spouštěcí skript, který spustí místní webový server. Zadejte skript, který v `<httpPlatform>` element `web.config`, kde `processPath` atribut body překladač Pythonu rozšíření lokality a `arguments` atribut body váš skript a všechny argumenty, kterou chcete přidat:

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <system.webServer>
    <handlers>
      <add name="PythonHandler" path="*" verb="*" modules="httpPlatformHandler" resourceType="Unspecified"/>
    </handlers>
    <httpPlatform processPath="D:\home\Python361x64\python.exe"
                  arguments="D:\home\site\wwwroot\runserver.py --port %HTTP_PLATFORM_PORT%"
                  stdoutLogEnabled="true"
                  stdoutLogFile="D:\home\LogFiles\python.log"
                  startupTimeLimit="60"
                  processesPerApplication="16">
      <environmentVariables>
        <environmentVariable name="SERVER_PORT" value="%HTTP_PLATFORM_PORT%" />
      </environmentVariables>
    </httpPlatform>
  </system.webServer>
</configuration>
```

`HTTP_PLATFORM_PORT` Proměnné prostředí, které jsou tady uvedené obsahuje port, který má místní server naslouchat pro připojení z místního hostitele. Tento příklad také ukazuje, jak vytvořit jiné proměnné prostředí, v případě potřeby v tomto případě `SERVER_PORT`.

## <a name="installing-packages"></a>Instalace balíčků

Překladač Pythonu nainstalované prostřednictvím rozšíření lokality je pouze jedna část prostředí Python. Budete pravděpodobně muset nainstalovat různých balíčcích ve také prostředí.

Instalovat balíčky přímo v prostředí serveru, použijte jednu z následujících metod:

| Metody | Použití |
| --- | --- |
| [Azure App Service Kudu konzoly](#azure-app-service-kudu-console) | Nainstaluje balíčky interaktivně. Balíčky musí být čistý Python nebo souborů Wheel, musíte publikovat. |
| [Kudu REST API](#kudu-rest-api) | Můžete použít k automatizaci instalace balíčku.  Balíčky musí být čistý Python nebo souborů Wheel, musíte publikovat. |
| Sady s aplikací | Instalovat balíčky přímo do projektu a potom je nasadit do služby App Service, jako by byly součástí vaší aplikace. V závislosti na tom, kolik závislostí máte a jak často je aktualizovat, tato metoda může být nejjednodušší způsob, jak získat pracovní nasazení budete. Se doporučuje, aby knihovny musí odpovídat verzi jazyka Python na serveru, v opačném případě se zobrazí skrytého chyby po nasazení. Ale nutné dodat, protože verze jazyka Python v App Service rozšíření lokality jsou stejné jako těchto verzí vydala python.org, můžete snadno získat kompatibilní verze pro místní vývoj. |
| Virtuální prostředí | Není podporováno. Místo toho použijte sdružování a nastavte `PYTHONPATH` proměnnou prostředí, aby odkazoval na umístění balíčků. |

### <a name="azure-app-service-kudu-console"></a>Azure App Service Kudu konzoly

[Kudu konzoly](https://github.com/projectkudu/kudu/wiki/Kudu-console) umožňuje přímé se zvýšením oprávnění příkazového řádku přístup k serveru služby App Service a její systému souborů. Toto je obou cenným nástrojem ke zjištění ladění a umožňuje pro operace rozhraní příkazového řádku, například při instalaci balíčků.

1. Otevření modulu Kudu z stránku služby App Service na portálu Azure tak, že vyberete **nástroje pro vývoj > Rozšířené nástroje**, pak výběrem **přejděte**. Tato akce přejde na adresu URL, která je stejná jako základní aplikace adresu URL služby s výjimkou s `.scm` vložit. Například, pokud je základní adresa URL `https://vspython-test.azurewebsites.net/` Kudu bude na `https://vspython-test.scm.azurewebsites.net/` (který můžete označit záložkou):

    ![Konzole Kudu pro službu Azure App Service](media/python-on-azure-console01.png)

1. Vyberte **konzolou pro ladění > CMD** pro otevření konzoly, ve kterém můžete přejít do instalace Python a zjistit, co knihovny jsou již existuje.

1. Chcete-li nainstalovat jeden balíček:

    a. Přejděte do složky instalace Python, ve které chcete nainstalovat balíček, jako například `d:\home\python361x64`.

    b. Použití `python.exe -m pip install <package_name>` nainstalovat balíček.

    ![Příklad instalace bottle přes konzolu Kudu pro Azure App Service](media/python-on-azure-console02.png)

1. Pokud jste nasadili `requirements.txt` pro vaši aplikaci k serveru neudělali, nainstalujte všechny tyto požadavky následujícím způsobem:

    a. Přejděte do složky instalace Python, ve které chcete nainstalovat balíček, jako například `d:\home\python361x64`.

    b. Spusťte příkaz `python.exe -m pip install --upgrade -r d:\home\site\wwwroot\requirements.txt`.

    Pomocí `requirements.txt` je doporučená, protože je snadné reprodukujte vašeho balíčku přesně nastavit lokálně a na serveru. Jenom nezapomeňte, přejděte konzole po nasazení všechny změny `requirements.txt` a spusťte příkaz znovu.

> [!Note]
> Neexistuje žádné kompilátor jazyka C v App Service, takže je potřeba nainstalovat wheel pro všechny balíčky s rozšíření nativní moduly. Mnoho oblíbených balíčky zadejte vlastní souborů Wheel. Pro balíčky, které nejsou, použijte `pip wheel <package_name>` na místním vývojovém počítači a pak nahrajte kolečka na váš web. Příklad, naleznete v části [Správa požadované balíčky s requirements.txt](managing-required-packages-with-requirements-txt.md).

### <a name="kudu-rest-api"></a>Kudu REST API

Místo použití konzole Kudu prostřednictvím portálu Azure, můžete spustit příkazy vzdáleně přes rozhraní REST API Kudu zveřejněním příkazu `https://yoursite.scm.azurewebsites.net/api/command`. Například k instalaci `bottle` balíček, post následujícím kódu JSON do `/api/command`:

```json
{
    "command": 'python.exe -m pip install bottle',
    "dir": '\home\python361x64'
}
```

Informace o příkazech a ověřování najdete v tématu [Kudu dokumentaci](https://github.com/projectkudu/kudu/wiki/REST-API).

Můžete také zjistit pomocí přihlašovacích údajů `az webapp deployment list-publishing-profiles` příkaz prostřednictvím rozhraní příkazového řádku Azure (v tématu [az webapp nasazení](/cli/azure/webapp/deployment?view=azure-cli-latest#az-webapp-deployment-list-publishing-profiles)). Pomocné knihovny pro publikování Kudu příkazy je k dispozici na [Githubu](https://github.com/lmazuel/azure-webapp-publish/blob/master/azure_webapp_publish/kudu.py#L42).
