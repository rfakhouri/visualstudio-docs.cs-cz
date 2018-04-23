---
title: 'Chyba: Zdá se, že Microsoft Visual Studio Remote Debugging Monitor (MSVSMON.EXE) na vzdáleném počítači neběží. | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.server_machine_no_default
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 683af8cf0c75068a58b5e8cf4732cdf69c586d4f
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
---
# <a name="error-the-microsoft-visual-studio-remote-debugging-monitor-msvsmonexe-does-not-appear-to-be-running-on-the-remote-computer"></a>Chyba: Zdá se, že Microsoft Visual Studio Remote Debugging Monitor (MSVSMON.EXE) na vzdáleném počítači neběží.
Tato chybová zpráva znamená, že Visual Studio nelze najít správný instanci Visual Studio Remote Debugging Monitor na vzdáleném počítači. Pro vzdálené ladění fungovat, musí být nainstalován Visual Studio Remote Debugging Monitor. Informace o stažení a nastavení vzdáleného ladicího programu najdete v tématu [vzdálené ladění](../debugger/remote-debugging.md).  
  
> [!IMPORTANT]
>  Pokud se domníváte, tato zpráva zobrazila z důvodu chyby produktu, prosím [tento problém nahlásit Visual Studio](../ide/how-to-report-a-problem-with-visual-studio-2017.md). Pokud potřebujete další pomoc, přečtěte si [kontaktujte nás](../ide/talk-to-us.md) pro způsoby, jak kontaktovat společnost Microsoft.  
  
