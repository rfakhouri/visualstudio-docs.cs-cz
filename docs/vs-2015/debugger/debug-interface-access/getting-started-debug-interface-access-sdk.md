---
title: Začínáme (přístup k rozhraní ladění SDK) | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- .dbg files
- DBG files
ms.assetid: cb3d040a-2846-40d7-bdbc-8a5beb5dd2f6
caps.latest.revision: 18
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 54f83f00ed2e99d1541e15092cb3ee0ce9e08952
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68164174"
---
# <a name="getting-started-debug-interface-access-sdk"></a>Začínáme (Přístup k rozhraní ladění SDK)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Ladění rozhraní přístup (DIA) SDK vám poskytuje s instruktážní dokumentace a ukázky, která ukazuje, jak použít rozhraní API DIA. Použití rozhraní a metody v sadě DIA SDK k vývoji vlastních aplikací, které otevírají soubory .pdb a dbg a prohledávat jejich obsah pro symboly, hodnoty, atributy, adresy a další informace o ladění. Tato sada SDK také obsahuje referenční tabulky pro vlastnosti přidružené k symboly v aplikacích jazyka C++.  
  
 Nejlepší použít sadu SDK DIA., měli seznámit s následujícími možnostmi:  
  
- Programovací jazyk C++  
  
- Programování v modelu COM  
  
- Visual Studio prostředí integrovaného vývojového (prostředí IDE) pro kompilaci ukázky  
  
  DIA SDK je obvykle nainstalován se sadou Visual Studio a jeho výchozí umístění je *[jednotka]* \Program Files\Microsoft 9.0\DIA sady Visual Studio SDK. Jako součást instalace, msdia90.dll, který implementuje DIA SDK automaticky zaregistrované, aby vše, co musíte udělat pro použití se zahrnou `dia2.h` ve vaší aplikaci a odkaz na `diaguids.lib`.  
  
  Záhlaví: include\dia2.h  
  
  Knihovna: lib\diaguids.lib  
  
  DLL: bin\msdia80.dll  
  
  IDL: idl\dia2.idl  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Přehled](../../debugger/debug-interface-access/overview-debug-interface-access-sdk.md)  
 Revize základní architekturu sady  
  
 [Dotazování na soubor .Pdb](../../debugger/debug-interface-access/querying-the-dot-pdb-file.md)  
 Obsahuje podrobné pokyny o tom, jak použít rozhraní API DIA k dotazování soubor .pdb.  
  
## <a name="see-also"></a>Viz také  
 [Přístup k rozhraní ladění SDK](../../debugger/debug-interface-access/debug-interface-access-sdk.md)
