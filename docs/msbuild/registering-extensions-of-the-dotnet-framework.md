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
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: bf1eb0001ca7c8b87fa44b5ea861df9d9fcba84d
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56644338"
---
# <a name="register-extensions-of-the-net-framework"></a>Registrace rozšíření rozhraní .NET Framework
Můžete vyvíjet sestavení, která rozšiřuje konkrétní verzi rozhraní .NET Framework. Povolit sestavení se zobrazí v sadě Visual Studio **Add References** dialogové okno, je nutné přidat složku obsahující do systémového registru.

 Předpokládejme například, že společnost Trey Research má vyvinuté knihovnu, která rozšiřuje rozhraní .NET Framework 4 a chce, aby se sestavení knihovny se zobrazí v **Add References** dialogové okno když projekt cílí na rozhraní .NET Framework 4. Taky se předpokládá, že sestavení jsou 32bitová sestavení instalujte spuštěná na počítači 32bitové nebo 64bitové sestavení běží na 64bitovém počítači, a že se nainstalují v *C:\TreyResearch\Extensions4\\*  složky.

 Pomocí tohoto klíče zaregistrujte tuto složku: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework\v4.0.21006\AssemblyFoldersEx\TreyResearch\\**. Byla tato výchozí hodnota klíče: **C:\TreyResearch\Extensions4**.

> [!NOTE]
>  Číslo sestavení rozhraní .NET Framework verze se může lišit.

 K registraci sestavení 32-bit na 64bitovém počítači, použijte Wow6432 uzlu, například: **HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\\.NETFramework\v4.0.21006\AssemblyFoldersEx\TreyResearch\\**.

### <a name="see-also"></a>Viz také:
- [Integrace se sadou Visual Studio](../msbuild/visual-studio-integration-msbuild.md)