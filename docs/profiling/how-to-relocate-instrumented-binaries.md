---
title: 'Postupy: Přemístění instrumentovaných binárních souborů | Dokumentace Microsoftu'
ms.date: 11/04/2016
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
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 96faf382145d7c4541f1fe66f872ad3622f64631
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62539296"
---
# <a name="how-to-relocate-instrumented-binaries"></a>Postupy: Přemístění instrumentovaných binárních souborů

Během instrumentace testy jsou vloženy do binárního souboru k měření výkonu aplikace. Výběrem přemístit instrumentované binární kopii původní binární soubor je instrumentovány a umístit do zadaného umístění. Tato možnost je užitečná, pokud nechcete, aby se profiler k přejmenování původní binární soubor. Pokud není přemístit binární soubor, přepíše původní verze binárního souboru.

## <a name="to-relocate-instrumented-binary"></a>K přesunutí instrumentovaný binární soubor

1. V **prohlížeč výkonu**, klikněte pravým tlačítkem na relaci výkonu a pak klikněte na tlačítko **vlastnosti**.

2. V **stránky vlastností**, klikněte na tlačítko **binární** vlastnosti.

3. Vyberte **přemístění instrumentovaných binárních souborů** zaškrtávací políčko.

4. Zadejte umístění pro instrumentované binární soubor.

## <a name="see-also"></a>Viz také:

[Konfigurace výkonnostních relací](../profiling/configuring-performance-sessions.md)
[VSInstr](../profiling/vsinstr.md)
