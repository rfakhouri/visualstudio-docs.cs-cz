---
title: Povolení ladění pro aplikace ASP.NET | Microsoft Docs
ms.custom: H1HackMay2017
ms.date: 09/21/17
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging ASP.NET Web applications
- Web.config configuration file, debug mode
- debugging [Visual Studio], ASP.NET
ms.assetid: 3beed819-cece-4864-8184-bd410000973a
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- aspnet
ms.openlocfilehash: 438e5a96ef07faf399d06ae517afe313a44673b4
ms.sourcegitcommit: 0bf2aff6abe485e3fe940f5344a62a885ad7f44e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/27/2018
ms.locfileid: "37057847"
---
# <a name="debug-aspnet-applications-in-visual-studio"></a>Ladění aplikací ASP.NET v sadě Visual Studio

Můžete ladit aplikace ASP.NET v sadě Visual Studio.

## <a name="requirements"></a>Požadavky

Podle pokynů v tomto tématu, potřebujete:

- Služba IIS Express, který je zahrnutý ve výchozím nastavení v sadě Visual Studio 2012 a novější

    -nebo-

- Místní služby IIS webový server (verze 8.0 nebo novější), správně nakonfigurovaná, a můžete spustit aplikace ASP.NET bez chyb.

Pokud je vzdálený server, musí být na vzdáleném počítači spuštěny vzdáleného ladicího programu. Chcete-li ladit na vzdáleném serveru služby IIS, přečtěte si téma [vzdáleného ladění ASP.NET na počítači se službou IIS](../debugger/remote-debugging-aspnet-on-a-remote-iis-7-5-computer.md). 

## <a name="configure-debug-settings"></a>Konfigurace nastavení pro ladění

### <a name="enable-aspnet-debugging-in-the-project-properties"></a>Povolit ladění ASP.NET ve vlastnostech projektu

1. Otevřete projekt ASP.NET v sadě Visual Studio.

2. Klikněte pravým tlačítkem na projekt v **Průzkumníku řešení**, zvolte **vlastnosti**a klikněte **webové** karta.

    Pro některé typy projektů vyberte **vlastnosti > ladění** místo. Pro projekt webové formuláře ASP.NET, klikněte pravým tlačítkem na projekt a vyberte **stránky vlastností > Možnosti spuštění**.
  
3.  V části **ladicí programy**, vyberte **ASP.NET** zaškrtávací políčko.

    ![Nastavení ladicího programu](../debugger/media/dbg-aspnet-enable-debugging.png "nastavení ladicího programu")

> [!NOTE]
> Pokud vytvoříte nový projekt ASP.NET (**soubor > Nový projekt**), nastavení pro ladění jsou již nakonfigurované správně.

### <a name="enable-debugging-in-the-webconfig-file"></a>Povolit ladění v souboru web.config  

Chcete-li ladit webové aplikace, musí být správně nakonfigurované souboru web.config aplikace. Soubor web.config je požadována, pokud hostování aplikace služby IIS nebo IIS Express.

Pro ASP.NET Core v souboru web.config se vytvoří automaticky při nasazení aplikace (Pokud již není přítomen).

> [!TIP]
> Váš proces nasazení může aktualizovat nastavení v souboru web.config. Proto před pokusem o ladění, ověřte nastavení web.config na serveru.
  
1.  V sadě Visual Studio otevřete soubor web.config.  
  
    > [!NOTE]  
    > V souboru web.config nelze přistupovat vzdáleně pomocí webového prohlížeče. Z bezpečnostních důvodů konfiguruje [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] službu Microsoft IIS pro zabránění přímého přístupu prohlížeče k souborům Web.config. Pokud se pokusíte přístup k souboru konfigurace pomocí prohlížeče, dojde k chybě přístup protokolu HTTP 403 (zakázáno).  
  
2.  Vyhledejte element `configuration/system.web/compilation`. Pokud element compilation neexistuje, vytvořte jej.

    Soubor web.config je soubor XML, obsahuje proto vnořené oddíly označené značkami.
  
