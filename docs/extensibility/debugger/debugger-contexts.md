---
title: Kontexty ladicího programu | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], contexts
ms.assetid: 79808036-b680-4e4c-9c61-4ed43aa11323
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 80e37d2994d446588de511c4f341381ca8611f1f
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53930182"
---
# <a name="debugger-contexts"></a>Kontexty ladicího programu
V [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ladění, ladicí stroj (DE) pracuje současně v rámci několika různých kontextech, následujícím způsobem:  
  
-   Kontext kódu, která popisuje aktuální umístění v datovém proudu provádění programu.  
  
-   Dokumentace ke službě kontext nebo umístění, která popisuje aktuální pozici ve zdrojovém dokumentu.  
  
-   Kontext vyhodnocení výrazu, popisující kontext, ve výrazu, který bude vyhodnocení proběhnout.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Kontext kódu](../../extensibility/debugger/code-context.md)  
 Tento článek popisuje kontext kódu jako adresa ve službě stream instrukce programu v dnešní za běhu architektury oproti netradičních jazyky, ve kterém kód nemusí reprezentovat pokyny, ale jiným způsobem.  
  
 [Pozice dokumentu](../../extensibility/debugger/document-position.md)  
 Definuje pozice dokumentu v ladění prostřednictvím abstrakce pozice ve zdrojovém souboru, protože ví, integrovaném vývojovém prostředí sady Visual Studio.  
  
 [Kontext dokumentu](../../extensibility/debugger/document-context.md)  
 Popisuje, jaké kontext dokumentu představuje v ladění sady Visual Studio ve vztahu k zdrojový soubor. Popisuje také způsob mapování obslužné rutiny symbolů kontext kódu do kontextu dokumentace ke službě.  
  
 [Kontext vyhodnocení výrazu](../../extensibility/debugger/expression-evaluation-context.md)  
 Obsahuje informace kontextu vyhodnocení výrazu v sadě Visual Studio. Třeba kontextu vyhodnocení výrazu přidružený blok zásobníku poskytuje kontext za vaše rozhodnutí vyzkoušet lokální proměnné, parametry metody a členy třídy.  
  
## <a name="related-sections"></a>Související oddíly  
 [Ladění koncepty](../../extensibility/debugger/debugger-concepts.md)  
 Popisuje hlavní koncepty ladění architektury.  
  
 [Ladění komponenty](../../extensibility/debugger/debugger-components.md)  
 Obsahuje přehled komponent ladění sady Visual Studio, mezi které patří ladicího stroje (DE), Chyba při vyhodnocování výrazu (EE) a obslužné rutiny symbolů (SH).  
  
 [Ladění úloh](../../extensibility/debugger/debugging-tasks.md)  
 Obsahuje odkazy na různé úlohy ladění, jako je například spuštění programu a vyhodnocení výrazů.