---
title: Podpora služby jazyka pro ladění | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugger, language support
- language services, debugging support
ms.assetid: 7a44067f-a410-4a6a-84d2-bda5184140bc
caps.latest.revision: 16
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: c61f7fa7e698e2c01cadb1dbb36a321c6e656e35
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68194998"
---
# <a name="language-service-support-for-debugging"></a>Podpora služby jazyka pro ladění
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Služba jazyka může poskytovat funkce, které podporují ladicí program prostřednictvím <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageDebugInfo> rozhraní. Tyto funkce patří ověřování zarážek a poskytnutí seznam výrazů **automatické hodnoty** okna.  
  
 Musíte však mít vyhodnocovače výrazů pro ladění jazyka. Chyba při vyhodnocování výrazu je zodpovědná za vaše rozhodnutí vyzkoušet výrazy k vytvoření hodnot při ladění. Informace o implementace vyhodnocovače výrazů modulu CLR najdete v tématu:  
  
- [Vyhodnocovače výrazů modulu CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators)  
  
- [Ukázka Vyhodnocovač spravovaných výrazů](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)  
  
## <a name="compiler-output"></a>Výstup kompilátoru  
 Typ kompilátoru jazyka určuje, co je potřeba provést k implementaci ladění pro váš jazyk. Pokud se kompilátor zaměřuje na operační systém Windows a zapíše soubor PDB, můžete ladit programy s nativním kódem ladicím modulu, který je integrovaný do sady Visual Studio. Pokud váš kompilátor vytvoří jazyk Microsoft intermediate language (MSIL), můžete ladit programy se spravovaným kódem ladění modul, který je také integrované do sady Visual Studio. Pokud se kompilátor zaměřuje na proprietární operačního systému nebo jiné běhové prostředí, budete muset napsat vlastní modulu pro ladění.  
  
 Další informace o implementaci ladění jazyka najdete v tématu [Začínáme](../../extensibility/debugger/getting-started-with-debugger-extensibility.md) v aplikaci Visual Studio SDK ladění.
