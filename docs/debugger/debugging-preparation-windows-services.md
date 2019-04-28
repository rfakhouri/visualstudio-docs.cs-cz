---
title: Příprava na ladění služeb Windows | Dokumentace Microsoftu
ms.custom: seodec18
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], Windows services
- Windows Service applications, debugging
ms.assetid: ac0a99f7-ec3d-4a20-b17f-698a817fdcc2
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e734a500d12c15022421383743c1fe1f45794d1b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62852577"
---
# <a name="debugging-preparation-windows-services"></a>Příprava ladění: Služby systému Windows
Služba Windows je program, který běží na pozadí v rámci Microsoft Windows. Mezi příklady patří služby Systémový čas Windows, která aktualizuje viditelné hodiny a službu Telnet. Služba Windows nemůže být spuštěna v rámci [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]; se musí spustit v rámci kontextu správce řízení služeb. Další informace najdete v tématu [vytváření služeb Windows](/dotnet/framework/windows-services/how-to-create-windows-services), [ladění aplikace služby Windows](/dotnet/framework/windows-services/how-to-debug-windows-service-applications), a [aplikace služby Windows](/dotnet/framework/windows-services/index).

## <a name="see-also"></a>Viz také
- [Ladění spravovaného kódu](../debugger/debugging-managed-code.md)
- [Typy projektů jazyka C#, F# a Visual Basic](../debugger/debugging-preparation-csharp-f-hash-and-visual-basic-project-types.md)
- [Nastavení projektu pro konfiguraci ladění jazyka C#](../debugger/project-settings-for-csharp-debug-configurations.md)
- [Nastavení projektu pro konfiguraci ladění jazyka Visual Basic](../debugger/project-settings-for-a-visual-basic-debug-configuration.md)
- [Postupy: Ladění metody OnStart](../debugger/how-to-debug-the-onstart-method.md)