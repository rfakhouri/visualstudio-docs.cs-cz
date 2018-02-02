---
title: "Nelze se připojit k Microsoft Visual Studio Remote Debugging Monitor | Microsoft Docs"
ms.custom: 
ms.date: 08/24/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vs.debug.error.remote_debug
- vs.debug.error.firewall.remotemachine
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 6efbb27052dc837ab10a74d8f43e949dfb816190
ms.sourcegitcommit: d6327b978661c0a745bf4b59f32d8171607803a3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/01/2018
---
# <a name="unable-to-connect-to-the-microsoft-visual-studio-remote-debugging-monitor"></a>Nepodařilo se připojit ke sledování Microsoft Visual Studio Remote Debugging Monitor.
Tato zpráva může dojít, protože sledování vzdáleného ladění není správně nastavena na vzdáleném počítači nebo vzdálený počítač je nedostupný v důsledku potížím se sítí nebo přítomnost bránou firewall.
  
> [!IMPORTANT]
>  Pokud se domníváte, tato zpráva zobrazila z důvodu chyby produktu, prosím [sestavy tento problém](../ide/how-to-report-a-problem-with-visual-studio-2017.md) k sadě Visual Studio. Pokud potřebujete další pomoc, přečtěte si [kontaktujte nás](../ide/talk-to-us.md) pro způsoby, jak kontaktovat společnost Microsoft.

## <a name="specificerrors"></a>Co je Podrobná chybová zpráva?

`Unable to Connect to the Microsoft Visual Studio Remote Debugging Monitor` Je obecná zpráva. Obvykle zprávu konkrétnější je zahrnutý v řetězec chyby a které mohou pomoci při identifikaci příčinu problému nebo vyhledejte další přesný opravu. Zde najdete několik běžných chybových zpráv, které se připojí k hlavní chybová zpráva:

