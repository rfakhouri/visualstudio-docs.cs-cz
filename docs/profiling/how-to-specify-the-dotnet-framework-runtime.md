---
title: 'Postupy: Určení modulu Runtime rozhraní .NET Framework | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Profiling Tools, .NET Framework versions
- .NET Framework versions,profililng
ms.assetid: d39f3579-719a-4f47-a97d-5b4232fe4c64
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: d9c62e430d19bbd2c03afbb4db76fca56563cb3c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62996315"
---
# <a name="how-to-specify-the-net-framework-runtime"></a>Postupy: Určení modulu runtime .NET Framework

S vydáním [!INCLUDE[net_v40_long](../code-quality/includes/net_v40_long_md.md)], aplikace se může skládat z modulů, které byly vytvořeny pomocí různých verzí [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] za běhu. Ve výchozím profilu Visual Studio nástroje pro profilaci sady první modulu runtime, který je načten aplikací. Můžete zadat za běhu, která má být profilována při spuštění aplikace s profilerem a při připojení profileru k již běžícímu aplikace.

## <a name="to-specify-the-net-framework-run-time-to-profile-when-starting-an-application-with-the-profiler"></a>Chcete-li určit běhu rozhraní .NET Framework profil při spuštění aplikace s profilerem

1. V **prohlížeč výkonu**, klikněte pravým tlačítkem na relaci výkonu, klikněte na tlačítko **vlastnosti**a potom klikněte na tlačítko **Upřesnit**.

     **Cílová verze CLR** seznamu se zobrazí **automatické** a verze [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] modulu runtime, které jsou nainstalovány v počítači.

2. Proveďte jeden z následujících kroků:

    - Klikněte na verzi CLR, který chcete Profilovat.

    - Klikněte na tlačítko **automatické** Profilovat první verze, která jsou načtená aplikací.

## <a name="to-specify-the-net-framework-run-time-to-profile-when-attaching-the-profiler-to-an-application"></a>K určení běhu rozhraní .NET Framework profilu, pokud připojení profileru k aplikaci

1. Na **analyzovat** nabídky, přejděte k **Profiler**, pak klikněte na tlačítko **Attach/Detach**.

2. Na **připojit Profiler k procesu** dialogového okna klikněte na proces, který chcete Profilovat.

     **Cílová verze CLR** pole se seznamem s **automatické** a verze [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] modulu runtime, které jsou nainstalovány v počítači.

3. Proveďte jeden z následujících kroků:

    - Klikněte na verzi CLR, který chcete Profilovat.

    - Klikněte na tlačítko **automatické** Profilovat verze, která jsou načtená při připojí profiler k aplikaci.