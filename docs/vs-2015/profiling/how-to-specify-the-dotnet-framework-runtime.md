---
title: 'Postupy: Určení modulu Runtime rozhraní .NET Framework | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- Profiling Tools, .NET Framework versions
- .NET Framework versions,profililng
ms.assetid: d39f3579-719a-4f47-a97d-5b4232fe4c64
caps.latest.revision: 15
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 5ce968e53dc00cd46d27154f4c6217fcc815ade1
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54771904"
---
# <a name="how-to-specify-the-net-framework-runtime"></a>Postupy: Určení modulu Runtime rozhraní .NET Framework
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

S vydáním [!INCLUDE[net_v40_long](../includes/net-v40-long-md.md)], aplikace se může skládat z modulů, které byly vytvořeny pomocí různých verzí [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] za běhu. Ve výchozím nastavení [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] nástrojů pro profilaci sady Profilovat první modulu runtime, který je načten aplikací. Můžete zadat za běhu, která má být profilována při spuštění aplikace s profilerem a při připojení profileru k již běžícímu aplikace.  
  
 **Požadavky**  
  
-   [!INCLUDE[vsUltLong](../includes/vsultlong-md.md)], [!INCLUDE[vsPreLong](../includes/vsprelong-md.md)], [!INCLUDE[vsPro](../includes/vspro-md.md)]  
  
### <a name="to-specify-the-net-framework-run-time-to-profile-when-starting-an-application-with-the-profiler"></a>Chcete-li určit běhu rozhraní .NET Framework profil při spuštění aplikace s profilerem  
  
1.  V **prohlížeč výkonu**, klikněte pravým tlačítkem na relaci výkonu, klikněte na tlačítko **vlastnosti**a potom klikněte na tlačítko **Upřesnit**.  
  
     **Cílová verze CLR** seznamu se zobrazí **automatické** a verze [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] modulu runtime, které jsou nainstalovány v počítači.  
  
2.  Proveďte jeden z následujících kroků:  
  
    -   Klikněte na verzi CLR, který chcete Profilovat.  
  
    -   Klikněte na tlačítko **automatické** Profilovat první verze, která jsou načtená aplikací.  
  
### <a name="to-specify-the-net-framework-run-time-to-profile-when-attaching-the-profiler-to-an-application"></a>K určení běhu rozhraní .NET Framework profilu, pokud připojení profileru k aplikaci  
  
1.  V nabídce analyzovat přejděte na Profiler a pak klikněte na tlačítko Attach/Detach.  
  
2.  Na připojit Profiler k procesu – dialogové okno klikněte na proces, který chcete Profilovat.  
  
     **Cílová verze CLR** pole se seznamem s **automatické** a verze [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] modulu runtime, které jsou nainstalovány v počítači.  
  
3.  Proveďte jeden z následujících kroků:  
  
    -   Klikněte na verzi CLR, který chcete Profilovat.  
  
    -   Klikněte na tlačítko **automatické** Profilovat verze, která jsou načtená při připojí profiler k aplikaci.
