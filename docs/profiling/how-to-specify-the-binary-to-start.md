---
title: 'Postupy: Určení binárního souboru ke spuštění | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.performance.property.itemlaunch
helpviewer_keywords:
- profiling tools, launching
- performance tools, launching
- performance sessions, launching
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8a82e67d92dcb7b59898e4eb9d4b72d3e53ff351
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54952571"
---
# <a name="how-to-specify-the-binary-to-start"></a>Postupy: Určení binárního souboru ke spuštění

Pro binární soubory profilu například knihovny DLL, je třeba zadat informace v  **\<cíl > stránky vlastností** dialogové okno. Tato informace indikuje, kde najít projekt knihovny DLL volající aplikace.

1. V **prohlížeč výkonu**, klikněte pravým tlačítkem na cílový binární soubor a potom klikněte na tlačítko **vlastnosti**.

2. V **stránky vlastností** dialogové okno, klikněte na tlačítko **spuštění** vlastnosti.

3. Vyberte **přepsat vlastnosti projektu** zaškrtávací políčko.

4. V **spustitelný soubor ke spuštění** textové pole, zadejte umístění souboru.

5. V **argumenty** textové pole, zadejte argumenty, které jsou vyžadovány pro spuštění aplikace.

6. V **pracovní adresář** textové pole, zadejte umístění adresáře.

7. Klikněte na **OK**.

## <a name="see-also"></a>Viz také:

[Konfigurace výkonnostních relací](../profiling/configuring-performance-sessions.md)