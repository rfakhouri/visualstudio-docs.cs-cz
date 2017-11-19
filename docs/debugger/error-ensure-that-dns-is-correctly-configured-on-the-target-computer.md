---
title: "Chyba: Ověřte, zda je server DNS správně nakonfigurovaný v cílovém počítači | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.error.callback_dns_failed
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: 2d364caf-73af-4186-bf9b-af186331cbe8
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6711ae54c87e5e71a643fee3c019c8214294c09a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="error-ensure-that-dns-is-correctly-configured-on-the-target-computer"></a>Chyba: Ověřte, zda je na cílovém počítači správně nakonfigurován server DNS.
Při pokusu provést vzdálené ladění, zobrazí se následující chybová zpráva:  
  
```  
Error: The Visual Studio Remote Debugger on the target computer cannot connect back to this computer. Ensure that DNS is correctly configured on the target computer.  
```  
  
 K této chybě dojde, když se cílový počítač nelze přeložit název hostitelského počítače ladicího programu sady Visual Studio. Zkontrolujte nastavení služby DNS v cílovém počítači.  
  
-   Informace o zobrazení vaše nastavení DNS ve Windows 8.1, Vista, Windows 7, Windows Server 2012, Windows Server 2008 nebo Windows Server 2008 R2, tomu: na **spustit** nabídce zvolte **Nápověda a podpora** a poté vyhledejte **Změna nastavení protokolu TCP/IP**.  
  
-   Další informace, přejděte na [webu Microsoft Windows](http://go.microsoft.com/fwlink/?LinkId=252720) a vyhledejte **Změna nastavení protokolu TCP/IP**.  
  
 Pokud DNS problém nevyřešíte, pokuste se spustit vzdáleného ladicího programu pod jiným účtem. K této chybě dojde pouze v případě, že je spuštěné vzdáleného ladicího programu pod místní systém nebo účet Network Service. Pokud spustíte vzdáleného ladicího programu pod jiným účtem, může použít ověřování NTLM, která nevyžaduje DNS. . Postup najdete v tématu [chybě: Visual Studio vzdáleného ladicího programu service v cílovém počítači se nemůže připojit zpět k tomuto počítači](../debugger/error-the-visual-studio-remote-debugger-service-on-the-target-computer-cannot-connect-back-to-this-computer.md).