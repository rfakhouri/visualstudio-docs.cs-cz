---
title: Registrace rozšíření rozhraní .NET Framework | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Add References dialog box, registering extensions of the .NET Framework
- MSBuild, registering extensions of the .NET Framework
- .NET Framework extensions, registering
ms.assetid: deee6f53-ea87-4b88-a120-bea589822e03
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 48322adffff68d1eecb0d44da7e8f78d39d82203
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53986063"
---
# <a name="register-extensions-of-the-net-framework"></a>Registrace rozšíření rozhraní .NET Framework
Můžete vyvíjet sestavení, která rozšiřuje konkrétní verzi rozhraní .NET Framework. Povolit sestavení se zobrazí v sadě Visual Studio **Add References** dialogové okno, je nutné přidat složku obsahující do systémového registru.  
  
 Předpokládejme například, že společnost Trey Research má vyvinuté knihovnu, která rozšiřuje rozhraní .NET Framework 4 a chce, aby se sestavení knihovny se zobrazí v **Add References** dialogové okno když projekt cílí na rozhraní .NET Framework 4. Taky se předpokládá, že sestavení jsou 32bitová sestavení instalujte spuštěná na počítači 32bitové nebo 64bitové sestavení běží na 64bitovém počítači, a že se nainstalují v *C:\TreyResearch\Extensions4\\*  složky.  
  
 Pomocí tohoto klíče zaregistrujte tuto složku: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\. NETFramework\v4.0.21006\AssemblyFoldersEx\TreyResearch\\**. Byla tato výchozí hodnota klíče: **C:\TreyResearch\Extensions4**.  
  
> [!NOTE]
>  Číslo sestavení rozhraní .NET Framework verze se může lišit.  
  
 K registraci sestavení 32-bit na 64bitovém počítači, použijte Wow6432 uzlu, například: **HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\\. NETFramework\v4.0.21006\AssemblyFoldersEx\TreyResearch\\**.  
  
### <a name="see-also"></a>Viz také:  
 [Integrace se sadou Visual Studio](../msbuild/visual-studio-integration-msbuild.md)