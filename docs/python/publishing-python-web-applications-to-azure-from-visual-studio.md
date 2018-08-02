---
title: Publikování aplikace v Pythonu do Azure App Service
description: Jak publikovat webovou aplikaci Python přímo do služby Azure App Service ze sady Visual Studio, včetně nutný obsah pro soubor web.config.
ms.date: 07/26/2018
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
ms.openlocfilehash: c42e87d6dcf4767621cafdb246294b8a45d0e4a7
ms.sourcegitcommit: 0cf1e63b6e0e6a0130668278489b21a6e5038084
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/02/2018
ms.locfileid: "39468667"
---
# <a name="publish-to-azure-app-service"></a>Publikování do Azure App Service

> [!Important]
> Nasazení aplikace v Pythonu do služby Azure App Service pro Linux se v současné době nepodporuje ze sady Visual Studio. Microsoft také plány přestat používat Python ve službě App Service ve Windows. V tomto článku, pokud je k dispozici budou aktualizace zveřejňovány. Do té doby můžete nasadit do služby App Service v Linuxu pomocí kontejnerů. Další informace najdete v tématu [nasazení webové aplikace v Pythonu ve službě Web App for Containers](/azure/app-service/containers/quickstart-python).

Visual Studio poskytuje možnost publikovat přímo do služby Azure App Service webovou aplikaci v Pythonu. Publikování do služby Azure App Service znamená, že zkopírujete potřebné soubory na serveru a nastavení odpovídající *web.config* soubor, který se dá pokyn webového serveru, jak pro spuštění vaší aplikace.

Proces publikování se liší mezi Visual Studio 2017 a Visual Studio 2015. Konkrétně, Visual Studio 2015 automatizuje některé z kroků, včetně vytváření *web.config*, ale tato automatizace omezuje dlouhodobé flexibility a kontroly. Visual Studio 2017 vyžaduje další ruční kroky, ale zajišťuje přesnější kontrolu nad prostředí Pythonu. Obě možnosti jsou popsány zde.

