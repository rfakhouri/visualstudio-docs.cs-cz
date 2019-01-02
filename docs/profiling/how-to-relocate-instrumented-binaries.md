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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f8b50c5b76ea5b22bc9d734d32e433db1c7594d9
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53893075"
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
