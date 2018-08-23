---
title: 'Postupy: povolení a zakázání upravit a pokračovat | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
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
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 57a9ec8b8e25da6edb36e1983e45f7bb78251208
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42675515"
---
# <a name="how-to-enable-and-disable-edit-and-continue"></a>Postupy: Povolení a zákaz operace Upravit a pokračovat
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [postupy: povolení a zakázání upravit a pokračovat](https://docs.microsoft.com/visualstudio/debugger/how-to-enable-and-disable-edit-and-continue).  
  
Můžete zakázat nebo povolit funkce upravit a pokračovat v **možnosti** dialogové okno v době návrhu. Toto nastavení při ladění, nelze změnit.  
  
 Upravit a pokračovat funguje pouze v sestaveních ladění. Pro nativní kód C++ upravit a pokračovat vyžaduje parametr/incremental – možnost.  
  
## <a name="procedures"></a>Procedury  
  
#### <a name="to-enabledisable-edit-and-continue"></a>Povolení nebo zakázání funkce upravit a pokračovat  
  
1.  Otevřít stránky možnosti ladění (**nástroje / Možnosti / ladění**).  
  
2.  Přejděte dolů k položce **upravit a pokračovat** kategorie.  
  
3.  Pokud chcete povolit, vyberte **Povolit Editovat a pokračovat** zaškrtávací políčko. Pokud chcete zakázat, zrušte zaškrtnutí políčka.  
  
    > [!NOTE]
    >  Pokud je povolená technologie IntelliTrace a shromažďovat události IntelliTrace a informace o volání, upravit a pokračovat je zakázané. Další informace najdete v tématu [nakonfigurujte nástroj IntelliTrace](http://msdn.microsoft.com/en-us/7657ecab-e07e-4b1b-872d-f05d966be37e).  
  
4.  Klikněte na tlačítko **OK**.  
  
 Další informace o těchto možnostech najdete v tématu [Obecné, ladění, dialogové okno Možnosti](../debugger/general-debugging-options-dialog-box.md).  
  
## <a name="see-also"></a>Viz také  
 [Upravit a pokračovat](../debugger/edit-and-continue.md)



