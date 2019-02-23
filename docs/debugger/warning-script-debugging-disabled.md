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
ms.openlocfilehash: 2543ad00b2065f7659a89e165c2d4df990403667
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56687039"
---
# <a name="warning-script-debugging-disabled"></a>Upozornění: Ladění skriptů zakázáno
V aplikaci Internet Explorer je aktuálně zakázáno ladění skriptu

 K tomuto upozornění dochází při pokusu o ladění skriptu bez povolení ladění skriptu v aplikaci Internet Explorer. Z bezpečnostních důvodů aplikace Internet Explorer zakáže ladění skriptů ve výchozím nastavení.

### <a name="to-enable-script-debugging-in-internet-explorer"></a>K povolení ladění skriptu v aplikaci Internet Explorer

1.  V Internet Exploreru **nástroje** nabídce zvolte **Možnosti Internetu**.

2.  V **Možnosti Internetu** dialogové okno, klikněte na tlačítko **Upřesnit** kartu.

3.  Na **Upřesnit** kartu, podívejte se **nastavení** pole **procházení** kategorie.

4.  Vymazat **zakázat ladění skriptů (aplikace Internet Explorer)**.

5.  Klikněte na **OK**.

6.  Ukončete a restartujte aplikaci Internet Explorer.

     Nová nastavení, nyní nebudou platit.

## <a name="see-also"></a>Viz také
- [Postupy: Připojení ke skriptu](../debugger/how-to-attach-to-script.md)