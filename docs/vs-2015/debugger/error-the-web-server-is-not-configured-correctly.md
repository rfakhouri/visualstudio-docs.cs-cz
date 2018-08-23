---
title: 'Chyba: Webový server není nakonfigurován správně | Dokumentace Microsoftu'
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
- vs.debug.remote.projnotconfigured
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- debugger, Web application errors
ms.assetid: 875ba87f-c372-4126-8fe3-e33931cf26c0
caps.latest.revision: 25
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 82d827e0f821712306cf1ec6049129fbf4437d67
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42673845"
---
# <a name="error-the-web-server-is-not-configured-correctly"></a>Chyba: Webový server není správně nakonfigurován.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [Chyba: webový server není nakonfigurován správně](https://docs.microsoft.com/visualstudio/debugger/error-the-web-server-is-not-configured-correctly).  
  
Mezi možné příčiny této chyby patří:  
  
-   Došlo k pokusu o ladění aplikace .NET Web, který byl zkopírován do jiného počítače, ručně přejmenovat nebo přesunout.  
  
-   Nemají dostatek připojení služby IIS. Další informace o nasazení webu do služby IIS najdete v tématu [vytvořit webovou stránku](http://www.iis.net/learn/get-started/getting-started-with-iis/create-a-web-site).  
  
-   Pokud se pokoušíte ladit aplikaci ASP.NET, najdete [publikování do služby IIS](https://docs.asp.net/en/latest/publishing/iis.html) pokyny k nasazení ke vzdálenému počítači se službou IIS 8 nebo novější, nebo [vzdálené ladění ASP.NET ve vzdáleném počítači7.5službyIIS](../debugger/remote-debugging-aspnet-on-a-remote-iis-7-5-computer.md) pokyny k nasazení na vzdálený počítač se systémem službu IIS 7.5.  
  
## <a name="see-also"></a>Viz také  
 [Ladění webových aplikací: Chyby a řešení potíží](../debugger/debugging-web-applications-errors-and-troubleshooting.md)