- [Ladicí program nemůže připojit ke vzdálenému počítači. Ladicí program nemohl vyřešit zadaný název počítače](#cannot_connect)
- [Odmítl žádost o připojení vzdáleného ladicího programu](#rejected)
- [Neplatný přístup k umístění v paměti](#invalid_access)
- [Server není zadaný název na vzdáleném počítači spuštěny](#no_server)
- [Název požadovaného platné, ale nebyla nalezena žádná data požadovaného typu](#valid_name)
- [Visual Studio vzdáleného ladicího programu v cílovém počítači se nemůže připojit zpět k tomuto počítači](#cant_connect_back)
- [Odepření přístupu](#access_denied)
- [Došlo k chybě specifické balíčku zabezpečení](#security_package)

## <a name="cannot_connect"></a>Ladicí program nemůže připojit ke vzdálenému počítači. Ladicí program nemohl vyřešit zadaný název počítače

Opakujte tyto kroky:

1. Ujistěte se, zadejte platný název počítače a číslo portu **připojit k procesu** dialogové okno nebo ve vlastnostech projektu (vlastnosti, naleznete v tématu [tyto kroky](#server_incorrect)). Název počítače musí být v následujícím formátu:

    `computername:port`

    > [!NOTE]
    > Číslo portu musí odpovídat [vzdáleného ladicího programu číslo portu](../debugger/remote-debugger-port-assignments.md), které *musí být spuštěna* v cílovém počítači.

2. Pokud název počítače nefunguje, zkuste IP adresu a číslo portu místo.

3. Ujistěte se, že verze vzdáleného ladicího programu na cílovém počítači spuštěna odpovídá vaší verzi sady Visual Studio. Chcete-li získat správnou verzi vzdáleného ladicího programu, najdete v části [vzdálené ladění](../debugger/remote-debugging.md).

    > [!TIP]
    > Pokud se připojujete k procesu a úspěšně připojit, ale nezobrazí proces, který má, vyberte **Zobrazit procesy všechny uživatele zaškrtněte políčko**. Tato rutina ukáže procesy Pokud jsou připojené v rámci jiného uživatelského účtu.

4. Pokud tyto kroky nebylo možné vyřešit tuto chybu, přečtěte si téma [vzdálený počítač není dosažitelný](#dns).

## <a name="rejected"></a>Odmítl žádost o připojení vzdáleného ladicího programu

V **připojit k procesu** dialogové okno pole nebo ve vlastnostech projektu, ujistěte se, že název vzdáleného počítače a číslo portu odpovídá název a číslo portu zobrazený v okně vzdáleného ladicího programu. Pokud nesprávná, opravte a zkuste to znovu.

Pokud tyto hodnoty jsou správné a zpráva uvádí **ověřování systému Windows** režim, zkontrolujte, zda vzdáleného ladicího programu je v režimu správné ověření (**nástroje > Možnosti**).

## <a name="invalid_access"></a>Neplatný přístup k umístění v paměti

Došlo k vnitřní chybě. Restartujte Visual Studio a zkuste to znovu.

## <a name="no_server"></a>Server není zadaný název na vzdáleném počítači spuštěny

Visual Studio se nemohl připojit k vzdáleného ladicího programu. Tato zpráva může mít několik příčin:

- Vzdálený ladicí program může být spuštěn pod účtem jiného uživatele. V tématu [tyto kroky](#user_accounts)

- Port je blokován v bráně firewall. Zkontrolujte, jestli je brána firewall [není blokování vaši žádost o](#firewall), zvlášť pokud používáte bránu firewall jiného výrobce.

- Verze vzdáleného ladicího programu sady Visual Studio neodpovídá. Chcete-li získat správnou verzi vzdáleného ladicího programu, najdete v části [vzdálené ladění](../debugger/remote-debugging.md)


## <a name="#valid_name"></a>Název požadovaného platné, ale nebyla nalezena žádná data požadovaného typu

Vzdálený počítač existuje, ale Visual Studio se nemohl připojit k vzdáleného ladicího programu. Tato zpráva může mít několik příčin:

- Problém s DNS brání připojení. V tématu [tyto kroky](#dns).

- Vzdálený ladicí program může být spuštěn pod účtem jiného uživatele. Postupujte podle [tyto kroky](#user_accounts).

- Port je blokován v bráně firewall. Zkontrolujte, jestli je brána firewall [není blokování vaši žádost o](#firewall), zvlášť pokud používáte bránu firewall jiného výrobce.

- Verze vzdáleného ladicího programu sady Visual Studio neodpovídá. Chcete-li získat správnou verzi vzdáleného ladicího programu, najdete v části [vzdálené ladění](../debugger/remote-debugging.md).

## <a name="cant_connect_back"></a>Visual Studio vzdáleného ladicího programu v cílovém počítači se nemůže připojit zpět k tomuto počítači

Vzdálený ladicí program může být spuštěn pod účtem jiného uživatele. Otevřete v vzdáleného ladicího programu **nástroje > oprávnění** přidejte uživatele na oprávnění vzdáleného ladicího programu. Další informace najdete v tématu [vzdáleného ladicího programu běží pod jiným uživatelským účtem](#user_accounts).

Pokud chybová zpráva také uvádí brána firewall, může být v bráně firewall na místním počítači znemožňuje komunikaci ze vzdáleného počítače zpět do Visual Studio. V tématu [tyto kroky](#firewall).

## <a name="access_denied"></a>Odepření přístupu

Tato chyba může zobrazit, pokud se pokusíte ladění na vzdáleném počítači 64-bit z 32bitového počítače (není podporováno).

## <a name="security_package"></a>Došlo k chybě specifické balíčku zabezpečení

Může se jednat o starší verze problém specifické pro systém Windows XP a Windows 7. Toto [informace](https://stackoverflow.com/questions/4786016/unable-to-connect-to-the-microsoft-remote-debugging-monitor-a-security-package). 

## <a name="causes-and-recommendations"></a>Příčiny a doporučení

### <a name="dns"></a>Vzdálený počítač není dostupný 

Pokud se nemůžete připojit pomocí název vzdáleného počítače, zkuste použít IP adresu. Můžete použít `ipconfig` v příkazovém řádku na vzdáleném počítači potřebujete adresu IPv4. Pokud používáte souboru HOSTITELŮ, ověřte, zda je správně nakonfigurována.

Pokud to nepomůže, ověřte, že vzdálený počítač je přístupný v síti ([ping](https://technet.microsoft.com/en-us/library/cc732509(v=ws.10).aspx) vzdáleného počítače). Vzdálené ladění přes Internet není podporován, s výjimkou v některých scénářích Microsoft Azure.
  
### <a name="server_incorrect"></a>Je nesprávný název serveru nebo software jiného výrobce narušuje vzdáleného ladicího programu

V sadě Visual Studio podívejte se na vlastnosti projektu a ujistěte se, že je název serveru správný. Najdete v tématech [C# a Visual Basic](../debugger/remote-debugging-csharp.md#remote_csharp) a [C++](../debugger/remote-debugging-cpp.md#remote_cplusplus). Pro technologii ASP.NET, otevřete **vlastnosti / Web / servery** nebo **vlastnosti / Debug** v závislosti na typu vašeho projektu.

> [!NOTE]
> Pokud se připojujete k procesu, nepoužívají se nastavení vzdálené ve vlastnostech projektu.

Pokud je název serveru správný, váš antivirový software nebo brána firewall blokuje vzdáleného ladicího programu. Při ladění místně, tomu může dojít, protože Visual Studio je 32bitová aplikace, takže používá 64bitové verze vzdáleného ladicího programu k ladění 64bitových aplikací. 32bitové a 64bitové procesy komunikují pomocí místní sítě v místním počítači. Žádné síťové přenosy nechá počítač, ale je možné, že software jiných výrobců zabezpečení může blokovat komunikaci.

### <a name="user_accounts"></a>Vzdáleného ladicího programu běží pod jiného uživatelského účtu 

Vzdáleného ladicího programu, ve výchozím nastavení, přijímají pouze připojení od uživatele, který spuštění vzdáleného ladicího programu a členy skupiny Administrators. Další uživatelé musí mít explicitně udělený oprávnění. 
 
Můžete to vyřešit v jednom z následujících způsobů:  

-   Přidejte Visual Studio uživatele na oprávnění vzdáleného ladicího programu (v okně vzdáleného ladicího programu vyberte **nástroje > oprávnění**).

-   Na vzdáleném počítači restartujte vzdáleného ladicího programu v rámci stejného uživatelského účtu a heslo, které používáte v sadě Visual Studio počítači.

    > [!NOTE]
    > Pokud používáte vzdálený ladicí program na vzdáleném serveru, klikněte pravým tlačítkem na aplikaci vzdáleného ladicího programu a zvolte **spustit jako správce** (nebo, můžete spustit vzdáleného ladicího programu jako služba). Pokud jste neběží na vzdáleném serveru, právě spusťte normálně.
  
-   Vzdáleného ladicího programu můžete spustit z příkazového řádku **/ povolit \<uživatelské jméno >** parametr: `msvsmon /allow <username@computer>`. 
  
-   Alternativně můžete povolit všem uživatelům provést vzdálené ladění. V okně vzdáleného ladicího programu přejděte do **nástroje > Možnosti** dialogové okno. Když vyberete **bez ověřování**, potom můžete zkontrolovat **umožnit všem uživatelům ladění**. Tato možnost však doporučujeme pouze v případě ostatních možností nezdaří, nebo pokud jste v privátní síti.

### <a name="firewall"></a>V bráně firewall na vzdáleném počítači neumožňuje pro příchozí připojení vzdáleného ladicího programu  
 V bráně firewall na tento počítač Visual Studio a brány firewall na vzdáleném počítači musí nakonfigurovat pro povolení komunikace mezi sadou Visual Studio a vzdáleného ladicího programu. Informace o portech používá vzdáleného ladicího programu najdete v tématu [přiřazení portu vzdáleného ladicího programu](../debugger/remote-debugger-port-assignments.md). Informace o konfiguraci brány Windows firewall najdete v tématu [konfigurace brány Windows Firewall pro vzdálené ladění](../debugger/configure-the-windows-firewall-for-remote-debugging.md).
  
### <a name="the-version-of-the-remote-debugger-doesnt-match-the-version-of-visual-studio"></a>Verze vzdáleného ladicího programu neodpovídá verzi sady Visual Studio  
 Verze sady Visual Studio, které běží místně musí odpovídat verzi sledování vzdáleného ladění, která běží na vzdáleném počítači. Chcete-li odstranit tento problém, stáhněte a nainstalujte odpovídající verzi sledování vzdáleného ladění. Chcete-li získat správnou verzi vzdáleného ladicího programu, najdete v části [vzdálené ladění](../debugger/remote-debugging.md).
  
### <a name="the-local-and-remote-machines-have-different-authentication-modes"></a>Místní a vzdálené počítače mají různá ověřovací režimy  
 Místní a vzdálené počítače nutné používat stejný režim ověřování. Chcete-li odstranit tento problém, ujistěte se, oba počítače používáte stejný režim ověřování. Můžete změnit režim ověřování. V okně vzdáleného ladicího programu přejděte do **nástroje > Možnosti** dialogové okno.
  
 Další informace o režimech ověřování najdete v tématu [Přehled ověřování systému Windows](https://technet.microsoft.com/en-us/library/hh831472.aspx).   
  
### <a name="anti-virus-software-is-blocking-the-connections"></a>Antivirový software blokuje připojení  
 Antivirový software Windows umožňuje připojení vzdáleného ladicího programu, ale některé třetích stran antivirový software může zablokovat. Podívejte se do dokumentace pro váš antivirový software a zjistěte, jak umožnit tato připojení.  
  
### <a name="network-security-policy-is-blocking-communication-between-the-remote-machine-and-visual-studio"></a>Zásady zabezpečení sítě blokuje komunikaci mezi vzdáleného počítače a Visual Studio  
 Zkontrolujte zabezpečení sítě a ujistěte se, že neblokuje komunikace. Další informace o zásadách zabezpečení sítě systému Windows najdete v tématu [nastavení zásad zabezpečení](/windows/device-security/security-policy-settings/security-policy-settings).  
  
### <a name="the-network-is-too-busy-to-support-remote-debugging"></a>Síť je příliš zaneprázdněn pro podporu vzdálené ladění  
 Budete muset provést vzdálené ladění v jinou dobu, nebo změnit plán práce v síti pro jinou dobu.  
  
## <a name="more-help"></a>Další nápovědu  
 Jak získat nápovědu více vzdáleného ladicího programu, otevřete stránku nápovědy vzdáleného ladicího programu (**pomoci > využití** v vzdáleného ladicího programu).
  
## <a name="see-also"></a>Viz také  
 [Vzdálené ladění](../debugger/remote-debugging.md)