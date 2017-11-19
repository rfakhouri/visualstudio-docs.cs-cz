---
title: "Postupy: ladění klientů a modelu COM pomocí ladění RPC servery | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.com
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- RPC (Remote Procedure Call), debugging COM clients and servers
- COM, debugging
- RPC (Remote Procedure Call)
- RPC (Remote Procedure Call), debugging
- COM clients, debugging
- COM servers, debugging
- out-of-process remote procedure call debugging
- remote debugging, RPC (Remote Procedure Call)
- in-process remote procedure call debugging
ms.assetid: 3e8526c8-43b5-4b87-8e0d-b22c24f0a3ea
caps.latest.revision: "23"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d93e56ce23948120f961720716f77ee9db5fb7b0
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-debug-com-clients-and-servers-using-rpc-debugging"></a>Postupy: Ladění klientů a serverů modelu COM pomocí ladění RPC
Ladění vzdáleného volání (procedur RPC) slouží k ladění aplikací modelu COM klienta nebo serveru. Je nutné povolit RPC Ladění povoleno ji používat. S povoleným laděním RPC, když krok do volání serveru z klienta, ladicí program připojí k serveru a umožňuje ladění jeho kódu. Pokud je připojen ladicí program, můžete použít všechny funkce ladicího programu s procesy klient i server.  
  
### <a name="to-enable-rpc-debugging"></a>Pokud chcete povolit ladění RPC  
  
1.  Na **nástroje** nabídky, klikněte na tlačítko **možnosti**.  
  
2.  V **možnosti** dialogové okno, klikněte **ladění** složky.  
  
3.  Klikněte **nativní** stránky.  
  
4.  Vyberte **ladění RPC** zaškrtávací políčko.  
  
    > [!NOTE]
    >  Chcete-li ladit volání RPC, musí mít oprávnění správce nebo Power Users.  
  
    > [!NOTE]
    >  RPC zanoříte se do vzdáleného serveru se systémem Microsoft Windows Vista bude fungovat pouze v případě, že je připojen nativní ladicí program ke vzdálenému serveru. Volání protokolu RPC, jinak nebude úspěšná bez chybovou zprávu. V opačném případě se dokončí volání protokolu RPC, ale krok do volání protokolu RPC nebude fungovat.  
  
## <a name="see-also"></a>Viz také  
 [COM Server a ladění kontejneru](../debugger/com-server-and-container-debugging.md)  
 [Ladění v sadě Visual Studio](../debugger/index.md) [prohlídka funkce ladicího programu](../debugger/debugger-feature-tour.md)