> [!Note]
> Informace o změny mezi Visual Studio 2015 a Visual Studio 2017, najdete v blogovém příspěvku, [publikovat do Azure v sadě Visual Studio 2017](https://blogs.msdn.microsoft.com/pythonengineering/2016/12/12/publish-to-azure-in-vs-2017/).

## <a name="prerequisites"></a>Požadavky

V tomto návodu budete potřebovat projekt webové aplikace založené na rozhraní Bottle, Flask a Django. Pokud ještě nemáte projektu a chtěli vyzkoušet proces publikování, vytvořte jednoduchou testovací projekt následujícím způsobem:

1. V sadě Visual Studio, vyberte **souboru** > **nový** > **projektu**, vyhledejte "Bottle", vyberte **Bottle webový projekt**, zadejte název a cestu k projektu, klikněte na tlačítko **OK**. (Šablona Bottle je součástí úlohy pro vývoj v Pythonu; viz [instalace](installing-python-support-in-visual-studio.md).)

1. Postupujte podle pokynů k instalaci externích balíčků, že vyberete **nainstalovat do virtuálního prostředí** a základním intepretu upřednostňované virtuálního prostředí. Obvykle odpovídají tato volba verzi Pythonu, které jsou nainstalované ve službě App Service.

1. Testování projektu místně stisknutím kombinace kláves **F5** nebo jeho výběru **ladění** > **spustit ladění**.

## <a name="create-an-azure-app-service"></a>Vytvoření služby Azure App Service

Publikování na platformě Azure, je požadován cíl služby App Service. K tomuto účelu můžete vytvořit služby App Service pomocí předplatného Azure nebo můžete použít dočasný Web.

Pokud ještě nemáte předplatné, začněte tématem [bezplatný účet Azure úplné](https://azure.microsoft.com/free/), což zahrnuje velkorysá kredity pro služby Azure. Také zvažte [Visual Studio Dev Essentials](https://azure.microsoft.com/pricing/member-offers/vs-dev-essentials/), kterým získáte kredit 25 USD měsíčně za celý rok.

> [!Tip]
> I když vyzve k zadání platební kartu k ověření svého účtu Azure, se neúčtuje karty. Můžete také nastavit [limit útraty](/azure/billing/billing-spending-limit) rovna vaše bezplatné kredity k zajištění, že dojde k žádné další poplatky. Kromě toho Azure nabízí free služby App Service úroveň plánu, který je ideální pro aplikace jednoduchý test, jak je popsáno v další části.

### <a name="use-a-subscription"></a>Použít jiné předplatné

S aktivní předplatné Azure vytvořte službu App Service s prázdnou webovou aplikaci následujícím způsobem:

1. Přihlaste se na [portal.azure.com](https://portal.azure.com).
1. Vyberte **+ nová**a pak vyberte **Web + mobilní zařízení** následovaný **webovou aplikaci**.
1. Zadejte název webové aplikace, ponechejte **skupiny prostředků** k **vytvořit nový**a zvolte **Windows** jako operační systém.
1. Vyberte **plán App service/umístění**vyberte **vytvořit nový**a zadejte název a umístění. Potom vyberte **cenová úroveň**, přejděte dolů a vyberte **F1 Free** plánovat, stiskněte klávesu **vyberte**následovaný **OK** a potom **Vytvořit**.
1. (Volitelné) Po vytvoření služby App Service přejít k němu, vyberte **získat profil publikování**a uložte si soubor .CSR místně.

### <a name="use-a-temporary-app-service"></a>Použijte dočasné služby App Service

Vytvořte dočasný službu App Service bez předplatného Azure následujícím způsobem:

1. Otevřete prohlížeč, abyste [try.azurewebsites.net](https://try.azurewebsites.net).
1. Vyberte **webovou aplikaci** typ aplikace vyberte **Další**.
1. Vyberte **prázdný web**následovaný **vytvořit**.
1. Přihlaste se pomocí přihlášení prostřednictvím sociální sítě podle vašeho výběru a po krátkou dobu je připraven na zobrazenou adresu URL vašeho webu.
1. Vyberte **stáhnout profil publikování** a uložit *.publishsettings* souboru, který můžete použít později.

## <a name="configure-python-on-azure-app-service"></a>Konfigurace Pythonu ve službě Azure App Service

Jakmile budete mít služby App Service s prázdnou webovou aplikací běžící (buď v rámci vašeho předplatného, nebo na bezplatné webu), nainstalujte zvolené verzi jazyka Python, jak je popsáno [Správa Pythonu ve službě Azure App Service](managing-python-on-azure-app-service.md). Publikování ze sady Visual Studio 2017, zaznamenejte přesnou cestu k interpretu Pythonu nainstalována s rozšířením webu, jak je popsáno v tomto článku.

V případě potřeby můžete také nainstalovat `bottle` balíček pomocí procesu v těchto pokynech, protože tento balíček nainstaluje jako součást jiné kroky v tomto názorném postupu.

## <a name="publish-to-app-service---visual-studio-2017"></a>Publikování do služby App Service – Visual Studio 2017

Publikování do služby Azure App Service ze sady Visual Studio 2017 kopií pouze soubory v projektu na serveru. Je proto nutné, vytvořit soubory potřebné ke konfiguraci prostředí serveru.

1. V sadě Visual Studio **Průzkumníka řešení**, klikněte pravým tlačítkem na projekt a vyberte **přidat** > **nová položka**. V dialogovém okně, které se zobrazí, vyberte **web.config pro Azure (Fastcgi)** šablony a vyberte **OK**. Tím se vytvoří *web.config* souboru v kořenovém adresáři projektu.

1. Upravit `PythonHandler` záznam v *web.config* tak, aby cesta odpovídá instalaci Pythonu na serveru (naleznete v tématu [odkaz Konfigurace služby IIS](https://www.iis.net/configreference) (iis.net) najdete přesné informace). Například pro Python 3.6.1 x64 položka by měla vypadat následovně:

    ```xml
    <system.webServer>
      <handlers>
        <add name="PythonHandler" path="*" verb="*" modules="FastCgiModule"
            scriptProcessor="D:\home\Python361x64\python.exe|D:\home\Python361x64\wfastcgi.py"
            resourceType="Unspecified" requireAccess="Script"/>
      </handlers>
    </system.webServer>
    ```

1. Nastavte `WSGI_HANDLER` záznam v *web.config* podle potřeby pro architekturu používáte:

    - **Bottle**: Přidat závorky po `app.wsgi_app` jak je znázorněno níže. To je nezbytné, protože tento objekt je funkce (viz *app.py*) namísto proměnné:

        ```xml
        <!-- Bottle apps only -->
        <add key="WSGI_HANDLER" value="app.wsgi_app()"/>
        ```

    - **Flask**: Změna `WSGI_HANDLER` hodnota, která se `<project_name>.app` kde `<project_name>` odpovídá názvu vašeho projektu. Můžete najít přesně identifikátor pohledem `from <project_name> import app` příkaz v *runserver.py*. Například pokud má projekt název "FlaskAzurePublishExample", položka bude vypadat takto:

        ```xml
        <!-- Flask apps only: change the project name to match your app -->
        <add key="WSGI_HANDLER" value="FlaskAzurePublishExample.app"/>
        ```

    - **Django**: dvě změny, které jsou potřeba k *web.config* pro projekty v Django. Nejprve změňte `WSGI_HANDLER` hodnota, která se `django.core.wsgi.get_wsgi_application()` (objekt je ve *wsgi.py* souboru):

        ```xml
        <!-- Django apps only -->
        <add key="WSGI_HANDLER" value="django.core.wsgi.get_wsgi_application()"/>
        ```

        Za druhé, přidejte následující položku níže pro `WSGI_HANDLER`a nahraďte `DjangoAzurePublishExample` s názvem vašeho projektu:

        ```xml
        <add key="DJANGO_SETTINGS_MODULE" value="DjangoAzurePublishExample.settings" />
        ```

1. **Jenom aplikace Django**: projekt v Django *settings.py* přidejte domény adresy URL webu do `ALLOWED_HOSTS` jak je znázorněno níže, nahradíte ".net vspython-test-02.azurewebsites" adresu URL a samozřejmě:

    ```python
    # Change the URL to your specific site
    ALLOWED_HOSTS = ['vspython-test-02.azurewebsites.net']
    ```

    Nepodařilo se přidat adresu URL svého výsledky do pole chyby **DisallowedHost na / neplatné záhlaví HTTP_HOST: "\<URL webu\>". Budete muset přidat "\<URL webu\>" k ALLOWED_HOSTS.**

    Pamatujte, že pokud je pole prázdné, Django umožňuje automaticky "localhost", ale přidáte vaše adresa URL výroby odebere této funkce. Pro kopie z tohoto důvodu můžete chtít udržovat samostatnou vývoje a provozu *settings.py*, nebo použít proměnné prostředí pro řízení běhu hodnoty.

1. V **Průzkumníka řešení**, rozbalte složku se stejným názvem jako váš projekt, klikněte pravým tlačítkem myši **statické** složky, vyberte **přidat** > **nová položka** , vyberte **Azure statické soubory web.config** šablony a vyberte **OK**. Tato akce vytvoří další *web.config* v *statické* složku, která zakáže zpracování pro složky Pythonu. Tato konfigurace odesílá požadavky pro statické soubory výchozí webový server, než pomocí aplikace v Pythonu.

1. Uložte projekt, pak v sadě Visual Studio **Průzkumníka řešení**, klikněte pravým tlačítkem na projekt a vyberte **publikovat**.

    ![Publikování příkazu v místní nabídce projektu](media/template-web-publish-command.png)

1. V **publikovat** kartu, která se zobrazí, vyberte cíl publikování:

    1. Ve vlastním předplatném Azure: vyberte **Microsoft Azure App Service**, pak **vybrat existující** následovaný **publikovat**. Zobrazí se dialogové okno, ve kterém můžete vybrat odpovídající předplatné a služby app service. Pokud není zobrazená služby App Service, použijte stažený profil publikování, jak je popsáno níže pro dočasné službu App Service.

       ![Publikování do Azure – krok 1, Visual Studio 2017 na stávající předplatná](media/tutorials-common-publish-1a-2017.png)

    2. Pokud používáte dočasné služby App Service na try.azurewebsites.net nebo jinak budete muset použít profil publikování, vyberte **\>** ovládacího prvku najít **importovat profil**, vyberte tuto možnost, pak Vyberte **publikovat**. Tento parametr vyzve k zadání umístění *.publishsettings* soubor předtím stáhli.

    ![Publikování do Azure – krok 1, Visual Studio 2017, dočasné app service](media/tutorials-common-publish-1b-2017.png)

1. Zobrazí stav publikování v sadě Visual Studio **aktivita publikování webu** okno a **publikovat** okna. Po dokončení publikování se otevře výchozí prohlížeč na adresu URL webu. Adresa URL je zobrazen také v **publikovat** okna.

1. Když se otevře v prohlížeči, může se zobrazit zpráva, **stránku nelze zobrazit, protože došlo k vnitřní chybě serveru.** Tato zpráva znamená, že vaše prostředí Python na serveru není úplně nakonfigurovaný, v takovém případě postupujte takto:

    1. Odkazovat na akci [Správa Pythonu ve službě Azure App Service](managing-python-on-azure-app-service.md), ujistěte se, že máte odpovídající rozšíření nainstalované na webu Pythonu.

    2. Zkontrolujte cestu k interpretu Pythonu ve vašich *web.config* souboru. Cesta musí přesně odpovídat umístění pro instalaci zvolený server rozšíření.

    3. Upgradovat všechny balíčky uvedené ve vaší aplikaci pomocí konzoly Kudu *souboru requirements.txt* souboru: přejděte do stejné složky Pythonu, který se používá v *web.config*, jako například  */home/python361x64*, a spusťte následující příkaz, jak je popsáno v [konzola Kudu](managing-python-on-azure-app-service.md#azure-app-service-kudu-console) části:

    ```command
    python -m pip install --upgrade -r /home/site/wwwroot/requirements.txt
    ```

    Pokud se zobrazí chyby oprávnění při spuštění tohoto příkazu, zkontrolujte, že používáte příkaz ve složce rozšíření lokality a *není* ve složce instalace Pythonu výchozí služby App Service. Protože nelze upravit tyto výchozí prostředí, pokus o instalaci balíčků jistě selže.

    4. Podrobné informace o chybě výstupu, přidejte následující řádek do *web.config* v rámci `<system.webServer>` uzlu, který poskytuje podrobnější chybový výstup:

    ```xml
    <httpErrors errorMode="Detailed"></httpErrors>
    ```

    5. Zkuste restartovat App Service po instalaci nové balíčky. Restart je nezbytný, při změně *web.config*, jak služby App Service nepodporuje automatické restartování vždy, když *web.config* změny.

    > [!Tip]
    > Pokud provedete změny do vaší aplikace *souboru requirements.txt* souboru, je nutné znovu pomocí konzoly Kudu nainstalovat všechny balíčky, které jsou teď uvedené v tomto souboru.

1. Po dokončení konfigurace plně serverovém prostředí, aktualizujte stránku v prohlížeči a webovou aplikaci by se měla objevit.

    ![Výsledky publikování aplikace Bottle, Flask a Django do služby App Service](media/azure-publish-results.png)

## <a name="publish-to-app-service---visual-studio-2015"></a>Publikování do služby App Service – Visual Studio 2015

> [!Note]
> Krátké video tohoto procesu můžete najít na [Visual Studio Pythonu pro tento kurz: vytváření webu](https://www.youtube.com/watch?v=FJx5mutt1uk&list=PLReL099Y5nRdLgGAdrb_YeTdEnd23s6Ff&index=6) (webu youtube.com, 3m10s).

1. V **Průzkumníka řešení**, klikněte pravým tlačítkem na projekt a vyberte **publikovat**.

1. V **publikovat** dialogového okna, vyberte **Microsoft Azure App Service**:

  ![Publikování do Azure – krok 1](media/tutorials-common-publish-1.png)

1. Vyberte cílovou třídu:

    - Pokud máte předplatné Azure, vyberte **Microsoft Azure App Service** jako cíl publikování v následujícím dialogovém okně vyberte stávající službu App Service nebo vyberte **nový** vytvořit nový certifikát.
    - Pokud používáte dočasný web z try.azurewebsites.net, vyberte **Import** jako cíl publikování, pak vyhledat *.publishsettings* soubor stáhnout z webu a vyberte **OK** .

1. Podrobnosti služby App Service se zobrazí v **publikovat** dialogového okna **připojení** kartu níže.

  ![Publikování do Azure – krok 2](media/tutorials-common-publish-2.png)

1. Vyberte **Další** podle potřeby a zkontrolujte další nastavení. Pokud máte v úmyslu [vzdáleně ladit kód Pythonu v Azure](debugging-remote-python-code-on-azure.md), je nutné nastavit **konfigurace** k **ladění**

1. Vyberte **publikovat**. Aplikaci nasadíte do Azure a váš výchozí prohlížeč otevře na dané lokalitě.

Jako součást tohoto procesu Visual Studio také provede následující kroky:

- Vytvoření *web.config* souboru na serveru, který obsahuje příslušné odkazy na aplikace `wsgi_app` fungovat a do služby App Service výchozí Python 3.4 překladač.
- Vypnout zpracování souborů v projektu *statické* složky (pravidla pro tento *web.config*).
- Virtuální prostředí publikujte na server.
- Přidat *web.debug.config* Souborová služba a ptvsd ladicí nástroje vám umožní povolit vzdálené ladění.

Jak bylo uvedeno dříve, postup automatického zjednodušení procesu publikování, ale to ztížit řízení prostředí Pythonu. Například *web.config* soubor je vytvořen pouze na serveru, ale nebyl přidán do projektu. Proces publikování také trvá déle, protože to je kopírování celé virtuální prostředí z vývojového počítače spíše než spoléhání se na konfiguraci serveru.

Nakonec můžete chtít spravovat vlastní *web.config* a *souboru requirements.txt* přímo udržovat balíčků na serveru. Pomocí *souboru requirements.txt*, zejména záruky, které prostředí vývoje a server vždy odpovídat.

## <a name="remote-debugging-on-azure-app-service"></a>Vzdálené ladění ve službě Azure App Service

Při publikování **ladění** konfigurace ze sady Visual Studio 2015 automaticky vytvoří proces *web.debug.config* soubor a přidá *ptvsd* složku obsahující Nástroje pro potřeby ladění.

Pomocí sady Visual Studio 2017 místo toho přidejte tyto součásti přímo do projektu. Klikněte pravým tlačítkem na projekt v **Průzkumníka řešení**vyberte **přidat** > **nová položka**a vyberte **Azure vzdálené ladění v souboru web.config** šablony. Pro ladění *web.debug.config* souboru a *ptvsd* složky nástroje se zobrazí ve vašem projektu.

Jakmile tyto soubory jsou nasazeny na server (automaticky pomocí sady Visual Studio 2015; v příštím publikování se sadou Visual Studio 2017), můžete postupovat podle pokynů pro [vzdálené ladění Azure](debugging-remote-python-code-on-azure.md).