3.  Pokud element `compilation` neobsahuje atribut `debug`, přidejte tento atribut do elementu.  
  
4.  Ujistěte se, že je hodnota atributu `debug` nastavena na `true`.  
  
V souboru web.config by měl vypadat jako v následujícím příkladu:

> [!NOTE]
> V tomto příkladu je soubor web.config částečné. Další části XML nejsou obvykle mezi konfiguračním a system.web elementy. Element kompilace může také obsahovat další atributy a elementy.
  
#### <a name="example"></a>Příklad  
  
```xml
<configuration>  
    ...  
    <system.web>  
        <compilation  
            debug="true"  
            ...  
        >  
        ...  
        </compilation>  
    </system.web>  
</configuration>  
```

Pokud používáte externí server místo výchozí server služby IIS Express, je nutné také zkontrolujte, zda `targetFramework` hodnota atributu odpovídá konfiguraci na serveru.

> [!IMPORTANT]
> Pro nejlepší výkon, nastavte produkční aplikace `debug=false` a zadat sestavení pro vydání, při vytvoření a publikování aplikace.

## <a name="configure-project-settings-for-the-server"></a>Konfigurace nastavení projektu pro server

Pro ladění na místní webový server, nastavte vlastnosti projektu. Pro ladění na vzdáleném serveru, postupujte podle pokynů komplexnější popsané v [vzdáleného ladění ASP.NET ve službě IIS](../debugger/remote-debugging-aspnet-on-a-remote-iis-7-5-computer.md) místo.

1. V **webové** Karta projektu vlastnosti, vyberte buď **IIS Express** nebo **externího serveru** pod **Server** nastavení. (Pro některé typy projektů, tato nastavení se zobrazí pod **ladění** kartě místo.)

    ![Nastavení serveru](../debugger/media/dbg-aspnet-server-settings.png "nastavení serveru")

    Služba IIS Express je výchozí server pro technologii ASP.NET a obvykle nevyžaduje žádnou zvláštní konfiguraci. Toto je nejjednodušší způsob, jak ladit aplikaci ASP.NET.

    Pro projekt webové formuláře ASP.NET, klikněte pravým tlačítkem na projekt, vyberte **stránky vlastností > Možnosti spuštění**a vyberte buď **použít výchozí webový server** nebo **použít vlastní server** () místo **externího serveru**).

    ![Nastavení serveru pro aplikace webových formulářů](../debugger/media/dbg-aspnet-server-settings-webforms.png "nastavení serveru pro aplikace webových formulářů")

2. Pokud si zvolíte externího serveru (vlastní), zadejte správnou adresu URL v **adresa URL projektu** (nebo **základní adresa URL**) pole.

    Pokud je externí server místní služba IIS, IIS musí být správně nainstalována a nakonfigurována. Například musí být nakonfigurován správnou verzi technologie ASP.NET ve službě IIS. Další informace najdete v tématu [IIS 8.0 pomocí technologie ASP.NET 3.5 a technologii ASP.NET 4.5](/iis/get-started/whats-new-in-iis-8/iis-80-using-aspnet-35-and-aspnet-45). Pokud budete chtít otestovat nasazení, jakož i ladění, přečtěte si téma [nasazení otestovat](/aspnet/web-forms/overview/deployment/visual-studio-web-deployment/deploying-to-iis).

    Pokud je externí server [vzdáleného](../debugger/remote-debugging-aspnet-on-a-remote-iis-7-5-computer.md), místo toho připojit k procesu a nepoužívají se tato nastavení projektu pro ladění.

## <a name="local-iis-web-server-configure-iis"></a>(Místní služba IIS webový server) Konfigurace služby IIS

Pro službu IIS Express, nemusíte konfigurovat webový server (tuto část přeskočte). Služba IIS Express se doporučuje pro počáteční testování.

Pokud používáte místní webový server IIS, postupujte podle těchto kroků.

