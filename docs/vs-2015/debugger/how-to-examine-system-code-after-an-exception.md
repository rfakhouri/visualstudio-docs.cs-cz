---
title: 'Postupy: Kontrola systémového kódu po výjimce | Dokumentace Microsoftu'
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
- debugging, exceptions
- exceptions, debugging
ms.assetid: a38ad49b-7cf3-483d-91c4-eb3116eba50c
caps.latest.revision: 18
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 289ef1825e8034566e2a9595a46919a3c498108d
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54755947"
---
# <a name="how-to-examine-system-code-after-an-exception"></a>Postupy: Kontrola systémového kódu po výjimce
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Když dojde k výjimce, bude pravděpodobně pro zkoumání kódu uvnitř do systémových volání a zjistěte příčinu výjimku. Následující postup vysvětluje, jak to provést, pokud nemáte byly načteny symboly pro kód systému nebo pokud je povoleno pouze můj kód.  
  
### <a name="to-examine-system-code-following-an-exception"></a>Chcete-li kontrola systémového kódu po výjimce  
  
1.  V **zásobník volání** okna, klikněte pravým tlačítkem, poté klikněte na tlačítko **zobrazit externí kód**.  
  
     Pokud není povolena funkce pouze můj kód, tato možnost není k dispozici v místní nabídce a ve výchozím nastavení se zobrazí kód systému.  
  
2.  Klikněte pravým tlačítkem na externí kód snímky, které se teď zobrazují v **zásobník volání** okna.  
  
3.  Přejděte na **načíst symboly z** a potom klikněte na tlačítko **Microsoft Symbol Servers**.  
  
    1.  Pokud byla povolena funkce pouze můj kód, zobrazí se dialogové okno. Uvádí, že nyní byla zakázána funkce pouze můj kód. To je nezbytné pro krokování s vnořením do systémových volání.  
  
    2.  **Stahování veřejných symbolů** zobrazí se dialogové okno. Zmizí při stahování dokončí.  
  
4.  Nyní můžete prozkoumat kód v systému **zásobník volání** okno a dalších oknech. Například dvojitým kliknutím na rámec zásobníku volání a zobrazte kód ve zdroji nebo **zpětný překlad** okna.  
  
## <a name="see-also"></a>Viz také  
 [Správa výjimek pomocí ladicího programu](../debugger/managing-exceptions-with-the-debugger.md)
