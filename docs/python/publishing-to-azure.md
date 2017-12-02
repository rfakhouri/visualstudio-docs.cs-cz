---
title: "Publikování aplikace Python do Azure App Service ze sady Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 09/27/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: article
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.openlocfilehash: a4f9ec85a7fa37c871344500cc412e57d8019100
ms.sourcegitcommit: b7d3b90d0be597c9d01879338dd2678c881087ce
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/01/2017
---
# <a name="publishing-to-azure-app-service"></a>Publikování do služby Azure App Service

Visual Studio poskytuje schopnost přímo publikovat webovou aplikaci Python přímo do služby Azure App Service. Publikování do služby Azure App Service znamená kopírování potřebné soubory na server a nastavením odpovídající `web.config` soubor, který se dá pokyn webového serveru, jak spusťte aplikaci. 

Proces publikování se liší mezi Visual Studio 2017 a Visual Studio 2015. Konkrétně Visual Studio 2015 automatizuje některé z kroků, včetně vytváření `web.config`, ale tato automatizace omezuje dlouhodobé flexibilitu a řízení. Visual Studio 2017 vyžaduje další provedení ručních kroků, ale zajišťuje přesnější kontrolu nad prostředí Python. Obě možnosti jsou popsány zde.

V tomto tématu:
- [Požadavky](#prerequisites)
- [Vytvoření služby Azure App Service](#create-an-azure-app-service)
- [Konfigurace Python v App Service](#configure-python-on-app-service)
- [Publikování do služby App Service - Visual Studio 2017](#publish-to-app-service-visual-studio-2017)
- [Publikování do služby App Service – Visual Studio 2015](#publish-to-app-service-visual-studio-2015)
- [Vzdálené ladění na služby App Service](#remote-debugging-on-app-service)

> [!Note]
> Pozadí na změny mezi Visual Studio 2015 a Visual Studio 2017, naleznete v příspěvku blogu, [publikovat do Azure na Visual Studio 2017](https://blogs.msdn.microsoft.com/pythonengineering/2016/12/12/publish-to-azure-in-vs-2017/).

## <a name="prerequisites"></a>Požadavky

V tomto návodu budete potřebovat projekt webové aplikace založené na rozhraní Bottle, Flask a Django. Pokud ještě nemáte projektu a chcete pokusit proces publikování, vytvoření projektu jednoduchá testovací následujícím způsobem:

1. V sadě Visual Studio, vyberte **soubor > Nový > projekt**, vyhledejte "Bottle", vyberte **Bottle webového projektu**, zadejte a název a cestu k projektu, klikněte na tlačítko **OK**. (Je součástí zatížení Python vývoj šablona Bottle; viz [instalace](installation.md).)

1. Postupujte podle pokynů k instalaci externích balíčků, výběr **nainstalovat do virtuálního prostředí** a vaše upřednostňované základní překladač pro virtuální prostředí. Tato volba verze jazyka Python, které jsou nainstalované v App Service se obvykle shodují.

1. Testování projektu místně stisknutím klávesy F5 nebo výběrem **ladění > Spustit ladění**. 


## <a name="create-an-azure-app-service"></a>Vytvoření služby Azure App Service

Publikování do služby Azure vyžaduje cíl služby App Service. Pro tento účel můžete vytvořit služby App Service pomocí předplatného Azure, nebo můžete použít dočasnou lokalitu.

Pokud ještě nemáte předplatné, začínat [bezplatný účet Azure úplné](https://azure.microsoft.com/en-us/free/), což zahrnuje štědrém kredity u služby Azure. Také vzít v úvahu registrujete [Visual Studio Dev Essentials](https://azure.microsoft.com/en-us/pricing/member-offers/vs-dev-essentials/), který vám dává 25 platební každý měsíc jeden rok.

> [!Tip]
> I když Azure požádá o platební karty se ověřit svůj účet, karta se nic nestrhne. Můžete také nastavit [útrat](https://docs.microsoft.com/azure/billing/billing-spending-limit) rovna vaší bezplatný kredit zaručit, že dojde k žádné další poplatky. Kromě toho Azure poskytuje bezplatné služby App Service vrstvy plán, který je ideální pro jednoduchá testovací aplikace, jak je popsáno v následující části.

### <a name="using-a-subscription"></a>Použití předplatného

S aktivní předplatné Azure vytvořte aplikační službu s prázdnou webovou aplikaci takto:

1. Přihlaste se na [portal.azure.com](https://portal.azure.com).
1. Vyberte **+ nový**, pak vyberte **Web + mobilní** následuje **webové aplikace**.
1. Zadejte název webové aplikace, ponechejte **skupiny prostředků** "Vytvořit nové" a zvolte **Windows** jako operační systém.
1. Vyberte **umístění plán služby App**, vyberte **vytvořit nový**a zadejte název a umístění. Potom vyberte **cenová úroveň**, přejděte dolů a vyberte **F1 Free** plánování, stiskněte klávesu **vyberte**, za nímž následují **OK** a potom **Vytvořit**.
1. (Volitelné) Po vytvoření služby App Service, přejděte k němu, vyberte **profilu publikování Get**a uložte soubor místně.

### <a name="using-a-temporary-app-service"></a>Pomocí dočasného služby App Service

Vytvořte dočasnou služby App Service bez předplatného Azure následujícím způsobem:

1. Otevřete prohlížeč, abyste [try.azurewebsites.net](https://try.azurewebsites.net).
1. Vyberte **webové aplikace** typu aplikace, pak vyberte **Další**.
1. Vyberte **prázdný web**, za nímž následují **vytvořit**.
1. Přihlaste se pomocí přihlášení prostřednictvím sociální sítě své volby a po krátkou dobu je připraven na zobrazené adrese URL vaší lokality.
1. Vyberte **stáhnout profil publikování** a uložte `.publishsettings` souboru, který můžete použít později.


## <a name="configure-python-on-azure-app-service"></a>Konfigurace Python v Azure App Service

Jakmile je aplikační službu s prázdnou webová aplikace spuštěná, (buď v rámci vašeho předplatného nebo na lokalitu volné), nainstalujte zvolené verzi jazyka Python, jak je popsáno [Správa Python ve službě Azure App Service](managing-python-on-azure-app-service.md). Publikování z Visual Studio 2017 záznam přesnou cestu k překladač Pythonu nainstalované s příponou lokality, jak je popsáno v tomto tématu.

V případě potřeby můžete taky nainstalovat `bottle` balíček pomocí procesu v těchto pokynech, protože tento balíček je nainstalován jako součást další kroky v tomto návodu.

## <a name="publish-to-app-service---visual-studio-2017"></a>Publikování do služby App Service - Visual Studio 2017

Publikování do služby Azure App Service z kopie Visual Studio 2017 pouze soubory v projektu na server. Je proto nutné, vytvoření potřebné soubory pro konfiguraci prostředí serveru.

1. V sadě Visual Studio **Průzkumníku řešení**, klikněte pravým tlačítkem na projekt a vyberte **Přidat > novou položku...* . V dialogovém okně se zobrazí výběrem šablony "Azure web.config (rychlé CGI)" a vyberte možnost OK. Tím se vytvoří `web.config` souboru do kořenového adresáře projektu. 

1. Změnit `PythonHandler` položku v `web.config` tak, aby cesta odpovídá Python instalace na serveru. Příklad pro jazyk Python 3.6.1 x64 položky by měl vypadat takto:
    
    ```xml
    <system.webServer>
      <handlers>
        <add name="PythonHandler" path="*" verb="*" modules="FastCgiModule"
            scriptProcessor="D:\home\Python361x64\python.exe|D:\home\Python361x64\wfastcgi.py"
            resourceType="Unspecified" requireAccess="Script"/>
      </handlers>
    </system.webServer>
    ```

1. Nastavte `WSGI_HANDLER` položku v `web.config` podle potřeby pro architekturu používáte:

    - **Bottle**: přidejte závorkách po `app.wsgi_app` jak je uvedeno níže. To je nezbytné, protože tento objekt je funkce (viz `app.py`) namísto proměnné:
   
        ```xml
        <!-- Bottle apps only -->
        <add key="WSGI_HANDLER" value="app.wsgi_app()"/>
        ```

    - **Flask**: Změna `WSGI_HANDLER` hodnotu `<project_name>.app` kde `<project_name>` odpovídá názvu projektu. Můžete najít přesný identifikátor prohlížením `from <project_name> import app` příkaz v `runserver.py`. Například pokud projekt s názvem "FlaskAzurePublishExample", položka by měly vypadat následovně:

        ```xml
        <!-- Flask apps only: change the project name to match your app -->
        <add key="WSGI_HANDLER" value="FlaskAzurePublishExample.app"/>
        ```

    - **Django**: dvě změny jsou potřeba k `web.config` pro aplikace Django. Nejprve změnit `WSGI_HANDLER` hodnotu `django.core.wsgi.get_wsgi_application()` (objekt je ve `wsgi.py` souborů):

        ```xml
        <!-- Django apps only -->
        <add key="WSGI_HANDLER" value="django.core.wsgi.get_wsgi_application()"/>
        ```

        Druhý, přidejte následující položku pod pro `WSGI_HANDLER`, ve které nahradíte `DjangoAzurePublishExample` s názvem projektu:

        ```xml
        <add key="DJANGO_SETTINGS_MODULE" value="DjangoAzurePublishExample.settings" />
        ```

1. **Jenom aplikace Django**: ve složce, která odpovídá názvu vašeho projektu, otevřete `settings.py` a přidejte domény adresy URL webu `ALLOWED_HOSTS` jak vidíte níže, nahraďte 'vspython-test-02.azurewebsites .net, adresa URL, samozřejmě:

    ```python
    # Change the URL to your specific site
    ALLOWED_HOSTS = ['vspython-test-02.azurewebsites.net']
    ```

    Nepodařilo se přidat adresu URL do pole výsledků v chybě "DisallowedHost / neplatný HTTP_HOST záhlaví: '\<URL webů\>'. Budete muset přidat '\<URL webů\>' k ALLOWED_HOSTS. "

1. V **Průzkumníku řešení**, rozbalte složku se stejným názvem jako projektu, klikněte pravým tlačítkem myši `static` složky, vyberte **Přidat > novou položku...** , vyberte šablonu, "Azure statické soubory web.config" a vyberte **OK**. Tato akce vytvoří jiné `web.config` v `static` složky, která zakáže Python zpracování pro tuto složku. Tato konfigurace zasílá požadavky pro statické soubory na webový server výchozí spíše než v aplikaci Python.
  
1. Uložte projekt, pak v sadě Visual Studio **Průzkumníku řešení**, klikněte pravým tlačítkem na projekt a vyberte **publikovat**. 

1. V **publikovat** kartu, která se zobrazí, vyberte cíl publikování:

    a. Vlastní předplatné: vyberte **Microsoft Azure App Service**, pak **vybrat existující** následuje **publikovat**. Zobrazí se dialogové okno, ve kterém můžete vybrat odpovídající předplatné a služby app service. Pokud App Service se nezobrazí, použijte stažený profil publikování, jak je popsáno níže pro dočasné APp Service.
    
    ![Publikovat do Azure kroku 1, Visual Studio 2017 existující odběry](media/tutorials-common-publish-1a-2017.png)

    b. Pokud používáte dočasné služby App Service na try.azurewebsites.net nebo jinak budete muset použít profil publikování, vyberte  **>**  řízení najít **importovat profil**, vyberte tuto možnost, pak Vyberte **publikovat**. Tento parametr vyzve k zadání umístění `.publishsettings` soubor předtím stáhli.

    ![Publikovat do Azure kroku 1, Visual Studio 2017 dočasné aplikační služby](media/tutorials-common-publish-1b-2017.png)    

1.  Visual Studio zobrazí stav publikování v okně "Aktivity publikování webového" a okna Publikovat. Po dokončení publikování výchozí prohlížeč otevře na adresu URL webu. Adresa URL je také zobrazí v okně publikování.

1. Když se otevře v prohlížeči, zobrazí se zpráva "stránku nelze zobrazit, protože došlo k vnitřní chybě serveru." Tato zpráva znamená, že vaše prostředí Python na serveru není plně konfigurována, v takovém případě provést následující kroky:

    a. Odkazovat znovu do [Správa Python ve službě Azure App Service](managing-python-on-azure-app-service.md), a ujistěte se, že máte odpovídající Python lokality rozšíření nainstalovat.
     
    b. Zkontrolujte cestu k překladač Pythonu ve vaší `web.config` souboru. Cesta musí přesně shodovat umístění instalovat rozšíření zvolené lokality.    
 
    c. Pomocí konzole Kudu můžete upgradovat všechny balíčky uvedené ve vaší aplikaci `requirements.txt` souboru: přejděte do stejné složky Python, který se používá v `web.config`, jako například `/home/python361x64`, a spusťte následující příkaz, jak je popsáno v [Kudu konzole](managing-python-on-azure-app-service.md#azure-app-service-kudu-console)části:

    ```
    python -m pip install --upgrade -r /home/site/wwwroot/requirements.txt
    ```          

    Pokud se zobrazí chyby oprávnění při spuštění tohoto příkazu, zkontrolujte, že příkaz spouštíte ve složce rozšíření lokality a *není* ve složce jednoho z instalace Python výchozí služby App Service. Protože tato výchozí prostředí nelze změnit, pokusu o instalaci balíčků bude jistě nezdaří.

    d. Pro výstup podrobné informace o chybě, přidejte následující řádek na `web.config` v rámci `<system.webServer>` uzlu, který poskytuje podrobnější chyba výstupu:

    ```xml
    <httpErrors errorMode="Detailed"></httpErrors>
    ```

    e. Zkuste restartovat App Service po instalaci nové balíčky. Restart je nezbytný, při změně `web.config`, jak služba aplikace nemá automatické restartování vždy, když `web.config` změny.

    > [!Tip] 
    > Pokud provedete změny do vaší aplikace `requirements.txt` souboru, je nutné znovu nainstalovat všechny balíčky, které jsou nyní uvedeny v tomto souboru pomocí konzole Kudu. 

1. Po dokončení konfigurace plně prostředí serveru, aktualizujte stránku v prohlížeči a webové aplikace by se měla objevit.

    ![Výsledky publikování Bottle, Flask a Django aplikace do služby App Service](media/azure-publish-results.png)


## <a name="publishing-to-app-service---visual-studio-2015"></a>Publikování do služby App Service – Visual Studio 2015

> [!Note] 
> Krátké video tohoto procesu můžete najít na [kurzu Python Visual Studio: vytváření webu](https://www.youtube.com/watch?v=FJx5mutt1uk&list=PLReL099Y5nRdLgGAdrb_YeTdEnd23s6Ff&index=6) (webu youtube.com, 3m10s). 

1. V **Průzkumníku řešení**, klikněte pravým tlačítkem na projekt vyberte **publikovat**. 

1. V **publikovat** dialogovém okně, vyberte **Microsoft Azure App Service**:

  ![Publikovat do Azure – krok 1](media/tutorials-common-publish-1.png)

1. Vyberte cíl:

    - Pokud máte předplatné Azure, vyberte **Microsoft Azure App Service** publikování cíl, pak v dialogovém okně následující vyberte stávající službu App Service nebo **nový** vytvořit nový.
    - Pokud používáte lokalitu dočasné z try.azurewebsites.net, vyberte **Import** publikování cíl, pak vyhledat `.publishsettings` soubor stáhnout z webu a vyberte **OK**.

1. Podrobnosti služby App Service se zobrazí v **publikovat** dialogovém okně **připojení** níže uvedené kartě.

  ![Publikovat do Azure – krok 2](media/tutorials-common-publish-2.png)

1. Vyberte **Další >** podle potřeby zkontrolovat další nastavení. Pokud máte v úmyslu [vzdáleně ladit kód Python ve službě Azure](debugging-azure-remote.md), je nutné nastavit **konfigurace** k **ladění**

1. Vyberte **publikování**. Jakmile vaše aplikace je nasazená do Azure, výchozí prohlížeč otevře na daném webu. 

Jako součást tohoto procesu Visual Studio také provede následující kroky:

- Vytvoření `web.config` soubor na serveru, který obsahuje příslušné odkazy na aplikace `wsgi_app` funkce a do služby App Service výchozí Python 3.4 překladač.
- Vypnout zpracování pro soubory v projektu `static` složky (Tato pravidla jsou ve `web.config`).
- Publikujte virtuální prostředí pro server.
- Přidat `web.debug.config` souborové služby a ptvsd ladění nástrojů, která umožňuje vzdálené ladění.
 
Jak již bylo uvedeno dříve, automatické takto zjednodušit proces publikování, ale to ztížit k řízení prostředí Python. Například `web.config` soubor je vytvořen pouze na serveru, ale není přidán do projektu. Proces publikování také trvá déle, protože kopírování celý virtuální prostředí z vývojovém počítači místo bude spoléhat na konfiguraci serveru.

Nakonec můžete chtít zachovat vlastní `web.config` souboru a používat `requirements.txt` přímo udržovat balíčků na serveru. Pomocí `requirements.txt`, zejména záruky, které vaše prostředí pro vývoj a server vždy odpovídat.

## <a name="remote-debugging-on-azure-app-service"></a>Vzdálené ladění na Azure App Service

Když publikujete konfiguraci ladění z Visual Studia 2015, proces automaticky vytvoří `web.debug.config` souboru a přidá `ptvsd` nástroje složku obsahující potřebné ladění.

S Visual Studio 2017 místo toho přidejte tyto součásti přímo do projektu. Klikněte pravým tlačítkem na projekt v **Průzkumníku řešení**, vyberte **Přidat > novou položku...** a vyberte šablonu "Azure vzdálené ladění web.config". Ladění `web.debug.config` souboru a `ptvsd` nástroj složky objeví ve vašem projektu.

Jakmile tyto soubory jsou nasazeny na server (automaticky s Visual Studiem 2015; v příštím publikování s Visual Studio 2017), můžete postupovat podle pokynů pro [Azure vzdálené ladění](https://docs.microsoft.com/visualstudio/python/debugging-azure-remote).
