---
title: Zabezpečení ladicího programu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], security
- debugger, security
- security [Visual Studio], debugging best practices
ms.assetid: d4fc3c43-e844-419c-8dbb-551cc2a9b09e
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3f0b97564c48255ea8b8f37e370402fa8f7499aa
ms.sourcegitcommit: 046a9adc5fa6d6d05157204f5fd1a291d89760b7
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/11/2018
ms.locfileid: "34065003"
---
# <a name="debugger-security"></a>Zabezpečení ladicího programu
Možnost ladění jiným procesem vám umožňuje velmi široký, které by jinak máte, zejména v případě, že ladění vzdáleně. Škodlivý ladicí program může způsobit poškození rozšířeným na počítači laděné.  
  
 Ale celá řada vývojářů není potřeba si uvědomit, že ohrožení zabezpečení můžete také toku v opačném směru. Je možné, škodlivý kód v procesu pozastaven ohrozit zabezpečení počítače ladění: počet zneužití zabezpečení, které musí být chráněn proti.  
  
## <a name="security-best-practices"></a>Doporučené postupy zabezpečení  
 Je vztah implicitní vztah důvěryhodnosti mezi kódem, který ladíte a ladicí program. Pokud jste ochotni něco ladit, měli byste také mít ochotná ji spustit. Dolní řádek je, že musí být schopné vztahu důvěryhodnosti, co jsou ladění. Pokud mu nelze důvěřovat, pak by neměl ladění nebo by měla ladění, z počítače, který jste si může dovolit ohrozit a v izolovaném prostředí.  
  
 Chcete-li snížit potenciální prostor pro útok, je třeba zakázat ladění na produkční počítače. Ze stejného důvodu by nikdy být povoleno ladění bez omezení.  
  
### <a name="managed-debugging-security"></a>Spravované ladění zabezpečení  
 Tady jsou některé obecné doporučení, které platí pro všechny spravované ladění.  
  
-   Buďte opatrní při připojování k procesu nedůvěryhodné uživatele: Pokud tak učiníte, budete předpokládat, že je důvěryhodný. Při pokusu o připojení k procesu nedůvěryhodné uživatele pole potvrzovací dialogové okno upozornění zabezpečení zobrazí dotazem, zda chcete připojit k procesu. "Důvěryhodné uživatelé" můžete zahrnout, a sadu standardní uživatelé běžně definované na počítačích, které mají rozhraní .NET Framework nainstalované, jako například **aspnet**, **localsystem**, **networkservice**, a **localservice**. Další informace najdete v tématu [upozornění zabezpečení: připojení k procesu vlastněných nedůvěryhodné uživatelem může být nebezpečný. Pokud tyto informace nezdá nebo si nejste jistí, nepřipojujte tohoto procesu](../debugger/security-warning-attaching-to-a-process-owned-by-an-untrusted-user.md).  
  
-   Buďte opatrní při stahování projektu vypnout Internetu a načítání do [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. To je velmi rizikové udělat i bez ladění. Když to uděláte, se za předpokladu, že projekt a kód, který obsahuje jsou důvěryhodné.  
  
 Další informace najdete v tématu [ladění spravovaného kódu](../debugger/debugging-managed-code.md).  
  
### <a name="remote-debugging-security"></a>Zabezpečení vzdálené ladění  
 Místní ladění je obecně bezpečnější než vzdálené ladění. Vzdálené ladění zvyšuje celkového povrchu, který může být zjištěný.  
  
 Visual Studio Remote Debugging Monitor (msvsmon.exe) se používá v vzdálené ladění a existuje několik doporučení zabezpečení pro její konfiguraci. Upřednostňovaný způsob konfigurace režim ověřování je ověřování systému Windows, protože režim bez ověřování je nezabezpečené.  
  
 ![Dialogové okno chyby](../debugger/media/dbg_err_remotepermissionschanged.png "DBG_ERR_RemotePermissionsChanged")  
  
 Při použití režimu ověřování systému Windows, mějte na paměti, udělení oprávnění nedůvěryhodné uživatele pro připojení k msvsmon je nebezpečné, protože uživateli je udělen všechna oprávnění v počítači...  
  
 O neznámý proces ve vzdáleném počítači není ladění: existují potenciální zneužití, který může mít vliv na počítač s ladicím programem nebo který může dojít k ohrožení msvsmon.exe, Visual Studio Remote Debugging Monitor. Pokud musíte ladit absolutně neznámé procesu, zkuste ladění místně a používejte bránu firewall, aby všechny potenciální hrozby lokalizované.  
  
 Další informace najdete v tématu [vzdálené ladění](../debugger/remote-debugging.md).  
  
### <a name="web-services-debugging-security"></a>Ladění zabezpečení webové služby  
 Je bezpečnější ladění místně, ale protože pravděpodobně nemáte [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nainstalovaná na webovém serveru, místní ladění nemusí být praktické. Obecně platí ladění webových služeb se provádí vzdáleně, s výjimkou během vývoje, takže doporučení pro vzdálené ladění zabezpečení platí také pro ladění webových služeb. Tady jsou některé další osvědčené postupy. Další informace najdete v tématu [ladění webové služby XML](http://msdn.microsoft.com/en-us/c900b137-9fbd-4f59-91b5-9c2c6ce06f00).  
  
-   Nepovolujte ladění na webovém serveru, který byl napaden.  
  
-   Ujistěte se, že víte, že webový server je zabezpečený před jeho ladění. Pokud si nejste jistí, že je bezpečné, není ladění ho.  
  
-   Dávejte pozor, zejména pokud ladíte webové služby, který je zveřejněný na Internetu.  
  
### <a name="external-components"></a>Externí součásti  
 Znát stav důvěryhodnosti externí součásti, které váš program komunikuje se službou, zejména v případě, že není psaní kódu. Také být vědomi součásti, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nebo může používat ladicí program.  
  
### <a name="symbols-and-source-code"></a>Symbolů a zdrojového kódu  
 Dva [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nástroje, které vyžadují přemýšlení o zabezpečení jsou následující:  
  
-   Zdrojový Server, který vám poskytne verzích zdrojového kódu z úložiště zdrojového kódu. Je vhodné, pokud není aktuální verze zdrojový kód aplikace. [Upozornění zabezpečení: Ladicí program musí spustit nedůvěryhodný příkaz](../debugger/security-warning-debugger-must-execute-untrusted-command.md).  
  
-   Symbol Server, který slouží k poskytování symboly potřebné k ladění selhání během volání systému.  
  
 V tématu [zadání symbolu (.pdb) a zdrojových souborů](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)  
  
## <a name="see-also"></a>Viz také  
 [Nastavení ladicího programu a příprava](../debugger/debugger-settings-and-preparation.md)   
 [Základy ladicího programu](../debugger/debugger-basics.md)   
 [Upozornění zabezpečení: Připojení k procesu, jehož vlastníkem je nedůvěryhodný uživatel, může být nebezpečné. Pokud tyto informace nezdá nebo si nejste jistí, nepřipojujte tohoto procesu](../debugger/security-warning-attaching-to-a-process-owned-by-an-untrusted-user.md)   
 [Upozornění zabezpečení: Ladicí program musí spustit nedůvěryhodný příkaz.](../debugger/security-warning-debugger-must-execute-untrusted-command.md)