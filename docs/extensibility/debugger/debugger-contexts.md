---
title: "Ladicího programu kontexty | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: debugging [Debugging SDK], contexts
ms.assetid: 79808036-b680-4e4c-9c61-4ed43aa11323
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 809f0f50ace62253371d4fd14425bb870a3be633
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="debugger-contexts"></a>Kontexty ladicí program
V [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ladění, modul ladění (DE) funguje současně v několika různých kontextů, následujícím způsobem:  
  
-   Kontext kód, který popisuje aktuální umístění v datovém proudu spuštění programu.  
  
-   Kontext dokumentaci nebo pozice, která popisuje aktuální pozici ve zdrojovém dokumentu.  
  
-   Kontext vyhodnocení výrazu, který popisuje kontext ve výrazu, který bude vyhodnocení probíhat.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Kontext kódu](../../extensibility/debugger/code-context.md)  
 Popisuje kontext kódu jako adresu v datovém proudu instrukce programu v dnešních běhu architektury versus netradičních jazyky, kde nemusí být reprezentován kód podle pokynů, ale jiným způsobem.  
  
 [Pozice dokumentu](../../extensibility/debugger/document-position.md)  
 Definuje pozice dokumentu v sadě Visual Studio ladění prostřednictvím abstrakci pozici ve zdrojovém souboru, protože znám rozhraní IDE.  
  
 [Kontext dokumentu](../../extensibility/debugger/document-context.md)  
 Popisuje, jaké kontextu dokumentu představuje v sadě Visual Studio ladění ve vztahu k zdrojového souboru. Také popisuje, jak obslužná rutina symbol mapuje kontext kódu na dokumentaci kontextu.  
  
 [Kontext vyhodnocení výrazu](../../extensibility/debugger/expression-evaluation-context.md)  
 Obsahuje informace o kontextu vyhodnocení výrazu v sadě Visual Studio. Například kontextu vyhodnocení výrazu přidružené rámce zásobníku poskytuje kontext pro vyhodnocení lokální proměnné, parametry metody a členy třídy.  
  
## <a name="related-sections"></a>Související oddíly  
 [Ladění koncepty](../../extensibility/debugger/debugger-concepts.md)  
 Popisuje hlavní koncepty ladění architektury.  
  
 [Ladění komponent](../../extensibility/debugger/debugger-components.md)  
 Poskytuje přehled ladění součásti sady Visual Studio, mezi které patří ladění modulu (DE), vyhodnocovací filtr výrazů (EE) a symbol obslužné rutiny (SH).  
  
 [Ladění úlohy](../../extensibility/debugger/debugging-tasks.md)  
 Obsahuje odkazy na různé ladění úlohy, jako je například spuštěním programu a vyhodnocení výrazů.