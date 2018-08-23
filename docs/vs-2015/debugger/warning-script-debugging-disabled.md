---
title: 'Upozornění: Ladění skriptů zakázáno | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.scriptdisabled
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: 323d2b1d-52a4-42f7-b4ad-96b4b0c23b8d
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 91b54b3e9a70284dc1efb03be7adfaa5d1421920
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42666079"
---
# <a name="warning-script-debugging-disabled"></a>Upozornění: Ladění skriptů zakázáno
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [upozornění: ladění skriptů zakázáno](https://docs.microsoft.com/visualstudio/debugger/warning-script-debugging-disabled).  
  
V aplikaci Internet Explorer je aktuálně zakázáno ladění skriptu  
  
 K tomuto upozornění dochází při pokusu o ladění skriptu bez povolení ladění skriptu v aplikaci Internet Explorer. Z bezpečnostních důvodů aplikace Internet Explorer zakáže ladění skriptů ve výchozím nastavení.  
  
### <a name="to-enable-script-debugging-in-internet-explorer"></a>K povolení ladění skriptu v aplikaci Internet Explorer  
  
1.  V Internet Exploreru **nástroje** nabídce zvolte **Možnosti Internetu**.  
  
2.  V **Možnosti Internetu** dialogové okno, klikněte na tlačítko **Upřesnit** kartu.  
  
3.  Na **Upřesnit** kartu, podívejte se **nastavení** pole **procházení** kategorie.  
  
4.  Vymazat **zakázat ladění skriptů (aplikace Internet Explorer)**.  
  
5.  Klikněte na tlačítko **OK**.  
  
6.  Ukončete a restartujte aplikaci Internet Explorer.  
  
     Nová nastavení, nyní nebudou platit.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: připojení ke skriptu](../debugger/how-to-attach-to-script.md)



