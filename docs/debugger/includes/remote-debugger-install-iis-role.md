---
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.openlocfilehash: 103cefa8573c8f44efff0b53b0c09a5ec26706e6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
Tyto kroky ukazují pouze základní konfiguraci služby IIS. Podrobnější informace, nebo nainstalovat do počítače s Windows Desktop, najdete v části [publikování do služby IIS](https://docs.microsoft.com/aspnet/core/publishing/iis?tabs=aspnetcore2x#iis-configuration) nebo [IIS 8.0 pomocí technologie ASP.NET 3.5 a technologii ASP.NET 4.5](https://docs.microsoft.com/iis/get-started/whats-new-in-iis-8/iis-80-using-aspnet-35-and-aspnet-45).

Pro operační systémy Windows Server, použijte **přidat role a funkce** Průvodce prostřednictvím **spravovat** odkaz nebo **řídicí panel** na odkaz v **správce serveru**. Na **role serveru** kroku, zaškrtněte políčko pro **webového serveru (IIS)**.

![Role webového serveru IIS je vybrali v kroku rolí vyberte server.](../media/remotedbg-server-roles-ws2012.png)

Na **služby rolí** kroku, vyberte služby rolí služby IIS požadavky nebo přijměte výchozí nastavení role služeb zadaný.

Pokračujte potvrzení postup instalace role Webový server a služby. Po instalaci role webového serveru (IIS) není nutné restartovat server nebo služby IIS.