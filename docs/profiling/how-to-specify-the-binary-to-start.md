---
title: 'Postupy: určení binárního souboru spuštění | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.property.itemlaunch
helpviewer_keywords:
- profiling tools, launching
- performance tools, launching
- performance sessions, launching
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 56da81bb1149ba927647a11d3b860d19a8bae43f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-specify-the-binary-to-start"></a>Postupy: určení binárního souboru spuštění

K profilu binární soubory například knihovny DLL, je třeba zadat informace v  **\<cíl > stránky vlastností** dialogové okno. Tyto informace označuje, kde je volající aplikace projektu knihovny DLL.

1. V **prohlížeč výkonu**, klikněte pravým tlačítkem na cílový binární soubor a pak klikněte na tlačítko **vlastnosti**.

2. V **stránky vlastností** dialogové okno, klikněte **spusťte** vlastnosti.

3. Vyberte **přepsat vlastnosti projektu** zaškrtávací políčko.

4. V **spustitelný soubor spustit** textové pole, zadejte umístění souborů.

5. V **argumenty** textové pole, zadejte argumenty, které jsou nezbytné ke spuštění aplikace.

6. V **pracovní adresář** textové pole, zadejte umístění adresáře.

7. Click **OK**.

## <a name="see-also"></a>Viz také

[Konfigurace výkonnostních relací](../profiling/configuring-performance-sessions.md)