---
title: Nasazení nezbytných součástí pro 64bitové aplikace | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- deploying applications [Visual Studio], 64-bit
- 64-bit [Visual Studio]
- 64-bit programming [Visual Studio]
- 64-bit applications [Visual Studio]
ms.assetid: 87399e20-5510-41e4-b5b7-4a87c5773f21
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f481d944baf60120bf691313400489c876ecf5c2
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56606248"
---
# <a name="deploy-prerequisites-for-64-bit-applications"></a>Nasazení nezbytných součástí pro 64bitové aplikace
ClickOnce – nasazení podporuje instalaci aplikací na 64bitových platformách. Cílové platformy jsou **x86** pro 32bitové platformy, **x64** pro počítače podporuje AMD64 a podporou technologie EM64T instrukční sadu, a **Itanium** pro procesor Itanium 64-bit.

## <a name="prerequisites"></a>Požadavky
 V následující tabulce jsou uvedeny distribuovatelné součásti, které můžete použít jako požadavky na instalaci 64bitové aplikace.

 Pokud vyberete požadovanou součást, která se nevyznačuje 64bitové komponenty, může se zobrazit upozornění oznamující, že vybrané balíčky nejsou k dispozici pro 64bitovou platformu.


| Distribuovatelné součásti | Podpora x64 | Podpora IA64 |
| - |-------------|--------------|
| [!INCLUDE[vsto_runtime](../deployment/includes/vsto_runtime_md.md)] | Ano | Ne |
| Knihovny Visual C++ 2010 Runtime (IA64) | Ne | Ano |
| Knihovny Visual C++ 2010 Runtime (x64) | Ano | Ne |
| Microsoft .NET Framework 4 (x86 a x64) | Ano | |
| Microsoft .NET Framework 4 Client Profile (x86 a x64) | Ano | |

## <a name="see-also"></a>Viz také:
- [Nasazení aplikací, služeb a komponent](../deployment/deploying-applications-services-and-components.md)
- [Postupy: Instalace předpokladů s aplikací ClickOnce](../deployment/how-to-install-prerequisites-with-a-clickonce-application.md)
- [64bitové aplikace](/dotnet/framework/64-bit-apps)