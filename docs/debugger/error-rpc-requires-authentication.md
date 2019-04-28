---
title: 'Chyba: RPC vyžaduje ověření. | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.rpc_requires_authentication
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c473916a6b689984f234736eb8b763056fc002d9
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62850455"
---
# <a name="error-rpc-requires-authentication"></a>Chyba: RPC vyžaduje ověření.
Visual Studio debugger se nemůže připojit ke vzdálenému počítači. Zásady protokolu RPC je povoleno v místním počítači, což znemožňuje vzdálené ladění.

### <a name="to-correct-this-error"></a>Oprava této chyby

1. Spustit `\` *windir*`\system32\regedt32.exe`

2. Vyhledejte a odstraňte `HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows NT\RPC\RestrictRemoteClients`.

3. Změna v registru se projeví až po restartování počítače.

4. Pokud se problém nevyřeší, obraťte se na správce domény o **konfigurace počítače > šablony pro správu > Systém > vzdálené volání procedur > omezení pro klienty neověřené RPC** zásady skupiny nastavení.