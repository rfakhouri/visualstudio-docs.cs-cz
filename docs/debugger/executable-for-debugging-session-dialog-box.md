---
title: "Spustitelný soubor pro relaci dialogové okno ladění | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.exefordebug
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- executable files, specifying when debugging
- DLLs, debugging
- debugger, Executable for Debugging Session dialog box
- Executable for Debugging Session dialog box
ms.assetid: c0ddbe32-b99f-4425-acf1-f48842804f56
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e2fa8dfde80cff512ca6f774d8ee90a524931450
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="executable-for-debugging-session-dialog-box"></a>Dialogové okno Spustitelný soubor pro relaci ladění
Toto dialogové okno se zobrazí při pokusu o ladění knihovny DLL pro které žádný spustitelný soubor je zadán. Visual Studio nelze spustit knihovnu DLL přímo. Místo toho spustíte zadaný spustitelný soubor. Knihovny DLL můžete ladit, když je volána metodou spustitelný soubor.  
  
 **Název spustitelného souboru**  
 Zadejte název cesty k spustitelné soubory, které volá knihovnu DLL, kterou ladíte.  
  
 **Adresa URL, kde může být projektu získat přístup k (pouze Server knihovny ATL)**  
 Pokud ladíte knihovny DLL knihovny ATL Server, zadejte adresu URL, kde můžete najít projekt.  
  
 Po zadání těchto nastavení jsou uloženy v projektu stránky vlastností, takže nebude nutné zadávat znovu při následné relace ladění. Pokud potřebujete změnit nastavení, můžete otevření stránek vlastností a změnit hodnoty. Další informace o určení spustitelný soubor pro relaci ladění najdete v tématu [ladění knihoven DLL](../debugger/how-to-debug-from-a-dll-project.md).  
  
## <a name="see-also"></a>Viz také  
 [Ladění v sadě Visual Studio](../debugger/index.md)  
 [Prohlídka funkce ladicí program](../debugger/debugger-feature-tour.md)