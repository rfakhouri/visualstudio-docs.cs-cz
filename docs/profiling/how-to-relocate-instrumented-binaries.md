---
title: 'Postupy: přemístění instrumentovaných binárních souborů | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.property.binaries
helpviewer_keywords:
- binaries, instrumented
- instrumentation, instrumented binaries
- instrumented binaries and relocating
- profiling tools, instrumented binaries
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ecf5b46fa6b3fee6e2df354133a0c371466ff5fe
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-relocate-instrumented-binaries"></a>Postupy: Přemístění instrumentovaných binárních souborů

Během instrumentace sondy vloženy do binárního souboru k měření výkonu aplikace. Výběrem přesunovat instrumentované binární je kopii původní binární instrumentovány a put v zadaném umístění. Tato možnost je užitečná, pokud nechcete, aby profileru přejmenovat vašeho původního binární. Pokud není přemístění binárního souboru, původní verze binárního souboru se přepíše.

## <a name="to-relocate-instrumented-binary"></a>Instrumentované binární přesunovat

1. V **prohlížeč výkonu**, klikněte pravým tlačítkem na výkonnostní relace a pak klikněte na tlačítko **vlastnosti**.

2. V **stránky vlastností**, klikněte **binární** vlastnosti.

3. Vyberte **přemístění instrumentovaných binárních souborů** zaškrtávací políčko.

4. Zadejte umístění pro instrumentované binární.

## <a name="see-also"></a>Viz také

[Konfigurace výkonnostních relací](../profiling/configuring-performance-sessions.md)  
[VSInstr](../profiling/vsinstr.md)
