---
title: 'Postupy: vyhledání DLL, které Program selhal v | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.dll
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugger, DLL crashes
- Module List dialog box
- errors [debugger], DLL crashes
- Modules window
- debugging [Visual Studio], DLL crashes
- DLLs, load order of
ms.assetid: ecf62568-8b65-4a41-b8a4-e962ff2dfb71
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 350cd8a78780eb8ddb2a197ed1e8920fda23bbf3
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
ms.locfileid: "31474824"
---
# <a name="how-to-find-which-dll-your-program-crashed-in"></a>Postupy: Hledání knihovny DLL, ve které program selhal.
  
 Pokud vaše aplikace, dojde k chybě při volání systémové knihovny DLL nebo kód jiného uživatele, budete muset najít na které byl aktivní knihovny DLL, když došlo k havárii. Pokud dojde k chybě v knihovně DLL mimo vlastní program, můžete identifikovat pomocí umístění **moduly** okno.  
  
### <a name="to-find-where-a-crash-occurred-using-the-modules-window"></a>Najít kde havárie došlo k použití okna moduly  
  
1.  Poznamenejte si adresu, kde došlo k havárii.

    Pokud adresu není zobrazený v chybové zprávě, musíte použít alternativní metody k identifikaci knihovny DLL. Pokud máte podezření systémové knihovny DLL, můžete [načíst symboly](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md) ze serverů Microsoft Symbol při ladění. Jinak, budete muset [vytvořte soubor výpisu](../debugger/using-dump-files.md) s haldy informace místo. Různé [nástroje](https://blogs.msdn.microsoft.com/andrehal/2009/12/31/what-is-a-dump-and-how-do-i-create-one/) jsou k dispozici pro vytvoření výpisu souborů.
  
2.  Na **ladění** nabídce zvolte **Windows**a klikněte na tlačítko **moduly**.  
  
3.  V **moduly** okně Najít **adresu** sloupce. Musíte použít posuvník k jeho zobrazení.  
  
4.  Klikněte **adresu** tlačítka v horní části Tento sloupec seřadit podle adresy knihovny DLL.  
  
5.  Kontrola seřazený seznam najít knihovnu DLL, jejichž rozsah adres obsahuje umístění havárií.  
  
6.  Podívejte se na **název** a **cesta** sloupce zobrazíte DLL název a cesta.  
  
## <a name="see-also"></a>Viz také  
 [Ladění projektů knihovny DLL](../debugger/debugging-dll-projects.md)   
 [Postupy: použití okna moduly](../debugger/how-to-use-the-modules-window.md)