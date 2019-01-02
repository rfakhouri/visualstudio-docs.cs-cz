---
title: 'Chyba: Webový server není správně nakonfigurován. | Dokumentace Microsoftu'
ms.date: 09/20/2017
ms.topic: troubleshooting
f1_keywords:
- vs.debug.remote.projnotconfigured
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugger, Web application errors
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2606304ba68530c7ec893dae9cbb4954cae33112
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53887487"
---
# <a name="error-the-web-server-is-not-configured-correctly"></a>Chyba: Webový server není správně nakonfigurovaný.

Až provedete kroky popsané tady řešení tohoto problému a před dalším pokusem o ladění může být také potřeba resetovat služby IIS. Můžete to udělat tak, že otevřete příkazový řádek správce a zadáním `iisreset`.

Proveďte tyto kroky k vyřešení tohoto problému:

1. Pokud webové aplikace hostované na serveru je nakonfigurovaný jako znovu publikovat jako sestavení pro ladění sestavení pro vydání a ověřte, že soubor web.config obsahuje `debug=true` v elementu kompilace. Resetování služby IIS a zkuste to znovu.

    Pokud používáte profil publikování pro sestavení pro vydání, změňte ho na ladění a znovu publikovat. V opačném případě bude nastaven atribut ladění `false` po publikování.

2. SLUŽBY (IIS) Ověřte správnost fyzickou cestu. Ve službě IIS, najdete v tomto nastavení **základní nastavení > fyzická cesta** (nebo **Upřesnit nastavení** ve starších verzích služby IIS).

    Fyzická cesta může být nesprávný, pokud webová aplikace byl zkopírován do jiného počítače, ručně přejmenovat nebo přesunout. Resetování služby IIS a zkuste to znovu.

3. Jestliže ladíte místně v sadě Visual Studio, ověřte, že je vybrán správný server ve vlastnostech. (Otevřete **vlastnosti > Web > servery** nebo **vlastnosti > ladění** v závislosti na typu vašeho projektu. Pro projekt webových formulářů, otevřete **stránky vlastností > Možnosti spuštění > Server**).

    Pokud používáte externí (vlastní) serveru, například službou IIS, adresa URL musí být správná. V opačném případě vyberte služby IIS Express a zkuste to znovu.

4. SLUŽBY (IIS) Ujistěte se, že je na serveru nainstalována správná verze technologie ASP.NET.

    Neshoda verzí technologie ASP.NET ve službě IIS a v projektu sady Visual Studio může způsobit potíže. Budete muset nastavit verzi rozhraní framework v souboru web.config. Instalace technologie ASP.NET na IIS, použijte [instalačního programu webové platformy (WebPI)](https://www.microsoft.com/web/downloads/platform.aspx). Viz také [IIS 8.0 pomocí technologie ASP.NET 3.5 a technologii ASP.NET 4.5](/iis/get-started/whats-new-in-iis-8/iis-80-using-aspnet-35-and-aspnet-45) nebo pro ASP.NET Core, [hostitelská služba ve Windows se službou IIS](https://docs.asp.net/en/latest/publishing/iis.html).
  
4. Pokud `maxConnection` limit ve službě IIS je příliš nízká a máte příliš mnoho připojení, možná budete muset [zvýšil limit připojení](/iis/configuration/system.applicationhost/sites/sitedefaults/limits).
  
## <a name="see-also"></a>Viz také  
 [Vzdálené ladění ASP.NET na počítači vzdálené služby IIS](../debugger/remote-debugging-aspnet-on-a-remote-iis-7-5-computer.md)   
 [Ladění webových aplikací: Chyby a řešení potíží](../debugger/debugging-web-applications-errors-and-troubleshooting.md)