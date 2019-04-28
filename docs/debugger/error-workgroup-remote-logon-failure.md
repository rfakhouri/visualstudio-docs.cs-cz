---
title: 'Chyba: Selhání přihlášení pracovní skupiny vzdálené | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.workgroup_remote_logon_failure
dev_langs:
- CSharp
- VB
- FSharp
- JScript
- C++
helpviewer_keywords:
- logon failure, remote debugging
- remote debugging, logon failure
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7d9142e92367dd10653bb8fdaaf86c34f3f17b84
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63399236"
---
# <a name="error-workgroup-remote-logon-failure"></a>Chyba: Selhání přihlášení vzdálené pracovní skupiny
Přečte tuto chybu:

 Chyba přihlášení: Neznámé uživatelské jméno nebo špatné heslo

 **Příčina**

 Této chybě může dojít při ladění z počítače v pracovní skupině a zkuste se připojit ke vzdálenému počítači. Mezi možné příčiny patří:

- Neexistuje žádný účet s odpovídajícím názvem a hesel na vzdáleném počítači.

- Pokud počítač Visual Studio a vzdálený počítač jsou v pracovních skupinách, této chybě může dojít z důvodu výchozí **místní zásady zabezpečení** nastavení na vzdáleném počítači. Ve výchozím nastavení **místní zásady zabezpečení** nastavení je **Guest - místní uživatelé ověřit jako hosta**. Chcete-li ladit na tento instalační program, je nutné změnit nastavení ve vzdáleném počítači, na **Classic - místní uživatelé ověřováni pomocí svých účtů**.

> [!NOTE]
> Musíte být správcem provádět následující úlohy.

### <a name="to-open-the-local-security-policy-window"></a>Chcete-li otevřít okno místní zásady zabezpečení

1. Spustit **secpol.msc** modul snap-in konzoly Microsoft Management Console. Zadejte secpol.msc ve službě Windows search pole spustit Windows nebo na příkazovém řádku.

### <a name="to-add-user-rights-assignments"></a>Chcete-li přidat přiřazení uživatelských práv

1. Otevřít **místní zásady zabezpečení** okna.

2. Rozbalte **místní zásady** složky.

3. Klikněte na tlačítko **přiřazení uživatelských práv**.

4. V **zásady** sloupce, klikněte dvakrát na **ladit programy** zobrazíte aktuální přiřazení zásad místní skupiny v **nastavení místních zásad zabezpečení** dialogové okno.

     ![Local Security Policy User Rights](../debugger/media/dbg_err_localsecuritypolicy_userrightsdebugprograms.png "DBG_ERR_LocalSecurityPolicy_UserRightsDebugPrograms")

5. Pokud chcete přidat nové uživatele, klikněte na tlačítko **přidat uživatele nebo skupinu** tlačítko.

### <a name="to-change-the-sharing-and-security-model"></a>Chcete-li změnit sdílení a modelu zabezpečení

1. Otevřít **místní zásady zabezpečení** okna.

2. Rozbalte **místní zásady** složky.

3. Klikněte na tlačítko **možnosti zabezpečení**.

4. V **zásady** sloupce, klikněte dvakrát na **přístup k síti: Model sdílení a zabezpečení pro místní účty**.

5. V **přístup k síti: Model sdílení a zabezpečení pro místní účty** dialogové okno pole, změňte hodnotu na **Classic - místní uživatelé ověřováni pomocí svých účtů** a klikněte na tlačítko **použít** tlačítko.

     ![Local Security Policy Security Options](../debugger/media/dbg_err_localsecuritypolicy_securityoptions_networkaccess.png "DBG_ERR_LocalSecurityPolicy_SecurityOptions_NetworkAccess")

## <a name="see-also"></a>Viz také
- [Chyby při vzdáleném ladění a jejich řešení](../debugger/remote-debugging-errors-and-troubleshooting.md)
- [Vzdálené ladění](../debugger/remote-debugging.md)