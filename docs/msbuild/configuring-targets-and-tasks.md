---
title: "Konfigurace cílů a úloh | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9aabe67a-1720-4bbf-80d3-822b3ccf75c0
caps.latest.revision: "6"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: d86802493e07bfd865ef0a737acae94dde95bf8b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="configuring-targets-and-tasks"></a>Konfigurace cílů a úloh
Můžete nakonfigurovat cíle MSBuild a aby úlohy běžely out-of-process pomocí nástroje MSBuild tak, aby můžete určit cílovou kontextů, které se liší od toho, kterou používáte na. Například můžete určit cílovou 32bitová aplikace rozhraní .NET Framework 2.0, když vývojovém počítači běží na operačním systému 64bitová verze rozhraní .NET Framework 4.5. Také můžete vybrat počítače, které spustit v rozhraní .NET Framework 4 nebo starším. Kombinace 32 - bitová nebo 64verze a na konkrétní verzi rozhraní .NET Framework se označuje jako *cílový kontext*.  
  
## <a name="installation"></a>Instalace  
 Rozhraní .NET Framework 4.5 a 4.5.1 nahraďte bez přejmenování je modul common language runtime (CLR), cíle, úlohy a nástroje pro rozhraní .NET Framework 4. Rozhraní .NET Framework 4.5.1 je nainstalován jako součást [!INCLUDE[vs_dev12](../extensibility/includes/vs_dev12_md.md)].  
  
 Pokud chcete instalovat nástroje MSBuild samostatně ze sady Visual Studio, můžete stáhnout instalační balíček z [MSBuild Stáhnout](http://go.microsoft.com/fwlink/?LinkId=309745). Je také nutné nainstalovat rozhraní .NET Framework verze, která si přejete použít taky.  
  
## <a name="targets-and-tasks"></a>Cílů a úloh  
 Spuštění nástroje MSBuild určité úlohy mimo proces cílit s větším počtem kontexty sestavení.  32-bit MSBuild například může spustit úlohu sestavení v procesu 64-bit do cílového počítače 64-bit. Toto se řídí `UsingTask` argumenty a `Task` parametry. Cíle nainstalovat rozhraní .NET Framework 4.5 nastavte tyto argumentů a parametrů a k vytváření aplikací pro různé cílové kontexty se nevyžadují žádné změny.  
  
 Pokud chcete vytvořit vlastní cílový kontext, musíte nastavit tyto argumentů a parametrů správně. Vyhledejte v rozhraní .NET Framework 4.5 Microsoft.Common.targets soubor a soubor Microsoft.Common.Tasks příklady.  Informace o tom, jak vytvořit vlastní úkol, který můžete pracovat s více kontexty cíl nebo jak upravit stávající úlohy najdete v tématu [postupy: konfigurace cílů a úloh](../msbuild/how-to-configure-targets-and-tasks.md).  
  
## <a name="see-also"></a>Viz také  
 [Cílení na více verzí](../msbuild/msbuild-multitargeting-overview.md)