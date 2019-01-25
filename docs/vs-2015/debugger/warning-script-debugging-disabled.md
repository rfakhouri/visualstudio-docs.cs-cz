---
title: 'Upozornění: Ladění skriptů zakázáno | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.scriptdisabled
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: 323d2b1d-52a4-42f7-b4ad-96b4b0c23b8d
caps.latest.revision: 10
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: b44c260e00ae5ef8b0d23e7aede139563ff22d98
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54779792"
---
# <a name="warning-script-debugging-disabled"></a>Upozornění: Ladění skriptů zakázáno
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

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
 [Postupy: Připojení ke skriptu](../debugger/how-to-attach-to-script.md)
