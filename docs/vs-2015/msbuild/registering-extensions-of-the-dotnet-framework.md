---
title: Registrace rozšíření rozhraní .NET Framework | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Add References dialog box, registering extensions of the .NET Framework
- MSBuild, registering extensions of the .NET Framework
- .NET Framework extensions, registering
ms.assetid: deee6f53-ea87-4b88-a120-bea589822e03
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2a2d3e281562be5234e0a70a877a6c169c346995
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42669153"
---
# <a name="registering-extensions-of-the-net-framework"></a>Registrace rozšíření rozhraní .NET Framework
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [registrace rozšíření rozhraní .NET Framework](https://docs.microsoft.com/visualstudio/msbuild/registering-extensions-of-the-dotnet-framework).  
  
  
Můžete vyvíjet sestavení, která rozšiřuje konkrétní verzi rozhraní .NET Framework. Povolit sestavení se zobrazí v sadě Visual Studio **Add References** dialogové okno, je nutné přidat složku obsahující do systémového registru.  
  
 Předpokládejme například, že společnost Trey Research má vyvinuté knihovnu, která rozšiřuje rozhraní .NET Framework 4 a chce, aby se sestavení knihovny se zobrazí v **Add References** dialogové okno když projekt cílí na rozhraní .NET Framework 4. Taky se předpokládá, že sestavení jsou 32bitová sestavení instalujte spuštěná na počítači 32bitové nebo 64bitové sestavení běží na 64bitovém počítači, a že se nainstaluje ve složce C:\TreyResearch\Extensions4\.  
  
 Pomocí tohoto klíče zaregistrujte tuto složku: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\. NETFramework\v4.0.21006\AssemblyFoldersEx\TreyResearch\\. Byla tato výchozí hodnota klíče: C:\TreyResearch\Extensions4.  
  
> [!NOTE]
>  Číslo sestavení rozhraní .NET Framework verze se může lišit.  
  
 K registraci sestavení 32-bit na 64bitovém počítači, použijte Wow6432 uzlu, například: HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\\. NETFramework\v4.0.21006\AssemblyFoldersEx\TreyResearch\\.  
  
## <a name="see-also"></a>Viz také  
 [Integrace se sadou Visual Studio](../msbuild/visual-studio-integration-msbuild.md)



