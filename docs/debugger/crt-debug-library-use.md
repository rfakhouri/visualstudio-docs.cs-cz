---
title: Použití knihovny ladění CRT | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- c.debug.runtime
dev_langs:
- CSharp
- VB
- FSharp
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
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9434be46f357a97ad01f10ceec184ebe6c52eb43
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56624162"
---
# <a name="crt-debug-library-use"></a>Použití knihovny ladění CRT
Knihovny run-time jazyka C poskytuje rozsáhlou podporu ladění. Chcete-li použít jeden z knihovny ladění CRT, je nutné propojit s [/DEBUG](/cpp/build/reference/debug-generate-debug-info) a proveďte kompilaci s **/MDd**, **/MTD**, nebo **/LDd**.

## <a name="remarks"></a>Poznámky
 Hlavní definice a makra pro ladění CRT naleznete v hlavičkovém souboru CRTDBG.h.

 Funkce knihovny ladění CRT jsou kompilovány s ladicími informacemi ([/Z7, / Zd, / zi, /ZI (formát informací o ladění)](/cpp/build/reference/z7-zi-zi-debug-information-format)) a bez optimalizace. Některé funkce obsahovat výrazy ověřte parametry, které jsou předány na ně a zdrojový kód je k dispozici. Se tento zdrojový kód můžete krokovat s vnořením funkce CRT, funkce fungují podle očekávání a vyhledejte chybné parametry nebo paměti stavů potvrďte. (Některé technologie CRT je proprietární a neposkytuje zdrojový kód pro zpracování výjimek s plovoucí desetinnou čárkou a několik jiných rutin.)

 Když instalujete Visual C++, máte možnost instalace zdrojový kód knihovny run-time jazyka C na pevném disku. Pokud nenainstalujete zdrojový kód, budete potřebovat disk CD-ROM krokovat do funkce CRT.

 Další informace o různých běhových knihoven, které můžete použít, najdete v části [C Run-Time Libraries](/cpp/c-runtime-library/crt-library-features).

## <a name="see-also"></a>Viz také

- [Techniky ladění CRT](../debugger/crt-debugging-techniques.md)
- [/MD, /MT, /LD (použití knihovny run-time)](/cpp/build/reference/md-mt-ld-use-run-time-library)