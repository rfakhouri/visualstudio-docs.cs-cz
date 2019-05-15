---
title: 'Chyba: Nelze automaticky krokování s vnořením do serveru | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
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
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: c8dcb8fa757f1cccf2f3aef6c2520e0c61da0b9f
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65682682"
---
# <a name="error-unable-to-automatically-step-into-the-server"></a>Chyba: Nelze automaticky krokování s vnořením do serveru
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Chyba čtení:  
  
 Nepovedlo se automatické krokování s vnořením do serveru. Ladicí program nebyl upozorněn, než se provedl vzdálené procedury  
  
 Této chybě může dojít, když se pokoušíte Krokovat s vnořením webové služby (viz [krokování do webové služby XML](https://msdn.microsoft.com/8e67de38-bf5f-41cc-a457-1b88ce63d764)). To může nastat, když [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] není správně nastavený.  
  
 Možné příčiny:  
  
- Soubor web.config pro vaše [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] aplikace v není nastaven na hodnotu "true" debug (naleznete v tématu [režim ladění v aplikacích ASP.NET](../debugger/how-to-enable-debugging-for-aspnet-applications.md)).  
  
- Verze [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] instaloval po instalaci sady Visual Studio. [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] musí se nainstalovat před Visual Studio. Chcete-li tento problém vyřešit, použijte Windows **ovládací panely**, **programy a funkce** opravit instalaci sady Visual Studio.  
  
## <a name="see-also"></a>Viz také  
 [Vzdálené ladění chyby a řešení potíží](../debugger/remote-debugging-errors-and-troubleshooting.md)   
 [Vzdálené ladění](../debugger/remote-debugging.md)
