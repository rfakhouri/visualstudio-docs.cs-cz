---
title: Kontext dokumentu | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], contexts
ms.assetid: 8e8b5702-5c16-4988-953d-69dd807d8b84
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: d15e53d29adc04a82274ebd456027d15b0e41703
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66345703"
---
# <a name="document-context"></a>Kontext dokumentu
V [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ladění, *kontext dokumentu*:

- Představuje pozici ve zdrojovém souboru. Kontext dokumentu pro jazyky, kde nemusí být zdrojový soubor existuje, identifikuje pozici v dokumentu obvykle generovaných běhového prostředí. Například skriptovací stroj může generovat dokument ze skriptu. Další informace najdete v tématu [pozice dokumentu](../../extensibility/debugger/document-position.md).

- Popisuje umístění ve zdrojovém dokumentu, který odpovídá kontext kódu. Obslužné rutiny symbolů mapuje na dokumentaci kontextu, pomocí informací generovaných kompilátor nebo překladač kontext kódu.

- Je implementováno [IDebugDocumentContext2](../../extensibility/debugger/reference/idebugdocumentcontext2.md) rozhraní.

## <a name="see-also"></a>Viz také:
- [Kontext kódu](../../extensibility/debugger/code-context.md)
- [Poskytovatel symbolů](../../extensibility/debugger/symbol-provider.md)
- [Rozhraní poskytovatele symbolů](../../extensibility/debugger/reference/symbol-provider-interfaces.md)
- [Kontexty ladicího programu](../../extensibility/debugger/debugger-contexts.md)