---
title: 'Postupy: Zahájení a ukončení shromažďování dat o výkonu | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.performance.wizard.summarypage
helpviewer_keywords:
- profiling tools, launching sessions
- performance sessions, launching
- performance sessions, ending
- profiling tools, ending sessions
ms.assetid: 9f6eb0d5-d9e9-4bec-b627-445065610bce
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c570145c2a8eae887de691c2507683dddb93b2cf
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62996105"
---
# <a name="how-to-start-and-end-performance-data-collection"></a>Postupy: Zahájení a ukončení shromažďování dat o výkonu
Je nutné přidat cílový binární soubor, který chcete Profilovat, do relace výkonu, před zahájením profilování. Chcete-li přidat cíl, klikněte pravým tlačítkem na **cíle** v **prohlížeč výkonu**a potom klikněte na tlačítko **přidat cílový binární**. V **přidat cílový binární** dialogové okno, vyberte název souboru a pak klikněte na tlačítko **otevřít**. Přidání nové binární soubor.

### <a name="to-start-profiling"></a>Chcete-li spustit profilování

1. Klikněte pravým tlačítkem na název relace výkonu na **prohlížeč výkonu** okno a zvolte jednu z následujících možností:

    - **Spustit s nástrojem pro profilaci** – aplikaci spustí a začne okamžitě profilace.

    - **Spustit s Pozastaveným** – spustí aplikaci, která ale není spuštění profilování. Můžete spustit profilování tak, že vyberete **opět spustit shromažďování** v **ovládacího prvku sběru dat** okna. Další informace najdete v tématu [jak: Pozastavit a obnovit shromažďování údajů o výkonu](../profiling/how-to-pause-and-resume-performance-data-collection.md).

### <a name="to-end-profiling"></a>Do konce profilace

- Preferovanou metodu ukončení relace profilování se ukončíte aplikaci. Okamžitě zastavit profilaci na **prohlížeč výkonu** nástrojů, klikněte na tlačítko **Zastavit**.

## <a name="see-also"></a>Viz také:
- [Řízení shromažďování dat](../profiling/controlling-data-collection.md)
- [Postupy: Pozastavit a obnovit shromažďování údajů o výkonu](../profiling/how-to-pause-and-resume-performance-data-collection.md)