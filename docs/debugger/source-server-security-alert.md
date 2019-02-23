---
title: Výstraha zabezpečení serveru zdroje | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.debug.sourceserver.enablewarning
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: 8451c281-6914-469c-b80c-6271cc3f3d17
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: af216023b1a157136f86f0ca8527a8b433b0a34b
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56719142"
---
# <a name="source-server-security-alert"></a>Výstraha zabezpečení zdrojového serveru
Při použití zdrojového serveru, používejte pouze soubory symbolů, které jsou ze známých a důvěryhodných umístění.

 Toto upozornění se zobrazí, když povolíte podporu zdrojového serveru. Příkazy ze zdrojového serveru jsou vloženy do souborů symbolů ladění (**\*PDB** soubory). Ujistěte se, že budete vědět, odkud pochází vaše soubory PDB.

> [!IMPORTANT]
>  Následující potenciální ohrožení zabezpečení se musí vzít v úvahu při použití zdrojového serveru: Libovolné příkazy lze vložit do souboru PDB aplikace, proto se ujistěte, že vložíte pouze ty, které chcete spustit v souboru srcsrv.ini. Pokus o provedení příkazu mimo soubor srcsvr.ini způsobí zobrazení dialogového okna s potvrzením. Další informace najdete v tématu [upozornění zabezpečení: Ladicí program musí spustit nedůvěryhodný příkaz](../debugger/security-warning-debugger-must-execute-untrusted-command.md). Parametry příkazu nejsou ověřovány, proto buďte s důvěryhodnými příkazy opatrní. Například pokud důvěřujete souboru cmd.exe, uživateli se zlými úmysly může zadat parametry, které by z příkazu mohly udělat hrozbu.

## <a name="see-also"></a>Viz také
- [Zadání symbolu (.pdb) a zdrojových souborů](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)
- [Zabezpečení ladicího programu](../debugger/debugger-security.md)
- [Zdrojový Server](/windows/desktop/Debug/source-server-and-source-indexing)
