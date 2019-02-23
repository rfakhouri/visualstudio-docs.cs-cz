---
title: Kontrola systémového kódu po výjimce | Dokumentace Microsoftu
ms.custom: seodec18
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging, exceptions
- exceptions, debugging
ms.assetid: a38ad49b-7cf3-483d-91c4-eb3116eba50c
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: fc3611c1f4b12b05b725725c6c8d92105d637bab
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56694319"
---
# <a name="how-to-examine-system-code-after-an-exception"></a>Postupy: Kontrola systémového kódu po výjimce
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
- [Správa výjimek pomocí ladicího programu](../debugger/managing-exceptions-with-the-debugger.md)