## <a name="i-got-this-message-while-i-was-debugging-in-visual-studio-2010-or-earlier"></a>Tato zpráva zobrazí chybové při I byl ladění v sadě Visual Studio 2010 nebo dřívější  
 Pokud je Visual Studio 2010 nebo starší verze sady Visual Studio, který používáte, může také tato chyba se zobrazí pokud není povoleno sdílení souborů a tiskáren. Další informace o tomto problému, naleznete na verzi sady Visual Studio 2010 této dokumentace: [chybě: Microsoft Visual Studio Remote Debugging Monitor (MSVSMON. Soubor EXE) nezobrazí, aby byl spuštěn ve vzdáleném počítači. – Visual Studio 2010](https://msdn.microsoft.com/en-us/library/ms164726\(v=vs.100\).aspx)  
  
## <a name="i-got-this-message-while-i-was-debugging-locally"></a>Tato zpráva zobrazí chybové při I byl místně ladění  
 Pokud jste tuto zprávu při ladění místně, mohou být na straně zmocnitele váš antivirový software nebo brány firewall třetích stran. Visual Studio se 32bitová aplikace, takže používá 64bitové verze vzdáleného ladicího programu k ladění 64bitových aplikací. Dva procesy komunikují pomocí místní sítě v místním počítači. Žádný provoz nechá počítač, ale je možné, že software jiných výrobců zabezpečení může blokovat komunikaci.  
  
 Následující části uvádějí některé z jiných důvodů, proč jste může být, že podmínky tuto zprávu, a jak vyřešit problém.  
  
## <a name="the-remote-machine-is-not-reachable"></a>Vzdálený počítač není dostupný  
 Zkuste [ping](https://technet.microsoft.com/en-us/library/ee624059\(v=ws.10\).aspx) vzdáleného počítače. Pokud je odpověď na příkaz ping, nástrojů pro vzdálenou nebudou moct připojit buď. Zkuste restartování vzdáleného počítače a jinak a ujistěte se, zda je správně nakonfigurován v síti.  
  
## <a name="the-version-of-the-remote-debugger-doesnt-match-the-version-of-visual-studio"></a>Verze vzdáleného ladicího programu neodpovídá verzi sady Visual Studio  
 Verze sady Visual Studio, které běží místně musí odpovídat verzi sledování vzdáleného ladění, která běží na vzdáleném počítači. Chcete-li odstranit tento problém, stáhněte a nainstalujte odpovídající verzi sledování vzdáleného ladění. Přejděte na [Download Center](http://www.microsoft.com/en-us/download) najít správnou verzi vzdáleného ladicího programu.  
  
## <a name="the-local-and-remote-machines-have-different-authentication-modes"></a>Místní a vzdálené počítače mají různá ověřovací režimy  
 Místní a vzdálené počítače nutné používat stejný režim ověřování. Chcete-li odstranit tento problém, ujistěte se, oba počítače používáte stejný režim ověřování. Další informace o režimech ověřování najdete v tématu [Přehled ověřování systému Windows](https://technet.microsoft.com/en-us/library/hh831472.aspx).  
  
## <a name="the-remote-debugger-is-running-under-a-different-user-account"></a>Vzdáleného ladicího programu běží pod jiného uživatelského účtu  
 Můžete to vyřešit v jednom z následujících způsobů:  
  
-   Můžete zastavit vzdáleného ladicího programu a restartujte ji pomocí účtu, který používáte v místním počítači.  
  
-   Vzdáleného ladicího programu můžete spustit z příkazového řádku **/ povolit \<uživatelské jméno >** parametr: `msvsmon /allow <username@computer>`  
  
-   Můžete přidat uživatele na oprávnění vzdáleného ladicího programu (v okně vzdáleného ladicího programu **nástroje > oprávnění**).  
  
-   Pokud nemůžete použít metody v předchozích krocích, můžete povolit všem uživatelům provést vzdálené ladění. V okně vzdáleného ladicího programu přejděte do **nástroje > Možnosti** dialogové okno. Když vyberete **bez ověřování**, potom můžete zkontrolovat **umožnit všem uživatelům ladění**. Ale tuto možnost používejte jenom v případě, že máte žádný výběr, nebo pokud jste v privátní síti.  
  
## <a name="the-firewall-on-the-remote-machine-doesnt-allow-incoming-connections-to-the-remote-debugger"></a>V bráně firewall na vzdáleném počítači neumožňuje pro příchozí připojení vzdáleného ladicího programu  
 V bráně firewall na tento počítač Visual Studio a brány firewall na vzdáleném počítači musí nakonfigurovat pro povolení komunikace mezi sadou Visual Studio a vzdáleného ladicího programu. Informace o portech používá vzdáleného ladicího programu najdete v tématu [přiřazení portu vzdáleného ladicího programu](../debugger/remote-debugger-port-assignments.md). Informace o konfiguraci brány Windows firewall najdete v tématu [konfigurace brány Windows Firewall pro vzdálené ladění](../debugger/configure-the-windows-firewall-for-remote-debugging.md).  
  
## <a name="anti-virus-software-is-blocking-the-connections"></a>Antivirový software blokuje připojení  
 Antivirový software Windows umožňuje připojení vzdáleného ladicího programu, ale některé třetích stran antivirový software může zablokovat. Podívejte se do dokumentace pro váš antivirový software a zjistěte, jak umožnit tato připojení.  
  
## <a name="network-security-policy-is-blocking-communication-between-the-remote-machine-and-visual-studio"></a>Zásady zabezpečení sítě blokuje komunikaci mezi vzdáleného počítače a Visual Studio  
 Zkontrolujte zabezpečení sítě a ujistěte se, že neblokuje komunikace. Další informace o zásadách zabezpečení sítě systému Windows najdete v tématu [nastavení zásad zabezpečení](/windows/device-security/security-policy-settings/security-policy-settings).  
  
## <a name="the-network-is-too-busy-to-support-remote-debugging"></a>Síť je příliš zaneprázdněn pro podporu vzdálené ladění  
 Budete muset provést vzdálené ladění v jinou dobu, nebo změnit plán práce v síti pro jinou dobu.  
  
## <a name="more-help"></a>Další nápovědu  
 Chcete-li získat nápovědu více vzdáleného ladicího programu, včetně přepínače příkazového řádku, klikněte na tlačítko **pomoci > využití** v okně vzdáleného ladicího programu. Pokud nemáte ho otevřete uvidíte webové stránky tak, že zkopírujete následující řádek do **Průzkumníka souborů** okno. (Je třeba nahradit \<Visual Studio Instalační adresář > s umístění instalace Visual Studia.)  
  
 res: / /*\<Visual Studio Instalační adresář >*\Common7\IDE\Remote%20Debugger\x64\msvsmon.exe/help.htm  
  
## <a name="see-also"></a>Viz také  
 [Vzdálené ladění chyby a řešení potíží](../debugger/remote-debugging-errors-and-troubleshooting.md)