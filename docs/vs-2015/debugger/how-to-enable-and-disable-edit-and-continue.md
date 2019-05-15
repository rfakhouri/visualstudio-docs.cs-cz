---
title: 'Postupy: Povolit a zakázat upravit a pokračovat | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- /INCREMENTAL linker option
- Apply Code Changes command
- Edit and Continue, disabling
- code changes, applying in break mode
- INCREMENTAL linker option
- Edit and Continue, enabling
- break mode, applying code changes
- Edit and Continue, applying code changes
- Step command
- Go command
ms.assetid: fd961a1c-76fa-420d-ad8f-c1a6c003b0db
caps.latest.revision: 29
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 70914da9be4046589a0ca3b8e5fd4ae13210ca51
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65689267"
---
# <a name="how-to-enable-and-disable-edit-and-continue"></a>Postupy: Povolit a zakázat upravit a pokračovat
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Můžete zakázat nebo povolit funkce upravit a pokračovat v **možnosti** dialogové okno v době návrhu. Toto nastavení při ladění, nelze změnit.  
  
 Upravit a pokračovat funguje pouze v sestaveních ladění. Pro nativní kód C++ upravit a pokračovat vyžaduje parametr/incremental – možnost.  
  
## <a name="procedures"></a>Procedury  
  
#### <a name="to-enabledisable-edit-and-continue"></a>Povolení nebo zakázání funkce upravit a pokračovat  
  
1. Otevřít stránky možnosti ladění (**nástroje / Možnosti / ladění**).  
  
2. Přejděte dolů k položce **upravit a pokračovat** kategorie.  
  
3. Pokud chcete povolit, vyberte **Povolit Editovat a pokračovat** zaškrtávací políčko. Pokud chcete zakázat, zrušte zaškrtnutí políčka.  
  
   > [!NOTE]
   > Pokud je povolená technologie IntelliTrace a shromažďovat události IntelliTrace a informace o volání, upravit a pokračovat je zakázané. Další informace najdete v tématu [nakonfigurujte nástroj IntelliTrace](https://msdn.microsoft.com/7657ecab-e07e-4b1b-872d-f05d966be37e).  
  
4. Klikněte na **OK**.  
  
   Další informace o těchto možnostech najdete v tématu [Obecné, ladění, dialogové okno Možnosti](../debugger/general-debugging-options-dialog-box.md).  
  
## <a name="see-also"></a>Viz také  
 [Operace Upravit a pokračovat](../debugger/edit-and-continue.md)
