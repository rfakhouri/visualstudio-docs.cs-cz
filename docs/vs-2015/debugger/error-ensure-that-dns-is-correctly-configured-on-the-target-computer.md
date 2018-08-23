---
title: 'Chyba: Ujistěte se, že DNS správně nakonfigurovaný v cílovém počítači | Dokumentace Microsoftu'
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
- vs.debug.error.callback_dns_failed
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: 2d364caf-73af-4186-bf9b-af186331cbe8
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1f0be44e07a42b132f00b476aa7cf4148720933a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42668972"
---
# <a name="error-ensure-that-dns-is-correctly-configured-on-the-target-computer"></a>Chyba: Ověřte, zda je na cílovém počítači správně nakonfigurován server DNS.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [Chyba: Ujistěte se, že DNS správně nakonfigurovaný v cílovém počítači](https://docs.microsoft.com/visualstudio/debugger/error-ensure-that-dns-is-correctly-configured-on-the-target-computer).  
  
Při pokusu o provádět vzdálené ladění, může zobrazit následující chybová zpráva:  
  
```  
Error: The Visual Studio Remote Debugger on the target computer cannot connect back to this computer. Ensure that DNS is correctly configured on the target computer.  
```  
  
 K této chybě dochází, když se cílový počítač nemůže přeložit název hostitelského počítače ladicího programu sady Visual Studio. Zkontrolujte nastavení DNS v cílovém počítači.  
  
-   Informace o zobrazení nastavení DNS ve Windows 8.1, Vista, Windows 7, Windows Server 2012, Windows Server 2008 nebo Windows Server 2008 R2, to provést: na **Start** nabídce zvolte **Nápověda a podpora** a poté vyhledejte **Změna nastavení protokolu TCP/IP**.  
  
-   Další informace najdete v části [webu Microsoft Windows](http://go.microsoft.com/fwlink/?LinkId=252720) a vyhledejte **Změna nastavení protokolu TCP/IP**.  
  
 Pokud DNS problém nevyřešíte, pokuste se spustit vzdálený ladicí program pod jiným účtem. Tato chyba nastane pouze při spouštění vzdáleného ladicího programu v rámci místní systém nebo účet síťové služby. Při spuštění vzdáleného ladicího programu pod jiným účtem, může použít ověřování NTLM, která nevyžaduje DNS. . Tento postup, naleznete v tématu [Chyba: služba The Visual Studio Remote Debugger na cílovém počítači se nemůže připojit zpět k tomuto počítači](../debugger/error-the-visual-studio-remote-debugger-service-on-the-target-computer-cannot-connect-back-to-this-computer.md).



