---
title: Kontexty ladicího programu | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], contexts
ms.assetid: 79808036-b680-4e4c-9c61-4ed43aa11323
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7f24360b29557ef767d1a9a5f91a6f116db9ec12
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42673824"
---
# <a name="debugger-contexts"></a>Kontexty ladicího programu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [kontexty ladicího programu](https://docs.microsoft.com/visualstudio/extensibility/debugger/debugger-contexts).  
  
V [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] ladění, ladicí stroj (DE) pracuje současně v rámci několika různých kontextech, následujícím způsobem:  
  
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
  
 [Ladění komponent](../../extensibility/debugger/debugger-components.md)  
 Obsahuje přehled komponent ladění sady Visual Studio, mezi které patří ladicího stroje (DE), Chyba při vyhodnocování výrazu (EE) a obslužné rutiny symbolů (SH).  
  
 [Úlohy ladění](../../extensibility/debugger/debugging-tasks.md)  
 Obsahuje odkazy na různé úlohy ladění, jako je například spuštění programu a vyhodnocení výrazů.

