---
title: 'Upozornění: Ladění skriptů zakázáno | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.debug.scriptdisabled
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: 323d2b1d-52a4-42f7-b4ad-96b4b0c23b8d
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 50fe457e2b66a4c1ddafc9fc24658f58f6f753d2
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60114642"
---
# <a name="warning-script-debugging-disabled"></a>Upozornění: Ladění skriptů zakázáno
V aplikaci Internet Explorer je aktuálně zakázáno ladění skriptu

 K tomuto upozornění dochází při pokusu o ladění skriptu bez povolení ladění skriptu v aplikaci Internet Explorer. Z bezpečnostních důvodů aplikace Internet Explorer zakáže ladění skriptů ve výchozím nastavení.

### <a name="to-enable-script-debugging-in-internet-explorer"></a>K povolení ladění skriptu v aplikaci Internet Explorer

1. V Internet Exploreru **nástroje** nabídce zvolte **Možnosti Internetu**.

2. V **Možnosti Internetu** dialogové okno, klikněte na tlačítko **Upřesnit** kartu.

3. Na **Upřesnit** kartu, podívejte se **nastavení** pole **procházení** kategorie.

4. Vymazat **zakázat ladění skriptů (aplikace Internet Explorer)**.

5. Klikněte na **OK**.

6. Ukončete a restartujte aplikaci Internet Explorer.

     Nová nastavení, nyní nebudou platit.

## <a name="see-also"></a>Viz také
- [Postupy: Připojení ke skriptu](../debugger/how-to-attach-to-script.md)