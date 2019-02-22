---
title: Sestava operací (zobrazení vláken) na disku | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.cv.threads.report.diskoperations
helpviewer_keywords:
- Concurrency Visualizer, File Operations Report (Threads View)
ms.assetid: e352f4f3-f654-45eb-96ed-417863487ddc
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c890ac9dbd3b542a400fc2a5b6db7ee2eb8f5db2
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56613853"
---
# <a name="disk-operations-report-threads-view"></a>Sestava diskových operací (Zobrazení vláken)
Sestava diskových operací ukazuje vstupně-výstupních operací disku v kanálech disku.

 Pro každý přístup na disk, který se nachází jménem proces, který je právě profilována v současném viditelném časovém okně se použije v hlášení tyto informace:

-   Název a identifikátor PID procesu, který provádí přístup k disku

-   ID vlákna, která využívají disku

-   Název souboru, která se použila

-   Počet čtení na souboru

-   Počet přečtených bajtů

-   Latence čtení v milisekundách

-   Počet zápisů

-   Počet zapsaných bajtů

-   Latence zápisu, v milisekundách

## <a name="see-also"></a>Viz také:
- [Zobrazení vláken](../profiling/threads-view-parallel-performance.md)