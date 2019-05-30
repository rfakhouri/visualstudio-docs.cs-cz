---
title: Kontexty ladicího programu | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], contexts
ms.assetid: 79808036-b680-4e4c-9c61-4ed43aa11323
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 011999929fd4cb1508bf4958629e622684f35739
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66345998"
---
# <a name="debugger-contexts"></a>Kontexty ladicího programu
V [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ladění, ladicí stroj (DE) pracuje současně v rámci několika různých kontextech, následujícím způsobem:

- Kontext kódu, která popisuje aktuální umístění v datovém proudu provádění programu.

- Dokumentace ke službě kontext nebo umístění, která popisuje aktuální pozici ve zdrojovém dokumentu.

- Kontext vyhodnocení výrazu, popisující kontext, ve výrazu, který bude vyhodnocení proběhnout.

## <a name="in-this-section"></a>V tomto oddílu
 [Kontext kódu](../../extensibility/debugger/code-context.md) popisuje kontext kódu jako adresa ve službě stream instrukce programu v dnešní za běhu architektury oproti netradičních jazyky, ve kterém kód nemusí reprezentovat pokyny, ale jiným způsobem.

 [Pozice dokumentu](../../extensibility/debugger/document-position.md) definuje pozice dokumentu v ladění sady Visual Studio prostřednictvím abstrakce pozice ve zdrojovém souboru, protože ví, rozhraní IDE.

 [Kontext dokumentu](../../extensibility/debugger/document-context.md) popisuje, jaké kontext dokumentu představuje v ladění sady Visual Studio ve vztahu k zdrojový soubor. Popisuje také způsob mapování obslužné rutiny symbolů kontext kódu do kontextu dokumentace ke službě.

 [Kontext vyhodnocení výrazu](../../extensibility/debugger/expression-evaluation-context.md) obsahuje informace kontextu vyhodnocení výrazu v sadě Visual Studio. Třeba kontextu vyhodnocení výrazu přidružený blok zásobníku poskytuje kontext za vaše rozhodnutí vyzkoušet lokální proměnné, parametry metody a členy třídy.

## <a name="related-sections"></a>Související oddíly
 [Ladění koncepty](../../extensibility/debugger/debugger-concepts.md) popisuje hlavní koncepty ladění architektury.

 [Ladění komponenty](../../extensibility/debugger/debugger-components.md) obsahuje základní informace o ladění komponenty, které zahrnují ladicího stroje (DE), Chyba při vyhodnocování výrazu (EE) a obslužné rutiny symbolů (SH) sady Visual Studio.

 [Ladění úlohy](../../extensibility/debugger/debugging-tasks.md) obsahuje odkazy na různé úlohy ladění, například spuštění programu a vyhodnocení výrazů.