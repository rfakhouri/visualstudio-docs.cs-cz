---
title: 'Chyba: Automatické krokování s vnořením do serveru nelze | Dokumentace Microsoftu'
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
- vs.debug.error.causality_no_server_response
dev_langs:
- FSharp
- VB
- CSharp
- C++
- JScript
- VB
- CSharp
- C++
helpviewer_keywords:
- remote debugging, notification error
ms.assetid: 9a370ccc-d358-429c-b285-9b6c0649bc68
caps.latest.revision: 16
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d75ed4ddb42705b95a5ddd834596bc828e0f3ec2
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42633564"
---
# <a name="error-unable-to-automatically-step-into-the-server"></a>Chyba: Automatické krokování s vnořením do serveru se nezdařilo.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [Chyba: nelze automaticky krok do the Server](https://docs.microsoft.com/visualstudio/debugger/error-unable-to-automatically-step-into-the-server).  
  
Chyba čtení:  
  
 Nepovedlo se automatické krokování s vnořením do serveru. Ladicí program nebyl upozorněn, než se provedl vzdálené procedury  
  
 Této chybě může dojít, když se pokoušíte Krokovat s vnořením webové služby (viz [krokování do webové služby XML](http://msdn.microsoft.com/en-us/8e67de38-bf5f-41cc-a457-1b88ce63d764)). To může nastat, když [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] není správně nastavený.  
  
 Možné příčiny:  
  
-   Soubor web.config pro vaše [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] aplikace v není nastaven na hodnotu "true" debug (naleznete v tématu [režim ladění v aplikacích ASP.NET](../debugger/how-to-enable-debugging-for-aspnet-applications.md)).  
  
-   Verze [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] instaloval po instalaci sady Visual Studio. [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] musí se nainstalovat před Visual Studio. Chcete-li tento problém vyřešit, použijte Windows **ovládací panely**, **programy a funkce** opravit instalaci sady Visual Studio.  
  
## <a name="see-also"></a>Viz také  
 [Vzdálené ladění chyby a řešení potíží](../debugger/remote-debugging-errors-and-troubleshooting.md)   
 [Vzdálené ladění](../debugger/remote-debugging.md)



