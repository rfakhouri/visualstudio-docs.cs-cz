---
title: Moduly | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- modules
- debugging [Debugging SDK], modules
ms.assetid: c4cf2809-dbdb-4e75-9273-b3d3d77b67d0
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: b231ee1eb84f41115a0892cda42a8b7e781e5e53
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66350681"
---
# <a name="modules"></a>Moduly
Z hlediska architektury ladicího programu *modulu*:

- Je fyzický kontejneru kódu, jako je spustitelný soubor nebo knihovny DLL.

- Můžete znovu načíst jeho symboly a popsat sám sebe. Modul popisy jsou zobrazovány v okně moduly v integrovaném vývojovém prostředí.

- Je reprezentován [IDebugModule2](../../extensibility/debugger/reference/idebugmodule2.md) rozhraní vytvořené ladicí stroj pro popis modulu.

## <a name="see-also"></a>Viz také:
- [Koncepty ladicího programu](../../extensibility/debugger/debugger-concepts.md)
- [IDebugModule2](../../extensibility/debugger/reference/idebugmodule2.md)