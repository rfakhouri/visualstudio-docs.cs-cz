---
title: Servery (Visual Studio SDK) | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- servers, debugging
- debugging [Debugging SDK], servers
ms.assetid: 62236d64-7956-448c-9ac3-5528f3edac1d
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ebd991a5bb61211a33cc965668c48644bdcf9a27
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66348598"
---
# <a name="servers-visual-studio-sdk"></a>Servery (Visual Studio SDK)
V architektuře ladicího programu *server*:

- Je kontejner, portů a dodavatelé portů a komunikuje porty a dodavatelé portů Správce ladění relace (SDM) a ladicí stroj.

- Můžete identifikovat podle názvu a vypsat jeho porty a dodavatelé portů.

- Je reprezentován [IDebugCoreServer2](../../extensibility/debugger/reference/idebugcoreserver2.md) rozhraní, které je implementováno pouze Visual Studio (jednu instanci serveru pro každou instanci sady Visual Studio spuštěná).

## <a name="see-also"></a>Viz také:
- [Porty](../../extensibility/debugger/ports.md)
- [Dodavatelé portů](../../extensibility/debugger/port-suppliers.md)
- [Koncepty ladicího programu](../../extensibility/debugger/debugger-concepts.md)
- [IDebugCoreServer2](../../extensibility/debugger/reference/idebugcoreserver2.md)