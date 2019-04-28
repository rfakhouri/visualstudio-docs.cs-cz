---
title: Moduly | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- modules
- debugging [Debugging SDK], modules
ms.assetid: c4cf2809-dbdb-4e75-9273-b3d3d77b67d0
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 611d067030cd935f6957a976c8a3aa2b7d4f8ae3
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62925398"
---
# <a name="modules"></a>Moduly
Z hlediska architektury ladicího programu *modulu*:

- Je fyzický kontejneru kódu, jako je spustitelný soubor nebo knihovny DLL.

- Můžete znovu načíst jeho symboly a popsat sám sebe. Modul popisy jsou zobrazovány v okně moduly v integrovaném vývojovém prostředí.

- Je reprezentován [IDebugModule2](../../extensibility/debugger/reference/idebugmodule2.md) rozhraní vytvořené ladicí stroj pro popis modulu.

## <a name="see-also"></a>Viz také:
- [Koncepty ladicího programu](../../extensibility/debugger/debugger-concepts.md)
- [IDebugModule2](../../extensibility/debugger/reference/idebugmodule2.md)