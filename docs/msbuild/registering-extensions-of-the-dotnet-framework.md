---
title: "Registrace rozšíření rozhraní .NET Framework | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Add References dialog box, registering extensions of the .NET Framework
- MSBuild, registering extensions of the .NET Framework
- .NET Framework extensions, registering
ms.assetid: deee6f53-ea87-4b88-a120-bea589822e03
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: 495a6bb1d72e521b3f44ea989974446def555c15
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="registering-extensions-of-the-net-framework"></a>Registrace rozšíření rozhraní .NET Framework
Můžete vyvíjet sestavení, které rozšiřuje na konkrétní verzi rozhraní .NET Framework. Chcete-li povolit sestavení se objeví v sadě Visual Studio **přidat odkazy** dialogové okno, je nutné přidat složku, která obsahuje do registru systému.  
  
 Předpokládejme například, že společnost Trey Research vyvinula knihovnu, která rozšiřuje rozhraní .NET Framework 4 a chce sestavení knihovny se objeví v **přidat odkazy** dialogové okno když na projekt cílí na rozhraní .NET Framework 4. Také předpokládají, že sestavení jsou 32bitová verze sestavení spuštěná v počítači 32bitová nebo 64bitová verze sestavení spuštěná na 64bitovém počítači a že bude nainstalována ve složce C:\TreyResearch\Extensions4\.  
  
 Pomocí tohoto klíče zaregistrujte tuto složku: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\. NETFramework\v4.0.21006\AssemblyFoldersEx\TreyResearch\\. Zadejte klíč tato výchozí hodnota: C:\TreyResearch\Extensions4.  
  
> [!NOTE]
>  Číslo sestavení verzi rozhraní .NET Framework se může lišit.  
  
 Pro registraci sestavení 32-bit na 64bitovém počítači, použijte Wow6432 uzlu, například: HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\\. NETFramework\v4.0.21006\AssemblyFoldersEx\TreyResearch\\.  
  
## <a name="see-also"></a>Viz také  
 [Visual Studio Integration](../msbuild/visual-studio-integration-msbuild.md)