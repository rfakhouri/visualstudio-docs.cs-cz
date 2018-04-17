---
title: Registrace rozšíření rozhraní .NET Framework | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- Add References dialog box, registering extensions of the .NET Framework
- MSBuild, registering extensions of the .NET Framework
- .NET Framework extensions, registering
ms.assetid: deee6f53-ea87-4b88-a120-bea589822e03
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 5e6d9de84f79bf26ee460cb6d93bd92600dff8c8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="registering-extensions-of-the-net-framework"></a>Registrace rozšíření rozhraní .NET Framework
Můžete vyvíjet sestavení, které rozšiřuje na konkrétní verzi rozhraní .NET Framework. Chcete-li povolit sestavení se objeví v sadě Visual Studio **přidat odkazy** dialogové okno, je nutné přidat složku, která obsahuje do registru systému.  
  
 Předpokládejme například, že společnost Trey Research vyvinula knihovnu, která rozšiřuje rozhraní .NET Framework 4 a chce sestavení knihovny se objeví v **přidat odkazy** dialogové okno když na projekt cílí na rozhraní .NET Framework 4. Také předpokládají, že sestavení jsou 32bitová verze sestavení spuštěná v počítači 32bitová nebo 64bitová verze sestavení spuštěná na 64bitovém počítači a že bude nainstalována ve složce C:\TreyResearch\Extensions4\.  
  
 Pomocí tohoto klíče zaregistrujte tuto složku: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\. NETFramework\v4.0.21006\AssemblyFoldersEx\TreyResearch\\. Zadejte klíč tato výchozí hodnota: C:\TreyResearch\Extensions4.  
  
> [!NOTE]
>  Číslo sestavení verzi rozhraní .NET Framework se může lišit.  
  
 Pro registraci sestavení 32-bit na 64bitovém počítači, použijte Wow6432 uzlu, například: HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\\. NETFramework\v4.0.21006\AssemblyFoldersEx\TreyResearch\\.  
  
## <a name="see-also"></a>Viz také  
 [Integrace sady Visual Studio](../msbuild/visual-studio-integration-msbuild.md)