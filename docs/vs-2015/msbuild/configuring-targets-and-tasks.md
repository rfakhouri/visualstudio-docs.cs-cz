---
title: Konfigurace cílů a úloh | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: conceptual
ms.assetid: 9aabe67a-1720-4bbf-80d3-822b3ccf75c0
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 304ebde1c30a78ab000a1fae4a16b5082b0aeecf
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54769263"
---
# <a name="configuring-targets-and-tasks"></a>Konfigurace cílů a úloh
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
Můžete nakonfigurovat cíle nástroje MSBuild a aby úlohy běžely na více instancí procesu pomocí nástroje MSBuild tak, že je možné cílit na kontextu, které se liší od spustíte v. Můžete například směrovat 32bitovou aplikaci rozhraní .NET Framework 2.0 v operačním systému 64bitová verze rozhraní .NET Framework 4.5 je spuštěn vývojovém počítači. Můžete také směrovat počítače se systémem pomocí rozhraní .NET Framework 4 nebo dřívější. Kombinace 32 nebo 64bitovou a konkrétní verzi rozhraní .NET Framework se označuje jako *cílový kontext*.  
  
## <a name="installation"></a>Instalace  
 Rozhraní .NET Framework 4.5 a 4.5.1 nahradit common language runtime (CLR), cíle, úkoly a nástroje rozhraní .NET Framework 4 bez nich. Rozhraní .NET Framework 4.5.1 je nainstalován jako součást [!INCLUDE[vs_dev12](../includes/vs-dev12-md.md)].  
  
 Pokud chcete nainstalovat MSBuild odděleně od sady Visual Studio, můžete stáhnout instalační balíček z [MSBuild Stáhnout](http://go.microsoft.com/fwlink/?LinkId=309745). Musíte také nainstalovat rozhraní .NET Framework verze, kterou chcete použít také.  
  
## <a name="targets-and-tasks"></a>Cíle a úlohy  
 Spuštění nástroje MSBuild určité úlohy mimo proces cílit s větším počtem kontexty sestavení.  32bitový nástroj MSBuild může být například spuštění úlohy sestavení jako 64bitový proces na 64bitovém počítači. Toto se řídí `UsingTask` argumenty a `Task` parametry. Nastavte cíle nainstalovat rozhraní .NET Framework 4.5 těchto argumentů a parametrů a nevyžaduje žádné změny k sestavování aplikací pro různé kontexty cíl.  
  
 Pokud chcete vytvořit vlastní cílový kontext, musíte nastavit tyto argumentů a parametrů odpovídajícím způsobem. Hledejte v rozhraní .NET Framework 4.5 Microsoft.Common.targets soubor a soubor Microsoft.Common.Tasks příklady.  Informace o tom, jak vytvořit vlastní úkol, který můžete pracovat s více kontexty cíl nebo úprava existující úlohy najdete v tématu [jak: Konfigurace cílů a úloh](../msbuild/how-to-configure-targets-and-tasks.md).  
  
## <a name="see-also"></a>Viz také  
 [Cílení na více verzí](../msbuild/msbuild-multitargeting-overview.md)
