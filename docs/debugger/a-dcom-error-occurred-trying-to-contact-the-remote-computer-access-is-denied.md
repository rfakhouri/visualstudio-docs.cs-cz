---
title: Při pokusu o spojení se vzdáleným počítačem došlo k chybě modelu DCOM. Přístup byl zamítnut. | Dokumenty Microsoft
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.debug.remote.dcom_access_denied
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- remote debugging, DCOM error
- remote DCOM access denied error
- DCOM, access errors
ms.assetid: 9d7dfc1b-9fe0-4f54-9c50-9c0e0f8358c5
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 75d1c9f9c23df04ca19f68dada718fba12dc51f3
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56622836"
---
# <a name="a-dcom-error-occurred-trying-to-contact-the-remote-computer-access-is-denied"></a>Při pokusu o spojení se vzdáleným počítačem došlo k chybě modelu DCOM. Přístup byl zamítnut.
Vzdálené ladění používá model DCOM ke komunikaci mezi místními a vzdálenými počítači v následujících situacích:

- Ladicí program je nastavena na **nativní režim kompatibility** nebo **spravovaný režim kompatibility** se změnami **nástroje > Možnosti > ladění** stránky

- Ladění spravovaného C++ (C + +/ CLI) kód.

- V sadě Visual Studio 2013 když **povolení nativní funkce upravit a pokračovat** se změnami **nástroje > Možnosti > ladění** stránky

- Některé třetích stran ladění scénářů

  Tato chyba nastane, pokud proces sady Visual Studio se nemůže ověřit samotného (nebo zadané přihlašovací údaje byly za nedostatečné) k procesu vzdálený ladicí program přes model DCOM. Tento problém může vyřešit nejméně jednu z následujících náhradních postupů:

- Vypnout **nativní režim kompatibility** a **spravovaný režim kompatibility**.

- V sadě Visual Studio 2013 vypnout **povolení nativní funkce upravit a pokračovat**.

- Oba počítače restartujte.

- Pokud vzdálené ladění vyžaduje zadání přihlašovacích údajů, zaškrtněte možnost pro uložení přihlašovacích údajů.

## <a name="see-also"></a>Viz také

- [Chyby při vzdáleném ladění a jejich řešení](../debugger/remote-debugging-errors-and-troubleshooting.md)
- [Vzdálené ladění](../debugger/remote-debugging.md)