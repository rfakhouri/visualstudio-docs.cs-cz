---
title: Sledování souborů | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- msbuild, file tracking
ms.assetid: e6c66ac0-3464-451f-9192-3b98dca21b4a
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7770da734143b2b6185b266137eeb46ba25bd32a
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56640607"
---
# <a name="file-tracking"></a>Sledování souborů
Volání do systému souborů Windows pro proces a podřízené procesy protokolů sledování souborů. Voláním funkcí uvedených níže programy řídí, kdy zapnout a vypnout protokolování a určit soubor protokolu, který chcete použít.

- [EndTrackingContext](../msbuild/endtrackingcontext.md) zastavte sledování aktuálního kontextu.

- [ResumeTracking](../msbuild/resumetracking.md) obnovte sledování po volání [SuspendTracking](../msbuild/suspendtracking.md).

- [SetThreadCount](../msbuild/setthreadcount.md) nastavte počet vláken pro sledování.

- [StartTrackingContext](../msbuild/starttrackingcontext.md) začněte nový kontext sledování.

- [StartTrackingContextWithRoot](../msbuild/starttrackingcontextwithroot.md) začněte nový kontext sledování se zadaným kořenem.

- [StopTrackingAndCleanup](../msbuild/stoptrackingandcleanup.md) End sledování a uvolnit zdroje používá.

- [SuspendTracking](../msbuild/suspendtracking.md) dočasně pozastavit sledování.

- [WriteAllTLogs](../msbuild/writealltlogs.md) vypsat protokoly sledování pro všechny kontexty.

- [WriteContextTLogs](../msbuild/writecontexttlogs.md) vypsat protokol sledování pro aktuální kontext.