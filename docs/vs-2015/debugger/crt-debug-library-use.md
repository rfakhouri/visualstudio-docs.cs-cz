---
title: Použití knihovny ladění CRT | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- c.debug.runtime
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- /DEBUG linker option [C++]
- crtdbg.h file
- debug library
- MDd compiler option [C++]
- libraries, CRT debug library
- MTd compiler option [C++]
- LDd compiler function [C++]
- /MTd compiler option [C++]
- /MDd compiler option [C++]
- debugging [CRT], CRT debug library
- DEBUG linker option [C++]
- /LDd compiler function [C++]
ms.assetid: 464de16b-4215-4787-9bfa-921aaff9d9f4
caps.latest.revision: 19
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 51534d226f3ae0f8726bb818423bf0a9b788fd8c
ms.sourcegitcommit: c496a77add807ba4a29ee6a424b44a5de89025ea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54834657"
---
# <a name="crt-debug-library-use"></a>Použití knihovny ladění CRT
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Knihovny run-time jazyka C poskytuje rozsáhlou podporu ladění. Chcete-li použít jeden z knihovny ladění CRT, je nutné propojit s [/DEBUG](http://msdn.microsoft.com/library/1af389ae-3f8b-4d76-a087-1cdf861e9103) a proveďte kompilaci s **/MDd**, **/MTD**, nebo **/LDd**.  
  
## <a name="remarks"></a>Poznámky  
 Hlavní definice a makra pro ladění CRT naleznete v hlavičkovém souboru CRTDBG.h.  
  
 Funkce knihovny ladění CRT jsou kompilovány s ladicími informacemi ([/Z7, / Zd, / zi, /ZI (formát informací o ladění)](http://msdn.microsoft.com/library/ce9fa7e1-0c9b-47e3-98ea-26d1a16257c8)) a bez optimalizace. Některé funkce obsahovat výrazy ověřte parametry, které jsou předány na ně a zdrojový kód je k dispozici. Se tento zdrojový kód můžete krokovat s vnořením funkce CRT, funkce fungují podle očekávání a vyhledejte chybné parametry nebo paměti stavů potvrďte. (Některé technologie CRT je proprietární a neposkytuje zdrojový kód pro zpracování výjimek s plovoucí desetinnou čárkou a několik jiných rutin.)  
  
 Když instalujete Visual C++, máte možnost instalace zdrojový kód knihovny run-time jazyka C na pevném disku. Pokud nenainstalujete zdrojový kód, budete potřebovat disk CD-ROM krokovat do funkce CRT.  
  
 Další informace o různých běhových knihoven, které můžete použít, najdete v části [C Run-Time Libraries](http://msdn.microsoft.com/library/a889fd39-807d-48f2-807f-81492612463f).  
  
## <a name="see-also"></a>Viz také  
 [Techniky ladění CRT](../debugger/crt-debugging-techniques.md)   
 [/MD, /MT, /LD (použití knihovny run-time)](http://msdn.microsoft.com/library/cf7ed652-dc3a-49b3-aab9-ad60e5395579)
