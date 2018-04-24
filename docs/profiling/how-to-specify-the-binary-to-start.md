---
title: 'Postupy: určení binárního souboru spuštění | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
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
ms.openlocfilehash: ac87c771cf6d9515f3eae8d82f7d0d40fa6590a8
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-specify-the-binary-to-start"></a>Postupy: Určení binárního souboru ke spuštění

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