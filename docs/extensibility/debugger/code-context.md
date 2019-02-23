---
title: Kontext kódu | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], contexts
ms.assetid: 65e4d37a-086b-426e-9394-a3534967fd59
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 114537976561e72a9b1922c41d94ffa5e7ce613b
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56714541"
---
# <a name="code-context"></a>Kontext kódu
V [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ladění, **kontext kódu**:

-   Poskytuje abstrakci pozice v kódu, protože ví ladicí stroj (DE). Pro většinu za běhu architektury v současné době kontext kódu můžete představit jako adresa ve službě stream instrukce programu. Pro netradičních jazyky, ve kterém kód nemusí být reprezentována pokyny, může být reprezentována kontext kódu jiným způsobem.

-   Popisuje aktuální pozici v datovém proudu provádění programu, který ladíte.

-   Existuje pouze, když se program zastavení na zarážce.

-   Má objekt context přidružený dokument.

-   Je implementováno [IDebugCodeContext2](../../extensibility/debugger/reference/idebugcodecontext2.md) rozhraní.

## <a name="see-also"></a>Viz také:
- [Kontext dokumentu](../../extensibility/debugger/document-context.md)
- [Kontexty ladicího programu](../../extensibility/debugger/debugger-contexts.md)