1. Ujistěte se, zda je služba IIS správně nainstalován. Další informace najdete v tématu [IIS 8.0 pomocí technologie ASP.NET 3.5 a technologii ASP.NET 4.5](/iis/get-started/whats-new-in-iis-8/iis-80-using-aspnet-35-and-aspnet-45).

    * Ujistěte se, že instalujete správnou verzi ASP.NET na serveru. Instalace webové platformy (WebPI) použít k instalaci technologie ASP.NET 4.5 (z uzlu serveru v systému Windows Server 2012 R2, zvolte **získat nové komponenty webové platformy** a poté vyhledejte ASP.NET). K instalaci ASP.NET Core, najdete v části [publikování do služby IIS](https://docs.asp.net/en/latest/publishing/iis.html#iis-configuration).

    > [!NOTE]
    > Pokud používáte Windows Server 2008 R2, nainstalujte technologii ASP.NET 4 místo použití tohoto příkazu:

     **C:\Windows\Microsoft.NET\Framework64\v4.0.30319\aspnet_regiis.exe -ir**

2. Otevřete **Internetová informační služba (IIS) Manager**. (V levém podokně Správce serveru, vyberte **IIS**. Pravým tlačítkem na server a vyberte **Správce Internetové informační služby (IIS)**.)

3. V části **připojení** v levém podokně přejděte do **lokality**.

4. Klikněte pravým tlačítkem myši **Default Web Site** uzel a vyberte možnost **přidat aplikaci**.

5. Nastavte **Alias** do **MyASPApp**, přijměte výchozí nastavení fondu aplikací (**DefaultAppPool**) a nastavte **fyzická cesta** k  **C:\inetpub\myNewFolder** (vytvořit novou složku pro aplikaci).

6. V části **připojení**, vyberte **fondy aplikací**. Otevřete **DefaultAppPool** a nastavte hodnotu pole fondu aplikací na hodnotu, která je správný pro vaši aplikaci (používá technologii ASP.NET 4 pro technologii ASP.NET 4.5. Použít **bez spravovaného kódu** pro ASP.NET Core).

## <a name="local-iis-web-server-deploy-the-app"></a>(Místní služba IIS webový server) Nasazení aplikace

Pro službu IIS Express, webové aplikace je nasazená automaticky při spuštění ladění (tuto část přeskočte).

Pokud používáte místní webový server IIS, postupujte podle těchto kroků. Publikování aplikace do služby IIS různými způsoby. V následujícím postupu ukážeme, jak vytvořit a použít profil publikování, abyste mohli nasadit pomocí systému souborů.

1. Restartujte Visual Studio jako správce.

    Pokud chcete nasadit pomocí této metody, potřebujete práva správce.

2. V sadě Visual Studio, klikněte pravým tlačítkem na projekt a zvolte **publikovat** (webových formulářů, použijte **publikování webové aplikace**).

3. Zvolte **služby IIS, FTP, atd.** a klikněte na tlačítko **publikovat**.

    ![Publikování do služby IIS](../debugger/media/dbg-aspnet-local-iis.png "publikování do služby IIS")

    Pro aplikace webových formulářů, zvolte **vlastní** v dialogovém okně Publikovat zadejte název profilu a vyberte **OK**.

4. V **metodu publikování** pole, zvolte **systém souborů**.

5. Pro **cílové umístění**, klikněte **Procházet** tlačítko.

6. (ASP.NET jader) Zvolte **systém souborů** a vyberte složku, kam jste dříve vytvořili pro aplikaci.

6. (ASP.NET) Zvolte **místní služba IIS**a vyberte web dřív vytvořili a pak klikněte na tlačítko **otevřete**.

    ![Publikování do služby IIS](../debugger/media/dbg-aspnet-local-iis-select-site.png "publikování do služby IIS")

    > [!TIP]
    > Pokud uvidíte, že zpráva, že webový server není správně nakonfigurován, ujistěte se, že je nainstalována správná verze technologie ASP.NET pro službu IIS.

7. Klikněte na tlačítko **Další** a vyberte **ladění** konfigurace.

    > [!NOTE]
    > Pokud nasadíte s konfigurací verze, nastaví tato `debug=false` v souboru web.config serveru.

8. Klikněte na tlačítko **Uložit** uložit nastavení publikování, a pak klikněte na **publikovat**.

    > [!CAUTION]
    >  Pokud potřebujete provést změny kódu nebo opětovné sestavení, musíte znovu publikovat a opakujte tento krok. Spustitelný soubor, který jste zkopírovali ke vzdálenému počítači se musí přesně shodovat místního zdroje a symboly.

## <a name="set-a-breakpoint-and-start-debugging"></a>Nastavit zarážky a spuštění ladění

1. Ve vašem projektu v sadě Visual Studio, sada zarážek na nějaký kód, který víte, poběží.

2. Chcete-li začít, ladění, stiskněte **F5** (**ladění > Spustit ladění**).

3. Kroky k spustit kód, který obsahuje zarážku.

    Ladicí program zastaví, kde nastavit bod přerušení.

### <a name="local-iis-troubleshooting-cannot-hit-the-breakpoint"></a>(Místní služba IIS) Řešení potíží: Nelze průchodu zarážkou

1. Spustí webovou aplikaci služby IIS a ujistěte se, že běží správně. Ponechte webová aplikace spuštěná.

2. Ze sady Visual Studio, vyberte **ladění > připojit k procesu** a připojte se k procesu ASP.NET (obvykle **w3wp.exe** nebo **dotnet.exe**). Další informace najdete v tématu [připojit k procesu](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md).

    Pokud budete moci připojit pomocí **připojit k procesu** a zasáhnout zarážku, ale nelze spustit ladění pomocí **F5**, pak je pravděpodobné, že je nastavení nesprávná ve vlastnostech projektu. Pokud používáte souboru HOSTITELŮ, ověřte, zda je správně nakonfigurována.

  
## <a name="robust-programming"></a>Robustní programování  
[!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] automaticky detekuje jakékoli změny v souboru Web.config a aplikuje nové nastavení konfigurace. Není nutné restartovat počítač nebo restartujte server IIS pro změny se projeví.  
  
Webová stránka může obsahovat více virtuálních adresářů a podadresářů a soubory Web.config mohou existovat v každém z nich. Aplikace [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] dědí nastavení ze souborů Web.config, které jsou v cestě adresy URL výše. Hierarchické konfigurační soubory umožňují změnit nastavení pro několik aplikací [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] současně, jako například pro všechny aplikace v hierarchii pod ní. Ale pokud `debug` je nastavena v souboru, která je nižší úrovni v hierarchii, přepíše vyšší hodnotu.  
  
Například můžete zadat `debug="true"` v www.microsoft.com/aaa/Web.config a všechny aplikace ve složce aaa nebo v jakékoli podsložkou aaa toto nastavení dědí. Takže když vaše [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] aplikace je na www.microsoft.com/aaa/bbb, dědí nastavení, protože se některé [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] aplikace v www.microsoft.com/aaa/ccc, www.microsoft.com/aaa/ddd a tak dále. Jedinou výjimkou je, pokud jedna z těchto aplikací přepíše nastavení pomocí vlastního nižšího souboru Web.config.  
  
> [!IMPORTANT]
> Povolení režimu ladění výrazně ovlivní výkon vaší [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] aplikace. Nezapomeňte vypnout režim ladění před nasazením vydání aplikace nebo před měřením výkonu.  
  
## <a name="see-also"></a>Viz také  
[ASP.NET ladění: systémové požadavky](aspnet-debugging-system-requirements.md)   
[Postupy: spuštění pracovního procesu pod účtem uživatele](how-to-run-the-worker-process-under-a-user-account.md)   
[Postupy: hledání názvu procesu ASP.NET](how-to-find-the-name-of-the-aspnet-process.md)   
[Ladění nasazených webových aplikací](debugging-deployed-web-applications.md)   
[Návod: Ladění webového formuláře](walkthrough-debugging-a-web-form.md)   
[Postupy: ladění výjimek ASP.NET](how-to-debug-aspnet-exceptions.md)   
[Ladění webových aplikací: Chyby a řešení potíží](debugging-web-applications-errors-and-troubleshooting.md)
  
