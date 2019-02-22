---
title: Výběr strategie implementace modulu ladění | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debug engines, implementation strategies
ms.assetid: 90458fdd-2d34-4f10-82dc-6d8f31b66d8b
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e2fb608acdad60f5387750045a15f8eba36e2375
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56683204"
---
# <a name="choose-a-debug-engine-implementation-strategy"></a>Volba strategie implementace modulu ladění
Určení strategie implementace ladicí stroj (DE) pomocí architektury za běhu. Můžete vytvořit ladicí modul v rámci procesu program, který ladíte. Vytvořte ladicí modul v rámci procesu správci ladicí relaci sady Visual Studio (SDM). Nebo můžete vytvořit ladicí stroj mimo proces do obou z nich. Podle následujících pokynů byste mohli vybrat mezi tyto tři strategie.

## <a name="guidelines"></a>Pokyny
 I když je možné pro Německo mimo proces SDM a program, kterou ladíte, obvykle neexistuje žádný důvod k tomu. Volání přes hranice procesu jsou relativně pomalé.

 Ladění moduly jsou už k dispozici pro prostředí Win32 nativní run-time a společné prostředí runtime jazyka. Pokud je nutné nahradit DE buď prostředí, měli byste vytvořit DE-procesu s SDM.

 V opačném případě můžete buď vytvořit DE v rámci procesu SDM nebo v rámci procesu program, kterou ladíte. Musíte vzít v úvahu, pokud vyhodnocovač výrazů DE vyžaduje časté přístup k úložišti symbolů programu. Nebo, pokud úložiště symbolů je možné načíst do paměti pro rychlý přístup. Zvažte také následující přístupy:

-   Pokud nejsou k dispozici mnoho volání mezi vyhodnocovací filtr výrazů a úložiště symbolů nebo úložiště symbolů lze načíst do paměti SDM, vytvořte DE v rámci procesu SDM. Identifikátor CLSID ladicí stroj musí vrátit SDM při připojování vašeho programu. K vytvoření instance v procesu je DE SDM používá tento identifikátor CLSID.

-   Pokud DE musí volat program pro přístup k úložišti symbolů, vytvořte program DE v rámci procesu. V takovém případě program vytvoří instance DE.

## <a name="see-also"></a>Viz také:
- [Rozšiřitelnost ladicího programu Visual Studio](../../extensibility/debugger/visual-studio-debugger-extensibility.md)